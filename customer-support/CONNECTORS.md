# Connectors — Customer Support

## How tool references work

These skills are **tool-agnostic**. In the prose, tools are referred to by *category* using a `~~placeholder` — for example `~~helpdesk`, `~~knowledge base`, or `~~CRM` — never by a specific product name.

The plugin's `.mcp.json` pins the specific MCP servers your team has connected. The markdown stays generic so that **any** server in a category works: swap Intercom for Zendesk, or Notion for Confluence, and the skills read exactly the same. When you customize a skill, keep the `~~category` language and let `.mcp.json` decide the actual product.

If your team uses a tool in a category not listed below, connect it in `.mcp.json` and it will slot into the matching `~~placeholder` automatically.

## Connectors for this plugin

| Category | Placeholder | Included servers | Other options |
| --- | --- | --- | --- |
| Helpdesk | `~~helpdesk` | Intercom | Zendesk, Front, Gorgias |
| Knowledge base | `~~knowledge base` | Guru, Notion | Confluence, Slab |
| CRM | `~~CRM` | HubSpot | Salesforce, Pipedrive, Copper |
| Project tracker | `~~project tracker` | Atlassian (Jira) | Trello, Shortcut, Linear |
| Chat | `~~chat` | Slack | Microsoft Teams, Discord |
| Email | `~~email` | Microsoft 365, Gmail | Microsoft 365 also covers docs + calendar |
