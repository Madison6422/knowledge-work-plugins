# Contributing

This is a starter repo meant to be forked and customized. Contributions that make the *starter* better — clearer skills, more accurate connector configs, new role plugins — are welcome.

Everything is markdown and JSON. There is nothing to build, compile, or run.

## Repo layout

```
knowledge-work-plugins/
├── .claude-plugin/marketplace.json   # index of all plugins — every plugin must be listed here
├── _template/                        # copy this to start a new plugin
└── <plugin>/
    ├── .claude-plugin/plugin.json    # manifest
    ├── .mcp.json                     # connectors (MCP servers)
    ├── CONNECTORS.md                 # category → placeholder → servers
    ├── README.md
    ├── commands/<command>.md         # slash commands
    └── skills/<skill>/SKILL.md       # skills
```

## Create a new plugin (by hand)

1. **Copy the template.** `cp -r _template your-plugin-name`
2. **Fill in the manifest** — `your-plugin-name/.claude-plugin/plugin.json`:
   ```json
   {
     "name": "your-plugin-name",
     "version": "0.1.0",
     "description": "One sentence on what this plugin helps a role do.",
     "author": { "name": "Your Team" }
   }
   ```
   `name` must match the folder name and be kebab-case.
3. **Set up connectors** — edit `.mcp.json`. Each entry is an MCP server:
   ```json
   {
     "mcpServers": {
       "notion": { "type": "http", "url": "https://mcp.notion.com/mcp" }
     }
   }
   ```
   Leave a `url` empty (`""`) to mark a server as a placeholder the installer must fill in.
4. **Write skills.** One folder per skill under `skills/`, each with a `SKILL.md`. Frontmatter needs a `name` (matching the folder) and a `description` whose last sentence lists the trigger phrases. See the [style rules](#skill-style-rules) below.
5. **Write commands.** One `.md` per command under `commands/`. Frontmatter needs `description` and `argument-hint`. Body is a short title plus a few numbered steps that point at a skill.
6. **Document connectors** in `CONNECTORS.md` and summarize the plugin in `README.md`.
7. **Register it.** Add an object to the `plugins` array in `.claude-plugin/marketplace.json`:
   ```json
   { "name": "your-plugin-name", "displayName": "Your Plugin", "source": "./your-plugin-name", "description": "..." }
   ```
8. **Validate the JSON** (see below) and open a PR.

## Skill style rules

- **Tool-agnostic.** Refer to connected tools by category with a `~~` placeholder (`~~CRM`, `~~chat`, `~~data warehouse`), never a hardcoded product name. The `.mcp.json` pins the actual servers.
- **Works standalone.** Every skill must be useful with no connectors, and explain what each connector adds.
- **Mark customization points** with `<!-- CUSTOMIZE: ... -->` so team leads know where to edit.
- **Human approval** for anything that touches money, customers, external sends, or legal/compliance judgment: Claude drafts, a person approves.
- Keep each `SKILL.md` focused (~60–130 lines).

## Validate before you PR

```bash
# every JSON file parses
find . -name '*.json' -print -exec python3 -c "import json,sys; json.load(open(sys.argv[1]))" {} \;

# every skill folder has a SKILL.md
find . -type d -path '*/skills/*' -maxdepth 3 ! -exec test -e '{}/SKILL.md' \; -print
```

If you installed the `plugin-management` plugin, `/plugin-management:plugin-audit` runs these checks and more for you.

## Conventions

- Kebab-case for plugin, skill, and command names.
- Skill folder name == the `name` in its frontmatter.
- Bump `version` in `plugin.json` when you change a plugin.
- Keep secrets out of the repo. `.mcp.json` holds public endpoints and OAuth client IDs only — never tokens or API keys.
