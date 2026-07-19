# Connectors — Marketing

## How tool references work

This plugin is **tool-agnostic**. Skills never name a specific product — they refer to a tool by its *category* using a `~~placeholder`, like `~~knowledge base` or `~~seo`. The `.mcp.json` file pins the specific MCP servers your team actually uses; the prose stays generic, so any server in a given category works.

That means you can swap the underlying tool (say, from one SEO platform to another) by editing `.mcp.json` only — the skills keep working, because they only care about the *category*. Every skill also works with **no connectors at all**, using what you paste in plus web research; connectors just remove copy-paste and add live data.

## Connectors for this plugin

| Category | Placeholder | Included servers | Other options |
| --- | --- | --- | --- |
| Knowledge base | `~~knowledge base` | Notion | Confluence, Guru, Slab |
| Design / creative | `~~design` | Canva, Figma | Sketch, Adobe XD, Adobe Express |
| CRM | `~~CRM` | HubSpot | Salesforce, Pipedrive, Copper |
| Product analytics | `~~product analytics` | Amplitude | Mixpanel, Heap, Pendo |
| SEO | `~~seo` | Ahrefs | Semrush, Moz |
| Competitive intelligence | `~~competitive intelligence` | Similarweb | Crayon, Klue |
| Email marketing | `~~email marketing` | Klaviyo | Mailchimp, Braze |
| Marketing analytics | `~~marketing analytics` | Supermetrics | Funnel, Adverity |
| Chat | `~~chat` | Slack | Microsoft Teams, Discord |
| Email | `~~email` | Gmail | Microsoft 365 |
| Calendar | `~~calendar` | Google Calendar | Microsoft 365 |

> **Note:** Some skills also reference `~~project tracker` (e.g. `campaign-plan`). No project-tracker server is pinned in `.mcp.json` yet — add one (Asana, Linear, Monday, ClickUp, Jira, Trello, Shortcut) to turn campaign plans into owned, dated tasks. Until then, those steps run standalone.
