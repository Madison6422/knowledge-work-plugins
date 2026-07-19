---
name: plugin-audit
description: Check a plugin for the common mistakes before you ship it — missing or malformed frontmatter, skill name not matching its folder, commands that reference skills that don't exist, invalid .mcp.json or marketplace.json, and hardcoded tool names that should be ~~category placeholders. Returns a checklist of issues with fixes. Trigger with "audit the [plugin] plugin", "check my plugin for problems", "lint this plugin before I ship it".
---

# Plugin Audit

A pre-flight check that catches the mistakes that keep a plugin from loading or behaving right.

## What it does
Scans one plugin's files and reports problems: missing or malformed skill/command frontmatter, a skill whose `name` doesn't match its folder, commands pointing at skills that don't exist, `.mcp.json` or `marketplace.json` that isn't valid JSON or is missing the plugin, and hardcoded product names in skill prose that should be `~~category` placeholders. Each finding comes with the fix. It works entirely on local files.

## Connectors it uses
None — this plugin edits files, it doesn't connect to external tools.

> **No connectors?** Expected — auditing reads local files only. Point Claude at the plugin folder and it produces the report.

## What it checks
| Check | Looks for | Fix |
| --- | --- | --- |
| Frontmatter present | Every `SKILL.md`/command has valid YAML with required keys | Add `name`+`description` (skills) or `description`+`argument-hint` (commands) |
| Name matches folder | `name:` equals the `skills/<folder>` name | Rename the folder or the `name` so they match |
| Trigger phrases | Skill `description` ends with quoted trigger examples | Add `Trigger with "..."` phrases |
| Command → skill | Each command references a skill that exists | Fix the skill name or create the skill |
| JSON valid | `.mcp.json` and `marketplace.json` parse | Fix commas/brackets; validate |
| Registered | Plugin appears in `marketplace.json` `plugins` | Add the marketplace entry |
| Category placeholders | Prose uses `~~category`, not product names | Replace e.g. "Salesforce" with `~~CRM` |
| Server ↔ category | Every `~~category` in skills has a server (or intentional blank) in `.mcp.json` | Add the server or a placeholder |
| Section order | Skills keep the standard sections | Restore missing sections |

## How it works
1. **Take the plugin.** Name or folder. Claude reads its `plugin.json`, skills, commands, and `.mcp.json`.
2. **Run the checks above.** For each, mark pass/fail and capture the exact file and line.
3. **Flag hardcoded tools.** Search skill prose for known product names and suggest the `~~category` swap.
<!-- CUSTOMIZE: add your company's tool names here so the audit flags them (e.g. flag "Salesforce" → ~~CRM) -->
4. **Cross-check JSON.** Confirm `.mcp.json` and `marketplace.json` parse and that the plugin is registered. (Report only — this skill doesn't edit JSON.)
5. **Rank findings.** Blockers first (won't load), then structure, then style.
<!-- CUSTOMIZE: mark which checks are hard blocks vs. warnings for your team -->

## Output
```markdown
# Audit: <plugin>

**Blockers:** <n> · **Warnings:** <n> · **Style:** <n>

## Blockers
- [ ] <file> — <issue> → <fix>

## Warnings
- [ ] <file> — <issue> → <fix>

## Style
- [ ] <file>:<line> — hardcoded "<tool>" → use `~~<category>`

## Clean
- <checks that passed>
```

## Customize this skill
- List your company's tool names in step 3 so they get flagged for placeholder swaps.
<!-- CUSTOMIZE: any extra house rules to enforce (naming prefixes, required sections) -->
- Decide which checks are blockers vs. warnings for your team.

## Related skills
- **create-plugin** — run this audit as the last step before shipping a new plugin.
- **customize-plugin** — re-run after customizing to confirm structure survived.
- **connector-setup** — fix any `~~category` that has no server backing it.
