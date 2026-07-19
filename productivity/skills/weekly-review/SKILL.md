---
name: weekly-review
description: End-of-week roll-up — what shipped, what slipped, next week's priorities, and anything waiting on someone else. Pulls from your project tracker, chat, and email. Trigger with "run my weekly review", "what did I get done this week", "wrap up the week".
---

# Weekly Review

A Friday roll-up that closes the loop on the week and sets up the next.

## What it does

Summarizes the week in four parts: what shipped, what slipped, next week's priorities, and anything you're waiting on from other people. It reads across your ~~project tracker, ~~chat, and ~~email to reconstruct the week, then hands back a review you can keep or share with your team.

With no tools connected it still works: paste your task list, a few threads, and your calendar, and it builds the same roll-up.

## Connectors it uses

| Category | Placeholder | What it adds |
|---|---|---|
| Project tracker | `~~project tracker` | What moved to done, what's still open, and due-date slips |
| Chat | `~~chat` | Threads where you're blocked or waiting on a reply |
| Email | `~~email` | Outstanding requests and unanswered asks from the week |

> **No connectors?** Paste your completed and open tasks plus a few threads. The review is assembled from what you provide — connectors just make the recall complete.

## How it works

1. Set the window. Default is the current week (Mon–Fri); accept a custom range.
<!-- CUSTOMIZE: your week boundaries and timezone — e.g. Sun–Sat, or a sprint boundary -->
2. **Shipped** — from ~~project tracker, list tasks completed this week; add notable wins mentioned in ~~chat. *Standalone:* use your pasted done list.
3. **Slipped** — items that were due this week but aren't done; note how far behind and why if known.
4. **Waiting on others** — asks in ~~email and ~~chat that are still open, with who owes what.
5. **Next week's priorities** — pull the top items due or starting next week and rank them.
<!-- CUSTOMIZE: how many priorities to surface (e.g. top 3) and how your team ranks them -->
6. Draft the review in the shape below. Offer to post it to ~~chat or file follow-ups into ~~project tracker — **you approve before anything is shared or created.**

## Output

```markdown
# Weekly Review — week of {{date}}

## Shipped ✅
- {{task}} — {{project tracker}}
- {{win}} — noted in ~~chat

## Slipped ⏳
- {{task}} — 2 days behind — {{reason}}

## Waiting on others
- {{name}} owes {{thing}} — asked {{when}}, via ~~email

## Next week — top priorities
1. {{item}} — due {{date}}
2. {{item}}
```

## Customize this skill

- Set your week boundaries and timezone in step 1.
- Choose how many next-week priorities to surface in step 5.
- Adjust the output sections — some teams add "learnings" or a metric line.
<!-- CUSTOMIZE: default ~~chat channel for posting the review to your team -->

## Related skills

- **daily-brief** — the daily counterpart; next-week priorities feed Monday's brief.
- **task-triage** — clears the backlog the review surfaces.
- **personal-memory** — a good moment to prune stale facts and record the week's decisions.
