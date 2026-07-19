---
name: roadmap-plan
description: Builds or updates a product roadmap — groups initiatives by theme and quarter, weighs effort against impact, and flags dependencies and capacity risks. Reads live status from your project tracker. Trigger with "plan the roadmap", "build a Q[n] roadmap", "update our roadmap", "what should we prioritize next quarter".
---

# Roadmap Plan
Turn a pile of initiatives into a prioritized, theme-based roadmap with the risks called out.

## What it does
Takes your candidate initiatives — from a list you paste or straight from your tracker — and organizes them into a roadmap grouped by theme and quarter. It scores effort versus impact, surfaces dependencies between items, and flags where planned work exceeds team capacity so you can cut or resequence before committing.

## Connectors it uses
| Category | Placeholder | What it adds |
| --- | --- | --- |
| Project tracker | `~~project tracker` | Live initiative status, estimates, owners, and existing epics so the roadmap reflects reality |

> **No connectors?** Paste your initiative list with rough effort and impact for each. The skill groups, scores, and sequences from that — you just supply the raw inputs instead of pulling them live.

## How it works
1. Gather initiatives: pull open epics and their estimates from `~~project tracker`, or use the list you paste in.
2. Group into **themes** so the roadmap tells a story, not just a backlog dump.
<!-- CUSTOMIZE: name your standing themes — e.g. Growth, Retention, Platform, Trust -->
3. Score each initiative on **effort vs. impact** and place it in a quarter.
<!-- CUSTOMIZE: set your scoring model — T-shirt sizes, RICE, or story points -->
4. Map **dependencies** — flag anything blocked by or blocking another item.
5. Check **capacity**: compare planned effort per quarter against team throughput and flag overloads.
<!-- CUSTOMIZE: set team capacity per quarter (people, sprints, or points) -->
6. Present the roadmap with a short rationale and the risks to review.

## Output
```markdown
# Roadmap — [timeframe]

## Theme: [Theme name]
| Initiative | Quarter | Effort | Impact | Depends on | Notes |
|------------|---------|--------|--------|------------|-------|
| [Name] | Q3 | M | High | [item] | [rationale] |

## Capacity check
- **Q3:** [planned] vs. [capacity] — ⚠️ over / ✅ ok

## Risks & dependencies
- [Dependency or capacity risk and suggested mitigation]

## Open decisions
- [ ] [Sequencing or scope call needing sign-off]
```

## Customize this skill
- Name your **standing themes** so grouping is consistent quarter to quarter.
- Set your **scoring model** (T-shirt, RICE, points) in step 3.
- Enter **team capacity per quarter** so overloads are flagged against real numbers.

## Related skills
- `write-spec` — flesh out an initiative once it's slotted into a quarter.
- `stakeholder-update` — communicate roadmap changes to the team and execs.
- `research-synthesis` — bring user evidence into impact scoring.
