# Connectors — Product Management

## How tool references work
These skills are **tool-agnostic**. In the prose, tools are referred to by *category* using a `~~placeholder` — like `~~project tracker` or `~~knowledge base` — never a specific product. The plugin's `.mcp.json` pins specific MCP servers, but the skills stay generic, so **any MCP server in a given category works**. Swap the pinned server for another in the same category and the skills keep working — no prose changes needed.

Every skill also runs **standalone**: with no connectors, it uses what you paste in plus web research where relevant. Connectors just widen the evidence and pull status live.

## Connectors for this plugin
| Category | Placeholder | Included servers | Other options |
|----------|-------------|------------------|---------------|
| Project tracker | `~~project tracker` | Linear, Asana, monday, ClickUp, Atlassian (Jira/Confluence) | Trello, Shortcut |
| Knowledge base | `~~knowledge base` | Notion | Confluence, Slab, Guru |
| Design | `~~design` | Figma | Sketch, Adobe XD |
| Product analytics | `~~product analytics` | Amplitude, Pendo | Mixpanel, Heap |
| Helpdesk | `~~helpdesk` | Intercom | Zendesk, Front, Gorgias |
| Conversation intelligence | `~~conversation intelligence` | Fireflies | Gong, Chorus, Otter.ai |
| Competitive intelligence | `~~competitive intelligence` | Similarweb | Crayon, Klue |
| Chat | `~~chat` | Slack | Microsoft Teams, Discord |
| Email | `~~email` | Gmail | Microsoft 365 |
| Calendar | `~~calendar` | Google Calendar | Microsoft 365 |
