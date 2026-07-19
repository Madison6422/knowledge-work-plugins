---
description: Prep for a specific sales call — snapshot, attendees, history, agenda, questions, objections.
argument-hint: "[company or meeting]"
---

# Call Prep

Runs the **call-prep** skill to build a one-page plan for a specific upcoming call.

## Instructions
1. Read `$ARGUMENTS` to identify the call — a company name, a meeting, or a time. If empty, ask which call, or check `~~calendar` for the next one.
2. Invoke the **call-prep** skill with that call.
3. Let it assemble the account snapshot, attendee research, prior touches, suggested agenda, discovery questions, and likely objections — using `~~CRM`, `~~email`, `~~chat`, and `~~conversation intelligence` when connected.
4. Return the completed prep in the skill's output format.
