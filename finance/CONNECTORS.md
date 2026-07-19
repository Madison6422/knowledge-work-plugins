# Connectors

## How tool references work

This plugin is **tool-agnostic**. Skills refer to a connected tool by its *category* using a `~~category` placeholder — for example `~~data warehouse` or `~~chat` — never a specific product name. This keeps the prose the same no matter which server you connect.

The `.mcp.json` file pins the specific MCP servers this plugin ships with. Any MCP server in a given category works in place of the pinned one — swap the entries in `.mcp.json` and the skills keep working, because they only ever reference the category. Every skill also runs **standalone**: with no connectors, paste in the numbers or documents and Claude works from those, always showing each figure with its source.

## Connectors for this plugin

| Category | Placeholder | Included servers | Other options |
|---|---|---|---|
| Data warehouse | `~~data warehouse` | Snowflake, Databricks, BigQuery | Redshift, Postgres |
| Chat | `~~chat` | Slack | Microsoft Teams, Discord |
| Email / docs / calendar | `~~email` | Microsoft 365 | Microsoft 365 covers mail, docs, and calendar |
| Email | `~~email` | Gmail | Microsoft 365 |
| Calendar | `~~calendar` | Google Calendar | Microsoft 365 |
