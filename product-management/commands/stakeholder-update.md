---
description: Write a concise stakeholder update tailored to exec or team.
argument-hint: "[audience, e.g. 'exec' or 'team']"
---

# Stakeholder Update
Runs the `stakeholder-update` skill to draft a concise update sized to the audience.

## Instructions
1. Read `$ARGUMENTS` as the audience (e.g. `exec` or `team`). If missing, ask who the update is for.
2. Run the **stakeholder-update** skill: what shipped, what's next, risks, and asks.
3. Pull status from `~~project tracker` and recent decisions from `~~chat` when connected; otherwise use the notes the user pastes in.
4. Tune tone for the audience — outcomes and asks for execs, more context for the team.
5. Return the draft for review. The user approves and sends it — do not post or email anything automatically.
