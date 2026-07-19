---
name: create-plugin
description: Walk a team lead through building a brand-new plugin for this marketplace — copy the template, fill in plugin.json, register it in marketplace.json, and scaffold 3–5 skills and a couple of commands. Produces ready-to-edit markdown and exact JSON to paste. Trigger with "create a new plugin", "scaffold a plugin for [role]", "start a plugin for our [workflow] team".
---

# Create Plugin

Take a team lead from an idea ("a plugin for our RevOps team") to a working plugin folder they can customize.

## What it does
Guides you through the whole scaffold: copy `_template/` into a new plugin folder, fill in `plugin.json`, add an entry to `marketplace.json`, and write 3–5 skills plus a couple of commands using the repo's conventions. Claude produces the exact file contents and JSON snippets; you paste them in and edit the wording for your company. It works entirely on local files — no tools need to be connected.

## Connectors it uses
None — this plugin edits files, it doesn't connect to external tools.

> **No connectors?** That's the normal case. Everything here happens against the repo's markdown and JSON files. Paste in the role or workflow the plugin is for, and Claude drafts the scaffold from that plus web research on how that role works.

## How it works
1. **Scope the plugin.** Ask what role or workflow it serves, name 3–5 jobs it should do, and list the tool categories it touches (as `~~category` placeholders — `~~CRM`, `~~chat`, `~~data warehouse`).
2. **Pick a name.** Kebab-case, matches the folder (e.g. `revops`). This is the `name` in `plugin.json` and `marketplace.json`.
3. **Copy the template.** Duplicate `_template/` to `<plugin>/`. It ships with `.claude-plugin/plugin.json`, `.mcp.json`, and `skills/example-skill/`.
<!-- CUSTOMIZE: if your team keeps a house style guide for skills, point to it here -->
4. **Fill in `plugin.json`.** Set `name`, bump `version` to `1.0.0`, write a one-sentence `description`, and set `author.name`. (You edit the JSON that already exists — this skill just tells you what to write.)
5. **Register in `marketplace.json`.** Add an object to the `plugins` array: `name`, `displayName`, `source` (`./<plugin>`), and `description`.
6. **Write the skills.** For each job, create `skills/<skill>/SKILL.md` from the template below. Keep each 60–130 lines with the standard sections.
7. **Write the commands.** Add 1–3 `commands/<command>.md` files as thin entry points to the skills.
8. **Set up `.mcp.json`.** List one MCP server per tool category; leave `url` empty for any the team must fill in later. (See the **connector-setup** skill for the server shape.)
9. **Audit before you ship.** Run the **plugin-audit** skill to catch missing frontmatter, name mismatches, and hardcoded tool names.

### `plugin.json` template
```json
{
  "name": "<plugin-name>",
  "version": "1.0.0",
  "description": "One sentence on what this plugin helps a role do.",
  "author": { "name": "<Your Team>" }
}
```

### `marketplace.json` entry
```json
{
  "name": "<plugin-name>",
  "displayName": "<Display Name>",
  "source": "./<plugin-name>",
  "description": "One-line summary shown in the marketplace."
}
```

### `SKILL.md` skeleton
```markdown
---
name: <skill-name>
description: <2–3 sentences>. Trigger with "<phrase>", "<phrase>".
---

# <Title Case Name>
<one-line summary>

## What it does
<2–4 sentences>

## Connectors it uses
| Category | Placeholder | What it adds |
| --- | --- | --- |
| <Category> | `~~category` | <what it adds> |

> **No connectors?** <standalone path>

## How it works
1. <step, referencing ~~category tools>
<!-- CUSTOMIZE: ... -->

## Output
​```markdown
<shape of the deliverable>
​```

## Customize this skill
- <what to edit>

## Related skills
- **<sibling>** — <what it does>
```

## Output
```markdown
# New plugin: <plugin-name>

**Folder:** knowledge-work-plugins/<plugin-name>/
**Skills:** <skill>, <skill>, <skill>
**Commands:** /<plugin>:<command>, /<plugin>:<command>
**Categories:** ~~<category>, ~~<category>

## Files to create
- [ ] .claude-plugin/plugin.json   (contents below)
- [ ] skills/<skill>/SKILL.md       (draft below)
- [ ] commands/<command>.md         (draft below)
- [ ] .mcp.json                     (servers below)

## marketplace.json entry to add
<json block>
```

## Customize this skill
- Set your default `author.name` and starting `version` in step 4.
<!-- CUSTOMIZE: your org's naming rules for plugins and skills (prefixes, casing) -->
- List the tool categories your team most often needs so new plugins start from them.
<!-- CUSTOMIZE: a link to your internal skill style guide, if you keep one -->

## Related skills
- **customize-plugin** — adapt an existing plugin's wording and workflows to your company.
- **connector-setup** — fill in `.mcp.json` with the right MCP servers.
- **plugin-audit** — check the new plugin for common mistakes before shipping.
