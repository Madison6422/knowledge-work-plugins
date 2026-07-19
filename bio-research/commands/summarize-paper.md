---
description: Summarize a paper or preprint with its methods, numbers, limits, and relevance.
argument-hint: "[DOI, PMID, or pasted abstract]"
---

# Summarize Paper
Runs the **paper-summary** skill.

## Instructions
1. Read `$ARGUMENTS`. If it's a DOI/PMID/link, resolve the record via ~~literature; if it's pasted text, work directly from it.
2. Follow the **paper-summary** skill: extract the question, methods, and key results — keeping the actual numbers (effect sizes, n, CIs, p-values).
3. Give an honest limitations read and flag whether the source is peer-reviewed or a preprint.
4. Close with a one-to-two sentence relevance note tied to the user's program.
5. Remind the user to verify numbers against the source PDF before citing; not clinical guidance.
