---
description: Adapt an existing plugin to your company's terms, workflows, and formats.
argument-hint: "[plugin name]"
---

# Customize Plugin

Runs the **customize-plugin** skill to tailor an existing plugin without breaking its structure.

## Instructions
1. Read `$ARGUMENTS` as the plugin to customize (e.g. "sales"). If empty, list the plugins in the marketplace and ask which one.
2. Invoke the **customize-plugin** skill: list the plugin's skills, collect every `<!-- CUSTOMIZE -->` marker, and gather the company specifics each one needs.
3. Edit the marked spots in place — terminology, trigger phrases, and output templates — keeping frontmatter, section order, and `~~category` placeholders intact.
4. Report which markers were filled and which still need a decision, then suggest running the **plugin-audit** skill.
