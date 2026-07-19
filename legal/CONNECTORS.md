# Connectors — Legal

## How tool references work

This plugin is **tool-agnostic**. Skills never name a specific product; they refer to a tool by its **category** using a `~~category` placeholder — for example `~~document management`, `~~knowledge base`, `~~chat`, `~~e-signature`. The prose stays generic so any MCP server in that category works.

The plugin's `.mcp.json` is where specific servers are pinned. When a server in a given category is connected, the skill uses it; when nothing is connected, the skill falls back to what you paste into the chat. Swap the pinned servers in `.mcp.json` for your own — the markdown does not change, because it only ever refers to the category.

## Connectors for this plugin

| Category | Placeholder | Included servers | Other options |
| --- | --- | --- | --- |
| Document management | `~~document management` | Box, Egnyte | SharePoint, Dropbox |
| Knowledge base | `~~knowledge base` | Atlassian (Confluence) | Notion, Guru, Slab |
| Project tracker | `~~project tracker` | Atlassian (Jira) | Trello, Shortcut |
| Chat | `~~chat` | Slack | Microsoft Teams, Discord |
| E-signature | `~~e-signature` | DocuSign | Adobe Acrobat Sign |
| Email / docs | `~~email` | Microsoft 365, Gmail | Microsoft 365 covers mail, docs, calendar |
| Calendar | `~~calendar` | Google Calendar, Microsoft 365 | Microsoft 365 |

> Atlassian covers two categories: Confluence serves as the `~~knowledge base` (standard positions, negotiation notes) and Jira as the `~~project tracker` (remediation and matter tracking).

Every skill runs without any of these connected — paste the contract, NDA, policy, or clause text and Claude works from that. Connecting a server in a category simply lets the skill pull the authoritative, current source (playbook, standard NDA, policy text, clause library) automatically instead of relying on what is pasted in.
