---
name: connector-setup
description: Set up a plugin's .mcp.json — add, swap, or remove an MCP server for a tool category, wire up the type/url/oauth shape, choose OAuth vs. token auth, and leave a server as an editable placeholder with an empty url. Explains how ~~category placeholders map to real servers. Trigger with "add a connector", "swap our CRM to [tool]", "set up the MCP server for [category]", "how does .mcp.json work".
---

# Connector Setup

Wire a plugin's `~~category` placeholders to real MCP servers — or leave them as blanks the team fills in later.

## What it does
Explains and edits a plugin's `.mcp.json`: how the file maps each connected tool to a server, how to add or swap a server for a category, the `type: http` + `url` shape, when to use OAuth vs. a token, and how to leave a server as an editable placeholder with an empty `url`. Skills stay tool-agnostic (`~~category`); `.mcp.json` is where the specific server gets pinned. It works entirely on local files — nothing is connected during setup.

## Connectors it uses
None — this plugin edits files, it doesn't connect to external tools.

> **No connectors?** Right — this skill *produces* connector config, it doesn't use any. Claude drafts the JSON; you paste it into `.mcp.json` and complete any credentials.

## How `.mcp.json` works
- The file has one object, `mcpServers`, keyed by a short server name (e.g. `slack`, `hubspot`).
- Skills never name a product — they say `~~chat`, `~~CRM`. `.mcp.json` decides which server sits behind each category.
- To **swap** a tool, replace the server object for that category; the skill prose doesn't change.
- Each server is `type: http` with a `url`. Servers needing user login also carry an `oauth` block; simpler ones use a token the user supplies on connect.

## Server shapes
OAuth server (user logs in through the tool):
```json
"slack": {
  "type": "http",
  "url": "https://mcp.slack.com/mcp",
  "oauth": {
    "clientId": "<client-id>",
    "callbackPort": 3118
  }
}
```

Token / simple HTTP server (no `oauth` block; user pastes a token on connect):
```json
"hubspot": {
  "type": "http",
  "url": "https://mcp.hubspot.com/anthropic"
}
```

Editable placeholder (empty `url` — the category is declared but the team must fill it in):
```json
"gmail": {
  "type": "http",
  "url": ""
}
```

## How it works
1. **Identify the category.** Which `~~category` are you wiring — `~~CRM`, `~~chat`, `~~data warehouse`? Confirm the skills already reference it.
2. **Pick the server.** Choose the MCP server for that category. If you don't have the URL yet, leave a placeholder (empty `url`).
<!-- CUSTOMIZE: your company's standard tool per category (e.g. ~~CRM = Salesforce) -->
3. **Choose auth.** OAuth for tools with a login flow (add the `oauth` block with `clientId` and `callbackPort`); token/simple HTTP otherwise (just `type` + `url`).
<!-- CUSTOMIZE: whether your org uses OAuth or service tokens for shared tools -->
4. **Add or swap.** Insert the server object under `mcpServers`, or replace the existing one for that category. Keep the key short and lowercase.
5. **Leave blanks intentionally.** For any tool not yet provisioned, set `url` to `""` so the entry is visible but clearly incomplete.
6. **Confirm the mapping.** Note which server now backs each `~~category` so the plugin's `CONNECTORS.md` table stays accurate.
<!-- CUSTOMIZE: keep your CONNECTORS.md category→server table in sync after each change -->

## Output
```markdown
# Connector change: <plugin>

**Category:** ~~<category>
**Action:** add | swap | placeholder
**Server:** <name> → <url or "(placeholder — url empty)">
**Auth:** OAuth | token

## .mcp.json snippet to paste
<json server object>

## Follow-ups
- [ ] Fill url / credentials for <server>
- [ ] Update CONNECTORS.md row for ~~<category>
```

## Customize this skill
- Record your default server per category in step 2 so swaps are one step.
<!-- CUSTOMIZE: your preferred auth method and any callbackPort conventions -->
- Note any self-hosted MCP URLs your team uses.

## Related skills
- **create-plugin** — sets up `.mcp.json` for the first time on a new plugin.
- **customize-plugin** — adjusts skill prose; leave `~~category` placeholders to this skill.
- **plugin-audit** — checks `.mcp.json` validity and that categories line up with the skills.
