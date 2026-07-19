---
name: knowledge-synthesis
description: Go beyond a list of links — read the top hits across every source and write one cited answer, flagging where sources disagree or look stale. Works standalone on pasted material and gets richer as sources connect. Trigger with "what's our answer on [X]", "synthesize what we know about [topic]", "give me the cited answer, not just links".
---

# Knowledge Synthesis

Not a list of links — an answer, with citations and caveats.

## What it does
Takes the strongest results across your sources, reads them, and writes a single coherent answer to your question. Every claim carries a citation back to its source, and the answer explicitly calls out where sources conflict or where a doc looks out of date, so you know how much to trust it. It works on whatever you paste in and gets more complete when it can pull the top hits directly from connected sources.

## Connectors it uses
| Category | Placeholder | What it adds |
| --- | --- | --- |
| Chat | `~~chat` | Recent decisions and context that never made it into a doc |
| Knowledge base | `~~knowledge base` | Canonical, authoritative statements to anchor the answer |
| Project tracker | `~~project tracker` | Current status and what's actually shipping |
| Email | `~~email` | External commitments and announcements |

> **No connectors?** Paste in the docs or threads and Claude synthesizes and cites from those. Connectors let it gather the top hits itself and check them against each other.

## How it works
1. Confirm the question and what a good answer would settle.
2. Gather the top hits per source (via **unified-search**) or read the material you provide.
3. Read each source and pull the load-bearing claims, keeping a citation for every one.
4. **Reconcile:** where sources agree, state it plainly; where they disagree, show both and note which is more authoritative or recent.
<!-- CUSTOMIZE: set your source-of-truth order — e.g. knowledge base overrides chat; a signed doc overrides a draft -->
5. **Flag staleness:** mark any source past your freshness limit as "may be outdated."
<!-- CUSTOMIZE: define "stale" for your team — e.g. anything not updated in 6 months on policy topics -->
6. Write the answer with inline citations, then list open questions the sources don't resolve.

## Output
```markdown
# Answer: <question>
<clear 2–5 sentence answer, with inline citations [1][2]>

## Key points
- <claim> [source, date]

## Where sources disagree
- <topic>: <source A says…> vs. <source B says…> — <which to trust and why>

## Freshness flags
- ⚠️ <source> last updated <date> — may be outdated

## Sources
[1] <title> — <source> · <link>
[2] <title> — <source> · <link>

## Still open
- <question the sources don't answer>
```

## Customize this skill
- Set your source-of-truth precedence under step 4.
- Define your staleness threshold under step 5.
<!-- CUSTOMIZE: note topics where a human must confirm before the answer is acted on (policy, legal, financial) -->
- List topics where a synthesized answer needs human confirmation before anyone acts on it. You review before it's treated as final.

## Related skills
- **unified-search** — gather the hits this skill reads and cites.
- **search-strategy** — sharpen the question before synthesizing.
- **daily-digest** — synthesis powers the "what changed and why it matters" digest.
