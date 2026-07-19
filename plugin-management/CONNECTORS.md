# Connectors — Plugin Management

## How tool references work
Across this marketplace, plugins stay **tool-agnostic**. Skills never name a specific product — they refer to a tool by category with a `~~` placeholder: `~~chat`, `~~CRM`, `~~project tracker`, `~~data warehouse`, `~~email`, `~~calendar`. Each plugin's `.mcp.json` is what pins those categories to real MCP servers, so any server in a category can back a skill without touching the prose. Swapping tools means editing `.mcp.json`, not the skills.

## Connectors for this plugin
**This plugin has no connectors of its own.** Plugin Management edits files — it copies templates, writes skills and commands, and drafts JSON. It does not connect to any external tool, so there is no `.mcp.json` and no server table here.

Its job is the opposite: it helps you **set up connectors for the other plugins** in this repo. Use the **connector-setup** skill (or `/plugin-management:add-connector`) to add, swap, or placeholder MCP servers in another plugin's `.mcp.json`, and keep that plugin's own `CONNECTORS.md` category table in sync.

For the `~~category` → server mappings you'll be configuring, see the category guidance in the marketplace's authoring spec and each target plugin's `CONNECTORS.md`.
