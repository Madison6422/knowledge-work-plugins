---
name: search-strategy
description: Turn a vague ask into a precise, high-yield search — clarify intent, expand synonyms and acronyms, choose which sources to hit, and iterate on the results. Works standalone as a query coach and gets sharper when it knows which sources are connected. Trigger with "help me search for [X]", "I can't find [thing]", "how should I look for [topic]".
---

# Search Strategy

Refine a fuzzy question into a query that actually finds the thing.

## What it does
Acts as a search coach. It reads what you're really after, asks one or two clarifying questions when the ask is ambiguous, expands your terms with synonyms and internal acronyms, and recommends which sources to search and in what order. After the first pass it reads the results with you and iterates — tightening or broadening terms until you land on the answer. It works with zero connectors as pure query advice and gets more targeted when it knows what's connected.

## Connectors it uses
| Category | Placeholder | What it adds |
| --- | --- | --- |
| Chat | `~~chat` | Signals where discussion lives, to prioritize as a source |
| Knowledge base | `~~knowledge base` | Signals where canonical docs live |
| Project tracker | `~~project tracker` | Signals where work items and status live |
| Email | `~~email` | Signals where external and announcement threads live |

> **No connectors?** Fully usable as a query coach — Claude sharpens your terms and suggests where to look even with nothing connected. Connectors let it recommend the specific source most likely to hold the answer.

## How it works
1. Restate the ask in one line to confirm intent; ask at most 1–2 clarifying questions if it's ambiguous.
<!-- CUSTOMIZE: add the questions worth asking for your team — e.g. which project, which quarter, internal vs. customer-facing -->
2. Expand the query: synonyms, plural/singular, internal acronyms, and likely document titles.
3. **Route to sources:** recommend which of `~~chat`, `~~knowledge base`, `~~project tracker`, `~~email` is most likely to hold it, and the order to try.
<!-- CUSTOMIZE: set default routing — e.g. policy questions → knowledge base first, status → project tracker first -->
4. Propose the exact query (or hand off to **unified-search** to run it).
5. **Iterate:** review results together — too many hits, tighten; too few, broaden or swap sources; repeat until found.

## Output
```markdown
# Search plan: "<your ask>"
**What you're really after:** <one-line intent>
**Clarify (if needed):** <1–2 questions>

## Query terms
- Core: <terms>
- Also try: <synonyms / acronyms / likely titles>

## Where to look (in order)
1. <source> — <why it's most likely>
2. <source> — <fallback>

## Next step
<run unified-search with this query | refine after first results>
```

## Customize this skill
- Add the clarifying questions that matter most for your team under step 1.
- Set default source routing by question type under step 3.
<!-- CUSTOMIZE: maintain a synonym/acronym list so vague terms expand to what your docs actually say -->
- Keep a living synonym and acronym list for step 2.

## Related skills
- **unified-search** — run the refined query across every source.
- **source-management** — know which sources exist before routing to them.
- **knowledge-synthesis** — synthesize an answer once the right results are found.
