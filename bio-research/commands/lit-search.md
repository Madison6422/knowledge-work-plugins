---
description: Run a structured, cited literature search on a research question or topic.
argument-hint: "[research question or topic]"
---

# Lit Search
Runs the **literature-search** skill.

## Instructions
1. Read `$ARGUMENTS` as the research question or topic. If it's broad, ask one clarifying question about scope (system, disease, date window) before running.
2. Follow the **literature-search** skill: frame the question, build an explicit search strategy, and confirm terms with the user.
3. Search ~~literature (and ~~clinical trials where relevant); screen hits for relevance and study type.
4. Return the cited summary with a listed source for every claim and direct links to each primary paper or preprint.
5. Remind the user the output is a research aid to verify against primary sources, not clinical guidance.
