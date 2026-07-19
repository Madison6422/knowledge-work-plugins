# Connectors

## How tool references work
This plugin is **tool-agnostic**. Skills never name a specific product — they refer to a tool by *category* using a `~~placeholder`, like `~~CRM` or `~~data enrichment`. The `.mcp.json` file pins specific MCP servers, but the prose stays generic so **any** server in that category works. Swap the servers in `.mcp.json` for the ones your team uses and the skills keep working unchanged.

Every skill also runs **standalone** — with zero connectors it uses what you paste in plus web research. Connectors just make it faster and more accurate.

## Connectors for this plugin
| Category | Placeholder | Included servers | Other options |
| --- | --- | --- | --- |
| CRM | `~~CRM` | HubSpot, Close | Salesforce, Pipedrive, Copper |
| Data enrichment | `~~data enrichment` | Clay, ZoomInfo, Apollo | Clearbit, Lusha |
| Sales engagement | `~~sales engagement` | Outreach | Salesloft, Apollo sequences |
| Conversation intelligence | `~~conversation intelligence` | Fireflies | Gong, Chorus, Otter.ai |
| Competitive intelligence | `~~competitive intelligence` | Similarweb | Crayon, Klue |
| Knowledge base | `~~knowledge base` | Notion | Confluence, Slab, Guru |
| Project tracker | `~~project tracker` | Atlassian (Jira / Confluence) | Trello, Shortcut |
| Chat | `~~chat` | Slack | Microsoft Teams, Discord |
| Email / docs / calendar | `~~email` | Microsoft 365, Gmail | Microsoft 365 covers mail, docs, and calendar |
| Calendar | `~~calendar` | Google Calendar | Microsoft 365 |
