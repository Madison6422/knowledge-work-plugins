---
description: One line shown in the slash-command menu describing what this command does.
argument-hint: "[what the user types after the command]"
---

# Example Command

Runs the **example-skill** skill. <!-- CUSTOMIZE: point this at your real skill -->

## Instructions

1. Take the user's argument (`$ARGUMENTS`) as the subject.
2. Invoke the `example-skill` workflow with it.
3. If required context is missing and no connectors are available, ask the user
   for the minimum needed, then proceed.
4. Return the deliverable in the skill's output format.
