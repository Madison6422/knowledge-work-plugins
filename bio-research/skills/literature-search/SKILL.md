---
name: literature-search
description: Run a structured literature search across published papers and preprints, screen hits for relevance, and return a cited summary with links to the primary sources. Trigger with "run a literature search on [topic]", "what does the literature say about [target/disease]", "find papers on [mechanism]".
---

# Literature Search
A structured, reproducible sweep of the literature that returns a cited, screened summary — not a raw hit list.

## What it does
Turns a research question into an explicit search strategy, runs it across ~~literature sources, screens results for relevance and study type, and returns a short synthesis with inline citations and links to every primary paper or preprint. The goal is a transparent, repeatable search you can hand to a colleague, not a black-box answer.

## Connectors it uses
| Category | Placeholder | What it adds |
|---|---|---|
| Literature | `~~literature` | Peer-reviewed papers and preprints, with abstracts, metadata, and stable links |
| Clinical trials | `~~clinical trials` | Registered and completed trials touching the same target or indication |
| Target–disease evidence | `~~target evidence` | Cross-check a gene/target claim against aggregated association data |

> **No connectors?** Paste in abstracts, PDFs, or a reference list and Claude will screen and synthesize those, plus use general web research to frame the field. Connecting ~~literature makes the search systematic and the links verifiable.

## How it works
1. **Frame the question.** Restate it as a searchable question (population/system, intervention/exposure, comparison, outcome). Confirm scope, date window, and any must-include or must-exclude terms.
2. **Build the strategy.** Draft explicit query terms and synonyms. Show them so you can adjust before running.
<!-- CUSTOMIZE: add your team's standard filters — species, model systems, minimum sample size, preprint policy. -->
3. **Run the search.** Query ~~literature for papers and preprints; optionally pull matching studies from ~~clinical trials. Standalone: screen the sources you pasted in.
4. **Screen for relevance.** Rank hits by fit to the question and note study type (in vitro, animal model, human, review). Drop off-topic and clearly weak results, with a one-line reason.
5. **Synthesize.** Write a short summary grouped by theme or finding, each claim carrying an inline citation. Flag where evidence conflicts or is thin.
6. **Return sources.** List every cited item with authors, year, venue, and a direct link.

## Output
```markdown
# Literature Search: <question>
**Scope:** <dates, systems, filters>  ·  **Sources searched:** ~~literature (+ ~~clinical trials)

## Search strategy
- Query terms: <terms / synonyms>
- Screened: <N> hits → <M> included

## Key findings
- <Finding, grouped by theme>. [Author Year]
- <Finding, with the caveat>. [Author Year]
- **Conflicts / gaps:** <where the literature disagrees or is silent>

## Included sources
1. Author et al. (Year). Title. Venue. <link>
2. ...

<!-- Research aid — verify every claim against the primary source before acting on it. Not clinical guidance. -->
```

## Customize this skill
- Set default date windows, species, and study-type filters for your program.
- Add your preferred evidence hierarchy (e.g. how you weight preprints vs. peer-reviewed).
- Adjust which connectors are searched by default.

## Related skills
- **paper-summary** — deep-dive a single paper the search surfaced.
- **target-prioritization** — turn target-level findings into a ranked dossier.
- **pathway-analysis** — explore the biology behind a hit.
