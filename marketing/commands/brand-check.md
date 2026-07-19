---
description: Check a draft against your brand voice and flag off-tone lines with fixes.
argument-hint: "[paste draft or file]"
---

# Brand Check

Runs the **brand-voice** skill to review a draft against your voice and messaging guidelines.

## Instructions
1. Read `$ARGUMENTS` for the draft text or file to check.
2. Run the **brand-voice** skill: load the voice guide and banned-word list from `~~knowledge base` if connected, otherwise use the voice notes pasted with the draft.
3. Scan line by line for off-tone phrasing, banned words, jargon, and hype.
4. Return each flagged line with the issue and an on-brand rewrite, plus an overall on-tone read.
