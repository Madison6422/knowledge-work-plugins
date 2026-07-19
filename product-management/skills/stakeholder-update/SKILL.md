---
name: stakeholder-update
description: Writes a concise stakeholder update — what shipped, what's next, risks, and asks — tailored in tone for an exec or team audience. Pulls status from your project tracker and chat. Trigger with "write a stakeholder update", "draft this week's update", "summarize progress for execs".
---

# Stakeholder Update
Draft a crisp update that says what shipped, what's next, what's at risk, and what you need — sized to the reader.

## What it does
Pulls recent progress from your tracker and team channels and shapes it into a short, skimmable update. It adjusts tone and depth for the audience — outcomes and asks for execs, more detail and context for the team — and always separates facts (what shipped) from forecasts (what's next) so nobody over-reads a plan as a promise.

## Connectors it uses
| Category | Placeholder | What it adds |
| --- | --- | --- |
| Project tracker | `~~project tracker` | Completed, in-progress, and blocked items so status is accurate, not from memory |
| Chat | `~~chat` | Recent decisions and callouts from team channels to catch what didn't make it to tickets |

> **No connectors?** Paste your progress notes, shipped items, and blockers. The skill still structures the update and tailors the tone — connectors just save you from assembling the status by hand.

## How it works
1. Set the **audience** (exec vs. team) and the period covered.
<!-- CUSTOMIZE: define your audiences and how much detail each wants -->
2. Pull status from `~~project tracker` (done / in-progress / blocked) and scan `~~chat` for decisions and risks. Standalone: use pasted notes.
3. Write **What shipped** — outcomes, not activity.
4. Write **What's next** — clearly flagged as plan, with confidence where useful.
5. Call out **Risks** and the specific **Asks** you need from readers.
<!-- CUSTOMIZE: set your risk labels — e.g. On track / At risk / Off track -->
6. Tune tone: tighter and outcome-first for execs, more context for the team.

> **You approve before it goes out.** This skill drafts the update. Review it, adjust the framing, and you send it — nothing is posted or emailed automatically.

## Output
```markdown
# [Team/Product] update — [period]
**Audience:** [exec / team]

## What shipped
- [Outcome, with impact]

## What's next
- [Plan] — [On track / At risk]

## Risks
- [Risk and mitigation]

## Asks
- [Specific decision or help needed, from whom, by when]
```

## Customize this skill
- Define your **audiences** and the detail level each expects.
- Set your **risk labels** (On track / At risk / Off track) for consistency.
- Add a **cadence and distribution list** note if updates go out on a schedule.

## Related skills
- `roadmap-plan` — the source of "what's next" when plans shift.
- `write-spec` — link the spec when announcing a new initiative.
- `research-synthesis` — cite user evidence behind a risk or a bet.
