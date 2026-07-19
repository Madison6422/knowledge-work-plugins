---
name: personal-memory
description: Maintain a durable memory file of your projects, people, preferences, and recurring context so Claude stops re-asking the same questions. Read it at session start; append new facts on request. Trigger with "remember that…", "load my context", "what do you know about my work".
---

# Personal Memory

A single file that holds the context Claude keeps needing — so you stop repeating yourself.

## What it does

Keeps a durable, plain-markdown memory of your active projects, the people you work with, your preferences, and recurring context (tools, cadences, standing goals). Claude reads it at the start of a session to ground its answers, and appends new facts whenever you ask it to remember something. You stay in control: nothing is written without your say-so.

This skill is fully standalone — the memory lives in a local markdown file and needs no connectors. Connected tools just make it easier to seed and verify facts.

## Connectors it uses

| Category | Placeholder | What it adds |
|---|---|---|
| Project tracker | `~~project tracker` | Seed project names, owners, and status when first building memory |
| Chat | `~~chat` | Confirm who's who and which teams own what |

> **No connectors?** This skill doesn't need any. The memory file is the source of truth; connectors only help populate it faster the first time.

## How it works

1. **Locate the memory file.** Default path below. If it doesn't exist, offer to create it.
<!-- CUSTOMIZE: memory file location — e.g. ~/claude-memory.md or a shared team path -->
2. **Read at session start.** Load the file and use it as background context; don't re-ask for things already recorded.
3. **Append on request.** When you say "remember that…", add a single dated bullet under the right section. Keep facts atomic and short.
4. **Deduplicate & update.** If a new fact contradicts an old one, update in place and note it changed rather than keeping both.
<!-- CUSTOMIZE: which sections you want — Projects, People, Preferences, Recurring context, Goals, Glossary -->
5. **Never store secrets.** Skip passwords, tokens, and sensitive personal data. Keep it to working context.
<!-- CUSTOMIZE: your rules on what must never be written to memory (e.g. customer PII, financials) -->
6. **Confirm writes.** Echo back what was added so you can catch mistakes early.

## Output

```markdown
# Personal Memory — {{your name}}
_Last updated: {{date}}_

## Projects
- **{{project}}** — goal: {{…}} — status: {{…}} — tracked in ~~project tracker

## People
- **{{name}}** — {{role}} — works on {{project}}; prefers {{channel}}

## Preferences
- Brief style: bullets over prose; times in {{timezone}}

## Recurring context
- Weekly review on Fridays; standup 9:00

## Glossary
- **{{term}}** — {{what it means here}}
```

## Customize this skill

- Set the memory file path in step 1.
- Choose your section headers in step 4 to match how you think about your work.
- Tighten the "never store" rules in step 5 for your company's data policy.
<!-- CUSTOMIZE: a short review cadence — e.g. prune stale facts monthly -->

## Related skills

- **daily-brief** — reads this memory to make the morning brief sharper.
- **meeting-notes** — durable decisions and new people can be appended here.
- **weekly-review** — a natural moment to prune and refresh memory.
