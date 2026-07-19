# Connectors

## How tool references work

The skills in this plugin are **tool-agnostic**. Instead of naming a specific
product, they refer to a tool by its *category* using a `~~placeholder` — for
example `~~data warehouse`, `~~notebook`, or `~~chat`. This keeps the prose
generic so the skills work with whatever server you have in that category.

The `.mcp.json` file pins the specific MCP servers your team actually uses. Any
MCP server in a given category will work — swap the pinned server for another in
the same category and the skills still read correctly. The `~~placeholder` is
the seam between the generic instructions and your concrete tools.

## Connectors for this plugin

| Category | Placeholder | Included servers | Other options |
|---|---|---|---|
| Data warehouse | `~~data warehouse` | Snowflake, Databricks, BigQuery | Redshift, Postgres |
| Notebook / BI | `~~notebook` | Hex | Deepnote, Mode |
| Product analytics | `~~product analytics` | Amplitude | Mixpanel, Heap, Pendo |
| BI / analytics | `~~analytics` | Definite | — |
| Project tracker | `~~project tracker` | Atlassian (Jira / Confluence) | Trello, Shortcut, Linear |
| Chat | `~~chat` | Slack | Microsoft Teams, Discord |
