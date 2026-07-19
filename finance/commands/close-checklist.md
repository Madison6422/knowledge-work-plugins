---
description: Drive the month-end close — checklist, tie-outs, and a close packet for sign-off
argument-hint: "[period, e.g. 'July 2026']"
---

# Close Checklist

Runs the `month-end-close` skill to track close tasks, run tie-outs, and assemble the packet.

## Instructions

1. Read `$ARGUMENTS` for the close period.
2. Run the `month-end-close` skill. Read balances and status from `~~data warehouse` and post updates or nudge owners via `~~chat` if connected; otherwise maintain the checklist from what the user pastes in.
3. Track each task through Not started → In progress → Done → Reviewed, and surface blockers or overdue items.
4. Run the required tie-outs and flag any break with the two figures that disagree.
5. Assemble the close packet and present it for the user to review and sign off. Do not mark the close complete — a person approves before the books are locked.
