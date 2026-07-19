---
description: Draft on-brand content from a brief in your team's voice and structure.
argument-hint: "[content type + topic]"
---

# Draft Content

Runs the **content-draft** skill to produce a ready-to-edit, on-brand draft.

## Instructions
1. Read `$ARGUMENTS` for the content type (blog, email, social, landing) and the topic; ask only if the type is missing.
2. Run the **content-draft** skill: pull voice rules from `~~knowledge base` and assets from `~~design` if connected, otherwise use the pasted brief.
3. Draft in the structure for that content type, with alternate hooks or subject lines.
4. Return the draft plus a short "needs review before publish" list for any claim requiring a fact-check or sign-off.
