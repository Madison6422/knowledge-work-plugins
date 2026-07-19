---
description: Check a document, process, or request against a named policy or regulation.
argument-hint: "[document + policy/regulation]"
---

# Compliance Check

Runs the **compliance-check** skill on the item and policy you provide.

## Instructions

1. Read `$ARGUMENTS` for two things: the item to check (document, process, or request) and the named policy or regulation. If either is missing, ask for it.
2. Run the **compliance-check** skill: load the current policy/regulation text from `~~knowledge base` / `~~document management` if connected (otherwise use the pasted text or named rule), then map each requirement to the item.
3. Mark each requirement Compliant / Gap / Unclear, citing the specific section, and list the required action and owner for every gap.
4. Escalate ambiguous or high-stakes items to counsel. Do not treat the output as a final compliance determination.
5. Close with the reminder: draft prepared by Claude, not legal advice and not a substitute for counsel — a qualified attorney must review and approve.
