---
description: Write, explain, or optimize SQL against the team's warehouse
argument-hint: "[what you want to know]"
---

# Write Query

Runs the **write-query** skill to turn your question into clean, commented SQL — sample-checked before it runs heavy.

## Instructions
1. Take the question in `$ARGUMENTS` and restate it, confirming the grain and time window.
2. Use the `~~data warehouse` schema (or a pasted schema) to find the real tables and join keys.
3. Draft SQL with inline comments, then run a small sample-check (`LIMIT` preview or cheap `COUNT`) before the full query.
4. Return the result with caveats (nulls, duplicates, timezone). Follow the **write-query** skill for conventions and thresholds.
