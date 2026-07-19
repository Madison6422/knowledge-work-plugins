---
name: example-skill
description: One to three sentences describing what this skill does and when Claude should use it. The last sentence lists the phrases that trigger it. Trigger with "example phrase", "another way a user might ask", "do the thing for [X]".
---

# Example Skill

<!-- CUSTOMIZE: replace everything below with your real workflow. This file is a shape to fill in, not a finished skill. -->

One-line summary of what the user gets when this skill runs.

## What it does

Two to four sentences of prose describing the outcome. Explain the value in
plain terms — what the user hands over, and what they get back.

## Connectors it uses

| Category | Placeholder | What it adds |
|----------|-------------|--------------|
| Chat | `~~chat` | Pulls relevant discussion so Claude has context |
| Knowledge base | `~~knowledge base` | Grounds the output in your team's docs |

> **No connectors?** Paste in the context you have and Claude works from that
> plus web research where relevant.

## How it works

1. **Gather context.** If tools are connected, pull from `~~chat` and
   `~~knowledge base`. If not, ask the user for what's needed.
2. **Do the work.** <!-- CUSTOMIZE: the actual steps your team follows -->
3. **Check it.** Re-verify any numbers, names, or claims before presenting.
4. **Deliver** in the format below. <!-- CUSTOMIZE: add an approval step here if this touches money, customers, or external sends -->

## Output

```markdown
# [Deliverable title]

**Summary:** [the headline]

## Section
- [point]
- [point]

## Next steps
1. [action]
```

## Customize this skill

- Replace the steps in **How it works** with your team's real process.
- Edit the **Output** block to match the format your team expects.
- Update the trigger phrases in the frontmatter `description` to match how your
  team actually asks for this.

## Related skills

- `another-skill` — what it does and when to use it instead.
