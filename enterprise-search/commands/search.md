---
description: Search across every connected source at once and return grouped, ranked results with links.
argument-hint: "[what you're looking for]"
---

# Search

Runs the **unified-search** skill: one query across chat, knowledge base, project tracker, and email.

## Instructions
1. Take the user's query from the argument. If it's empty or vague, ask for it (or suggest running **search-strategy** to refine it first).
2. Invoke the **unified-search** skill with the query.
3. Fan out to every connected source, dedupe, and rank by relevance and recency.
4. Return results grouped by source with a snippet and direct link each, and flag the single best match.
5. Offer a next step: refine with **search-strategy**, or synthesize a cited answer with **knowledge-synthesis**.
