---
name: daily-brief
description: Assemble a short morning brief for the day — calendar, top priorities, overdue tasks, unread items that need a reply, and one suggested focus. Works from what you paste in, or pulls live from your connected tools. Trigger with "plan my day", "what's my morning brief", "what should I focus on today".
---

# Daily Brief

A one-screen morning brief so you start the day knowing what matters.

## What it does

Pulls together today's meetings, your top priorities, anything overdue, and unread messages that are actually waiting on you — then names one suggested focus for the day. It reads across your ~~calendar, ~~email, ~~chat, and ~~project tracker so you don't have to open four apps before your first coffee.

With no tools connected it still works: paste your calendar, a task list, or a few threads and it will shape them into the same brief.

## Connectors it uses

| Category | Placeholder | What it adds |
|---|---|---|
| Calendar | `~~calendar` | Today's meetings, times, and gaps for focus blocks |
| Email | `~~email` | Unread messages that need a reply from you |
| Chat | `~~chat` | Direct mentions and threads waiting on your response |
| Project tracker | `~~project tracker` | Your assigned tasks, due dates, and overdue items |

> **No connectors?** Paste in your agenda, task list, or a few message threads. The brief is assembled from whatever you provide — the connectors just make it automatic and complete.

## How it works

1. Set the day. Default is today; accept an optional date or focus theme.
2. **Calendar** — from ~~calendar, list today's meetings with times; flag back-to-backs and note the largest free block. *Standalone:* use the agenda you paste in.
3. **Priorities & overdue** — from ~~project tracker, pull tasks assigned to you due today or already overdue. *Standalone:* use your pasted task list.
4. **Needs a reply** — scan ~~email and ~~chat for unread items that are directed at you and awaiting a response. Skip FYIs and newsletters.
<!-- CUSTOMIZE: what counts as "needs a reply" vs noise — e.g. only direct mentions, only from your team, ignore specific channels -->
5. **Suggested focus** — pick the single highest-leverage thing to protect time for today, and suggest which free block to use.
<!-- CUSTOMIZE: how your team defines "high-leverage" — revenue, launch-blocking, exec-facing, etc. -->
6. Output the brief. Keep it to one screen; link or reference items rather than quoting them in full.

## Output

```markdown
# Morning Brief — {{date}}

**Suggested focus:** {{one sentence}} — protect {{free block, e.g. 9:30–11:00}}.

## Calendar
- 9:00 Standup (15m)
- 13:00 Roadmap review (60m) — back-to-back with 14:00
- Largest free block: 9:30–11:00

## Top priorities
1. {{task}} — due today — {{project tracker}}
2. {{task}} — due today

## Overdue
- {{task}} — 2 days late — {{project tracker}}

## Needs a reply
- {{person}} in ~~chat — asked for the deck by EOD
- {{person}} in ~~email — waiting on your sign-off
```

## Customize this skill

- Edit step 4 to define what "needs a reply" means for you — direct mentions only, specific channels, VIP senders.
- Edit step 5 to match how your team ranks importance.
- Adjust the output template to add or drop sections (some teams want a "waiting on others" line).
<!-- CUSTOMIZE: add a standing section your team always wants, e.g. on-call status or key metric -->

## Related skills

- **task-triage** — build the ranked to-do list the priorities section draws from.
- **weekly-review** — the Friday counterpart to this daily view.
- **personal-memory** — supplies context on your projects and people so the brief is smarter.
