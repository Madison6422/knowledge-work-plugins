---
description: Profile a table or dataset before you analyze it
argument-hint: "[table or dataset]"
---

# Explore

Runs the **explore-dataset** skill to profile a dataset — row counts, distributions, nulls, keys, and data-quality flags.

## Instructions
1. Take the table or dataset in `$ARGUMENTS` and confirm its intended grain.
2. Profile it via `~~data warehouse` (row count, types, nulls, distinct counts, min/max) or the pasted sample.
3. Check the primary key for uniqueness and flag duplicates or join fan-out.
4. Render distributions in `~~notebook` if connected, and list any data-quality issues.
5. Summarize what the dataset is good for and what to avoid, per the **explore-dataset** skill.
