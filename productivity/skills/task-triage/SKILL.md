---
name: task-triage
description: Gather open action items scattered across chat, email, and your project tracker, dedupe them, sort by urgency and importance, and propose a ranked to-do list with owners and due dates. Trigger with "triage my tasks", "what's on my plate", "pull together my action items".
---

# Task Triage

Turn scattered "can you…" messages into one clean, ranked list.

## What it does

Collects open action items from everywhere they hide — ~~chat threads, ~~email requests, and tickets in your ~~project tracker — then removes duplicates, sorts each by urgency and importance, and hands back a ranked to-do list with an owner and a due date on every line. You review and confirm before anything gets filed back.

With no tools connected, paste the messages and lists you want triaged and it does the same dedupe-and-rank pass.

## Connectors it uses

| Category | Placeholder | What it adds |
|---|---|---|
| Chat | `~~chat` | "Can you…" asks and follow-ups buried in threads |
| Email | `~~email` | Action items and requests sitting in your inbox |
| Project tracker | `~~project tracker` | Already-tracked tasks, their status and due dates |

> **No connectors?** Paste your threads, emails, and a task dump. Triage runs on whatever you give it — connectors just widen the net so nothing is missed.

## How it works

1. Gather. Collect open items from ~~chat, ~~email, and ~~project tracker over a chosen window (default: last 7 days). *Standalone:* use what you paste in.
2. Normalize each item to a single action: verb + object + who asked.
3. **Dedupe** — merge items that describe the same work across tools; keep the richest version and note where it came from.
4. **Prioritize** — score each on urgency (deadline pressure) and importance (impact), then sort into an urgent/important grid.
<!-- CUSTOMIZE: your urgency + importance definitions — e.g. "urgent = due <48h", "important = customer- or revenue-facing" -->
5. **Assign owner + due date** — default owner is you; flag items that belong to someone else as "delegate".
<!-- CUSTOMIZE: default owner, team members you can delegate to, and your standard SLA per priority tier -->
6. Propose the ranked list. Offer to file new or updated tasks into ~~project tracker — **you approve before anything is created or changed.**

## Output

```markdown
# Task Triage — {{date range}}

## Do first (urgent + important)
1. {{action}} — owner: you — due {{date}} — from ~~chat ({{person}})
2. {{action}} — owner: you — due {{date}} — from ~~email

## Schedule (important, not urgent)
- {{action}} — owner: you — due {{date}}

## Delegate (urgent, someone else)
- {{action}} — owner: {{name}} — from ~~project tracker

## Drop / clarify
- {{ambiguous item}} — needs scope before it can be ranked

_Duplicates merged: 3. Ready to file 4 items into ~~project tracker on your OK._
```

## Customize this skill

- Edit step 4 with your team's exact urgency and importance thresholds.
- Edit step 5 with default owners, who you can delegate to, and SLA per tier.
- Adjust the default gather window in step 1.
<!-- CUSTOMIZE: which ~~chat channels or ~~email labels to include or ignore during gather -->

## Related skills

- **daily-brief** — surfaces the top of this list each morning.
- **meeting-notes** — feeds fresh action items in from meetings.
- **weekly-review** — reviews what got done vs. what slipped.
