# Your Plugin Name

<!-- CUSTOMIZE: replace this line with one sentence on what this plugin helps a role do. -->
One-line description of what this plugin does for its role.

This is a **template**. Copy this whole `_template/` folder to a new folder named
after your plugin, then fill everything in. Delete these instruction notes as you go.

## Steps to build your plugin

1. Rename the folder to your plugin's kebab-case name (e.g. `recruiting`).
2. Edit `.claude-plugin/plugin.json` — set `name` (must match the folder), `description`, `author`.
3. Edit `.mcp.json` — list the MCP servers for the tools this role uses. Leave a `url` empty (`""`) to mark a placeholder.
4. Write your skills under `skills/<skill-name>/SKILL.md` (copy `skills/example-skill/SKILL.md` as a starting point).
5. Write your slash commands under `commands/<command>.md` (copy `commands/example-command.md`).
6. Fill in `CONNECTORS.md` with the category → server table.
7. Add your plugin to `../.claude-plugin/marketplace.json`.

## What's inside

| Skill | What it does |
|-------|--------------|
| `example-skill` | <!-- CUSTOMIZE: describe each skill --> |

| Command | What it does |
|---------|--------------|
| `/your-plugin-name:example-command` | <!-- CUSTOMIZE: describe each command --> |

## Connectors

See [CONNECTORS.md](./CONNECTORS.md).

## Customize for your team

- Put your terminology, workflows, and rules into each `SKILL.md`.
- Point `.mcp.json` at your actual tools.
- Adjust each skill's `## Output` block to the format your team expects.
