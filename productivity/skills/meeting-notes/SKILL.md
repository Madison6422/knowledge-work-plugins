---
name: meeting-notes
description: Turn raw notes or a transcript into clean minutes — decisions, action items with owners and due dates, and open questions — then offer to file the tasks into your project tracker. Trigger with "clean up these meeting notes", "turn this transcript into minutes", "what were the action items".
---

# Meeting Notes

From messy notes to shareable minutes in one pass.

## What it does

Takes raw notes or a transcript and produces clean minutes: the decisions made, the action items (each with an owner and a due date), and the open questions left hanging. It then offers to file the action items as tasks in your ~~project tracker — you approve before anything is created.

It works entirely from text you paste, so it needs no connectors at all. A ~~project tracker connection just lets it turn action items into real tickets in one step.

## Connectors it uses

| Category | Placeholder | What it adds |
|---|---|---|
| Project tracker | `~~project tracker` | Files action items as tasks with owner + due date |
| Chat | `~~chat` | Optionally posts the minutes to the relevant channel |

> **No connectors?** Paste your notes or transcript. The minutes are generated from the text alone — connectors only help with filing and sharing afterward.

## How it works

1. Take the input: pasted notes, a transcript, or a doc link. Note the meeting title, date, and attendees if present.
2. **Extract decisions** — capture what was actually decided, not the discussion around it. One line each.
3. **Extract action items** — for each, record the action, an owner, and a due date. If owner or date is missing, mark it `TBD` rather than guessing.
<!-- CUSTOMIZE: how your team assigns owners and default due dates, e.g. "unassigned action items default to the meeting organizer, due in 1 week" -->
4. **Extract open questions** — unresolved items and anything explicitly parked.
5. Draft the minutes in the output shape below. Keep decisions and actions crisp.
<!-- CUSTOMIZE: your minutes template or required fields — e.g. a "risks" section, a project code, a distribution list -->
6. Offer to file. On your OK, create the action items in ~~project tracker and optionally post the minutes to ~~chat. **You approve before tasks are created or anything is shared externally.**

## Output

```markdown
# {{Meeting title}} — {{date}}
Attendees: {{names}}

## Decisions
- {{decision}}
- {{decision}}

## Action items
| Action | Owner | Due |
|---|---|---|
| {{action}} | {{name}} | {{date}} |
| {{action}} | TBD | TBD |

## Open questions
- {{question}}

_Ready to file 2 action items into ~~project tracker on your OK._
```

## Customize this skill

- Edit step 3 for how owners and default due dates are assigned.
- Edit step 5 to match your team's minutes template and required fields.
- Decide in step 6 whether filing to ~~project tracker should be one-click or always confirmed item-by-item.
<!-- CUSTOMIZE: default ~~project tracker project/board and ~~chat channel for posting minutes -->

## Related skills

- **task-triage** — dedupe and rank the action items this produces against the rest of your plate.
- **daily-brief** — new due-dated actions show up in tomorrow's brief.
- **personal-memory** — record durable decisions and people mentioned here.
