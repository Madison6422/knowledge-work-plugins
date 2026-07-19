---
description: Append a fact to your personal memory file so Claude stops re-asking.
argument-hint: "[the thing to remember]"
---

# Remember

Appends a fact to your memory via the **personal-memory** skill.

## Instructions

1. Take `$ARGUMENTS` as the fact to remember. If empty, ask what to record.
2. Run the **personal-memory** skill: locate the memory file (create it if missing).
3. Add the fact as a single dated bullet under the right section (Projects, People, Preferences, Recurring context, or Glossary). If it contradicts an existing fact, update in place.
4. Skip anything sensitive — no passwords, tokens, or secrets.
5. Echo back exactly what was written and where, so the user can confirm.
