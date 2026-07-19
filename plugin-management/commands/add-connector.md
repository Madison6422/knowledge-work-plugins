---
description: Add or swap an MCP server for a tool category in a plugin's .mcp.json.
argument-hint: "[tool or category]"
---

# Add Connector

Runs the **connector-setup** skill to add, swap, or placeholder an MCP server.

## Instructions
1. Read `$ARGUMENTS` as the tool or category to wire up (e.g. "Salesforce", "~~CRM", "chat"). If empty, ask which category and which plugin.
2. Invoke the **connector-setup** skill: confirm the `~~category` the skills use, pick the server, and choose OAuth vs. token.
3. Produce the `.mcp.json` server object in the `type: http` + `url` shape — use an empty `url` when the team hasn't provisioned the tool yet. Do not edit the `.json` file for them unless asked.
4. Note which server now backs the category so `CONNECTORS.md` can be kept in sync.
