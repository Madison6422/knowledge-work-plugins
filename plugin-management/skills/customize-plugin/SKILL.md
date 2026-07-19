---
name: customize-plugin
description: Adapt an existing plugin to how your company actually works — inject terminology and workflows at the <!-- CUSTOMIZE --> markers, tighten trigger phrases, and adjust output templates without breaking the file structure. Keeps every skill's required sections intact. Trigger with "customize the [plugin] plugin", "adapt [plugin] for our company", "make the sales plugin match our process".
---

# Customize Plugin

Take a generic starter plugin and make it sound and behave like your team, without breaking its structure.

## What it does
Reads an existing plugin's skills and commands, finds every `<!-- CUSTOMIZE -->` marker, and helps you fill each one with your company's terminology, workflows, thresholds, and templates. It tightens trigger phrases so skills fire on the words your team actually uses, and adjusts output shapes to match your formats — all while preserving the required frontmatter and section order. It works only on local files.

## Connectors it uses
None — this plugin edits files, it doesn't connect to external tools.

> **No connectors?** That's expected. All edits happen against the plugin's markdown. Tell Claude your company's terms, stage names, and formats, and it rewrites the marked spots to match.

## How it works
1. **Pick the plugin.** Name it (e.g. `sales`) or point at its folder. Claude lists its skills and commands.
2. **Scan the markers.** For each `SKILL.md`, collect every `<!-- CUSTOMIZE: ... -->` line and the "Customize this skill" bullets — that's the editable surface.
3. **Gather your specifics.** Ask for the details each marker needs: terminology, stage/status names, approval rules, thresholds, and preferred output templates.
<!-- CUSTOMIZE: keep a short glossary of your company's terms so this stays consistent across plugins -->
4. **Edit in place.** Replace generic wording with yours *around* each marker; keep the marker so the next person can re-customize. Never delete required sections (`## What it does`, `## How it works`, `## Output`, etc.).
5. **Tighten triggers.** In each skill's frontmatter `description`, swap the example trigger phrases for the exact ones your team says. Keep them in quotes.
<!-- CUSTOMIZE: list the phrases your team actually uses to invoke each workflow -->
6. **Adjust outputs.** Reshape the ```markdown``` output block to your real format (field names, section order, sign-off lines) — but keep it a fenced markdown block.
7. **Keep tool references generic.** Leave `~~category` placeholders as placeholders; the actual servers live in `.mcp.json`. (Use **connector-setup** to change those.)
8. **Re-audit.** Run **plugin-audit** to confirm nothing structural broke.

## What to keep vs. change
| Keep (structure) | Change (your company) |
| --- | --- |
| Frontmatter keys `name` / `description` | The trigger phrases inside `description` |
| Section headings and their order | The prose and examples under them |
| `~~category` placeholders | Which server backs them (in `.mcp.json`) |
| The `<!-- CUSTOMIZE -->` markers themselves | The text around each marker |
| A fenced `Output` block | The fields inside it |

## Output
```markdown
# Customized: <plugin> for <company>

## Changes by skill
### <skill-name>
- Terminology: <old> → <new>
- Triggers: added "<phrase>", "<phrase>"
- Output: <what changed>
- Markers filled: <n> of <total>

## Left as placeholders (need a decision)
- <skill> — <marker that still needs input>
```

## Customize this skill
- Add your company glossary in step 3 so terminology stays uniform across plugins.
<!-- CUSTOMIZE: your approval rules — who signs off on customer-facing or money-touching outputs -->
- Note any sections your org always adds (e.g. a compliance line) so they get applied consistently.
<!-- CUSTOMIZE: your standard output header/sign-off format -->

## Related skills
- **create-plugin** — scaffold a new plugin from the template instead of adapting one.
- **connector-setup** — point a `~~category` placeholder at the right MCP server.
- **plugin-audit** — verify structure is intact after your edits.
