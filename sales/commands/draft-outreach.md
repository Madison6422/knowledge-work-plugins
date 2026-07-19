---
description: Draft a personalized outreach sequence grounded in real account context. You approve before sending.
argument-hint: "[prospect or account]"
---

# Draft Outreach

Runs the **draft-outreach** skill to write a personalized email sequence for a prospect.

## Instructions
1. Read `$ARGUMENTS` to identify the prospect or account. If empty, ask who the outreach is for.
2. Invoke the **draft-outreach** skill with that prospect and any context provided.
3. Let it gather personalization hooks from web research, `~~data enrichment`, and `~~CRM`, then draft a first email plus follow-ups.
4. Show the full sequence for review. **Nothing sends until the user approves** — only then may it load into `~~sales engagement`.
