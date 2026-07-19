---
description: Scaffold a new plugin for this marketplace from the template.
argument-hint: "[role or workflow the plugin is for]"
---

# Create Plugin

Runs the **create-plugin** skill to scaffold a new plugin end to end.

## Instructions
1. Read `$ARGUMENTS` as the role or workflow the plugin is for (e.g. "RevOps", "recruiting coordinator"). If empty, ask what it should serve.
2. Invoke the **create-plugin** skill and follow its steps: scope the jobs and tool categories, pick a kebab-case name, copy `_template/`, and draft `plugin.json`, the `SKILL.md` files, the commands, and `.mcp.json`.
3. Produce the marketplace.json entry and the file contents for the user to paste in — do not edit any `.json` file for them unless asked.
4. Finish by suggesting they run `/plugin-management:add-connector` for each tool category and the **plugin-audit** skill before shipping.
