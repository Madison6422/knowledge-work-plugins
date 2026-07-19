# Plugin Management

Create new plugins or customize existing ones for your organization's specific tools and workflows. Configure MCP servers, adjust plugin behavior, and adapt templates to match how your team works.

This is the meta-plugin: it helps a team lead build and tailor the *other* plugins in this marketplace. It edits local markdown and JSON files — it doesn't connect to any external tool.

## What's inside

### Skills
| Skill | What it does |
| --- | --- |
| `create-plugin` | Walk through scaffolding a new plugin: copy `_template/`, fill in `plugin.json`, register it in `marketplace.json`, and draft 3–5 skills and a couple of commands. |
| `customize-plugin` | Adapt an existing plugin to your company — fill in `<!-- CUSTOMIZE -->` markers, tighten trigger phrases, and adjust output templates without breaking structure. |
| `connector-setup` | Explain and edit `.mcp.json`: add or swap an MCP server for a category, use the `type: http` + `url` shape, choose OAuth vs. token, or leave an editable placeholder. |
| `plugin-audit` | Check a plugin for common problems: missing frontmatter, skill/folder name mismatches, commands referencing missing skills, invalid JSON, and hardcoded tool names. |

### Commands
| Command | What it does |
| --- | --- |
| `/plugin-management:create-plugin` | Runs **create-plugin** for a role or workflow you name. |
| `/plugin-management:customize-plugin` | Runs **customize-plugin** for a plugin you name. |
| `/plugin-management:add-connector` | Runs **connector-setup** to add or swap a server for a tool or category. |

## Connectors

This plugin has **no connectors of its own** — see [CONNECTORS.md](./CONNECTORS.md). Instead, it helps you configure connectors (the `~~category` → MCP server mapping in `.mcp.json`) for every other plugin in the repo.

## Customize for your team
- In **create-plugin**, set your default `author.name`, starting `version`, and the tool categories new plugins usually need.
- In **customize-plugin**, add a company glossary and your standard output header/sign-off so terminology stays uniform.
- In **connector-setup**, record your default MCP server per category and your OAuth-vs-token convention.
- In **plugin-audit**, list your company's tool names so the audit flags them for `~~category` swaps, and mark which checks are hard blockers.
- Fill in every `<!-- CUSTOMIZE -->` marker across the skills as you adopt them.
