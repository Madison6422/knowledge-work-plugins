# Connectors

## How tool references work

This plugin is **tool-agnostic**. Skills never name a specific product — they refer to tools by *category* using a `~~placeholder` marker, like `~~chat`, `~~knowledge base`, `~~project tracker`, or `~~email`. This keeps the prose portable: any MCP server in a given category works, and swapping one product for another needs no edits to the skills.

The concrete servers are pinned in **`.mcp.json`**. That file maps each category to the specific server(s) your team uses; the markdown stays generic. To change what a category points at, edit `.mcp.json` — not the skills.

## Connectors for this plugin

| Category | Placeholder | Included servers | Other options |
| --- | --- | --- | --- |
| Chat | `~~chat` | Slack | Microsoft Teams, Discord |
| Knowledge base | `~~knowledge base` | Notion, Guru | Confluence, Slab |
| Project tracker | `~~project tracker` | Atlassian (Jira/Confluence), Asana | Trello, Shortcut |
| Email | `~~email` | Microsoft 365, Gmail | Microsoft 365 |
| Calendar | `~~calendar` | Google Calendar | Microsoft 365 |

> Microsoft 365 spans email, docs, and calendar — it can cover more than one category on its own.

Every skill works with **zero connectors** (searching what you paste in, plus public web research where relevant). Each connector simply widens what a single query can reach: connect more sources, and unified search, digests, and synthesis cover more of your real work.
