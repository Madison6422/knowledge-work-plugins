---
description: Review open opportunities — stage, next step, risk flags, and a prioritized action list.
argument-hint: "[optional: rep, segment, or 'my deals']"
---

# Pipeline Review

Runs the **pipeline-review** skill to scan open deals and rank what to work next.

## Instructions
1. Read `$ARGUMENTS` for scope — a rep, a segment, or `my deals`. If empty, default to the current user's open deals.
2. Invoke the **pipeline-review** skill with that scope.
3. Let it pull open opportunities from `~~CRM` (or a pasted list), apply risk flags, and prioritize.
4. Return the deal table and the ordered "do this first" action list.
