---
description: Build or update a product roadmap grouped by theme and quarter.
argument-hint: "[optional: quarter or theme]"
---

# Roadmap
Runs the `roadmap-plan` skill to build or update a prioritized, theme-based roadmap.

## Instructions
1. Read `$ARGUMENTS` for an optional focus — a specific quarter or theme. If empty, build the full roadmap.
2. Run the **roadmap-plan** skill: gather initiatives, group by theme, score effort vs. impact, and place items in quarters.
3. Pull live status and estimates from `~~project tracker` when connected; otherwise use the initiative list the user provides.
4. Flag dependencies and any quarter where planned effort exceeds capacity.
5. Return the roadmap with a short rationale and the open sequencing decisions to review.
