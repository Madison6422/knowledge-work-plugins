---
name: pipeline-review
description: Review your open opportunities — stage, next step, and risk flags like stalled deals, single-threaded relationships, or no next meeting booked — then get a prioritized action list. Pulls live deal data from your CRM when connected. Trigger with "review my pipeline", "what deals need attention", "pipeline review for my deals".
---

# Pipeline Review

Scan your open deals, surface the risks, and get a ranked list of what to do next.

## What it does
Looks across your open opportunities and flags the ones that need attention — deals that have stalled, are single-threaded, have no next meeting booked, or are slipping their close date. It then hands you a prioritized action list so you know exactly what to work first. Runs on live CRM data when connected, or on a list you paste in.

## Connectors it uses
| Category | Placeholder | What it adds |
| --- | --- | --- |
| CRM | `~~CRM` | Live open deals — stage, amount, close date, last activity, contacts |

> **No connectors?** Paste an export or a quick list of your deals (stage, amount, last touch) and Claude runs the same review and flags. Connecting `~~CRM` just means it pulls the data itself and stays current.

## How it works
1. Load open opportunities from `~~CRM`, or from the list you paste in.
2. Scope to what you asked for — your deals, a rep, or a segment.
3. **Apply risk flags** to each deal:
   <!-- CUSTOMIZE: set your risk thresholds — e.g. "stalled" = no activity in 14 days -->
   - **Stalled** — no activity in your threshold window.
   - **Single-threaded** — only one contact engaged.
   - **No next step** — no future meeting or task booked.
   - **Date slip** — close date in the past or repeatedly pushed.
4. **Prioritize:** rank by amount, stage, and risk so the highest-leverage actions come first.
5. Output a table plus a short, ordered action list.
<!-- CUSTOMIZE: set your stage names and what "priority" means for your team -->

## Output
```markdown
# Pipeline Review — <scope> — <date>
**Open deals:** <n> · **At risk:** <n> · **Total value:** <amount>

## Deals
| Deal | Stage | Amount | Next step | Flags |
| --- | --- | --- | --- | --- |

## Do this first
1. <deal> — <specific action> — <why now>
2. ...
```

## Customize this skill
- Set risk thresholds and stage names under step 3.
<!-- CUSTOMIZE: add your own flags (e.g. no economic buyer, no mutual action plan) -->
- Define how deals are prioritized (amount, stage weight, close date).
- Note which segments or reps this should default to.

## Related skills
- **call-prep** — prep the calls this review tells you to book.
- **draft-outreach** — re-engage stalled or single-threaded deals.
- **account-research** — go deeper on a key account that's slipping.
