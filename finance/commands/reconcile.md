---
description: Reconcile an account against its source and propose adjustments for approval
argument-hint: "[account + period]"
---

# Reconcile

Runs the `reconciliation` skill to match an account against its source and surface exceptions.

## Instructions

1. Read `$ARGUMENTS` for the account (bank, AP, AR, or a GL code) and the period to reconcile.
2. Run the `reconciliation` skill. Pull both sides from `~~data warehouse` if connected; otherwise ask the user to paste the account activity and the source statement.
3. Match items, then list unmatched, timing, and aged items with their balance impact.
4. Propose adjusting entries where the fix is clear, and recompute the reconciled balance so it ties to the source.
5. Present the reconciliation and proposed adjustments for the user to review and approve. Do not post anything — show every figure with its source.
