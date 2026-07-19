---
description: Fast-triage an inbound NDA with a sign / redline / escalate recommendation.
argument-hint: "[NDA file or paste]"
---

# Triage NDA

Runs the **nda-triage** skill on the NDA you provide.

## Instructions

1. Take the NDA from `$ARGUMENTS` — a file path, a link, or pasted text. If nothing is provided, ask for the NDA.
2. Run the **nda-triage** skill: classify mutual vs one-way, extract term and carve-outs, and check against standard positions from `~~document management` / `~~knowledge base` if connected (otherwise the positions the user provides).
3. Surface red flags and give a clear **Sign / Redline / Escalate** recommendation with reasons and any suggested fixes.
4. Present to the attorney. Do not sign or route for signature without attorney approval.
5. Close with the reminder: draft prepared by Claude, not legal advice — a qualified attorney must review and approve.
