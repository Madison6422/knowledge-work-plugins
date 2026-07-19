# Connectors

## How tool references work

This plugin's skills are **tool-agnostic**. They refer to tools by *category*
using a `~~placeholder` (for example `~~chat`, `~~knowledge base`, `~~CRM`)
rather than naming a specific product. The `.mcp.json` file pins the actual MCP
servers, but any server in the same category works — so a team on Salesforce and
a team on HubSpot can share the same skills.

To swap a tool: edit `.mcp.json`, replace the server for that category, and the
skills keep working unchanged.

## Connectors for this plugin

<!-- CUSTOMIZE: one row per category. Fill in from your .mcp.json. -->

| Category | Placeholder | Included servers | Other options |
|----------|-------------|------------------|---------------|
| Chat | `~~chat` | Slack | Microsoft Teams, Discord |
| Your category | `~~your-tool` | Your Tool | Alternative A, Alternative B |

> **No connectors?** The skills still work — you paste in context and Claude
> researches the rest. Connecting tools just lets Claude pull that context itself.
