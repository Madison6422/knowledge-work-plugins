# Connectors

## How tool references work

This plugin is **tool-agnostic**. Skills never name a specific product — they refer to tools by *category* using a `~~placeholder`, like `~~calendar`, `~~email`, `~~chat`, or `~~project tracker`.

The `.mcp.json` file pins specific MCP servers for each category, but the prose stays generic on purpose: **any MCP server in a category works.** If your team uses a different tracker or chat tool, swap the server in `.mcp.json` and the skills keep working unchanged — no prose edits required.

Every skill also runs **standalone**. With nothing connected, paste in your agenda, task list, or a few threads and the skill does the same job on what you provide.

## Connectors for this plugin

| Category | Placeholder | Included servers | Other options |
|---|---|---|---|
| Chat | `~~chat` | Slack | Microsoft Teams, Discord |
| Email | `~~email` | Gmail, Microsoft 365 | Microsoft 365 (covers mail, docs, calendar) |
| Calendar | `~~calendar` | Google Calendar, Microsoft 365 | Microsoft 365 |
| Project tracker | `~~project tracker` | Asana, Linear, Atlassian (Jira), Monday, ClickUp | Trello, Shortcut |
| Knowledge base | `~~knowledge base` | Notion | Confluence, Slab |

Microsoft 365 spans email, docs, and calendar, so it appears under both `~~email` and `~~calendar` — connect it once and it serves both categories.
