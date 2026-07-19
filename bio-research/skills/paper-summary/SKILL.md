---
name: paper-summary
description: Summarize a specific paper or preprint — its question, methods, key results with the actual numbers, limitations, and relevance to your program. Trigger with "summarize this paper", "what are the key results in [DOI/PMID]", "is this preprint relevant to my program".
---

# Paper Summary
A tight, numbers-first read of one paper or preprint — what they asked, what they did, what they found, and what it means for you.

## What it does
Takes a single paper (DOI, PMID, a link, or a pasted abstract/PDF), retrieves or reads it, and returns a structured summary that keeps the actual effect sizes, sample sizes, and statistics — not vague "significant improvement" language. Closes with an honest limitations read and a relevance note tied to your program.

## Connectors it uses
| Category | Placeholder | What it adds |
|---|---|---|
| Literature | `~~literature` | Resolve a DOI/PMID to the full record, abstract, and metadata |
| Target–disease evidence | `~~target evidence` | Cross-check the paper's target/disease claims against aggregated evidence |

> **No connectors?** Paste the abstract or the full text and Claude summarizes it directly. Connecting ~~literature lets it resolve an identifier and pull the record for you, and confirm venue and citation details.

## How it works
1. **Locate the paper.** From a DOI/PMID/link, retrieve the record via ~~literature. From pasted text, work directly from what you gave.
2. **Extract the core.** Identify the research question, study design, and system/model.
3. **Pull the numbers.** Capture the primary results with their actual values — effect sizes, n, confidence intervals, p-values, key figures — rather than paraphrasing them away.
<!-- CUSTOMIZE: list the readouts your team always wants pulled (e.g. IC50/EC50, fold-change, hazard ratio, cohort size). -->
4. **Read the limits.** Note sample size, controls, confounders, generalizability, and whether it is peer-reviewed or a preprint.
5. **Tie to your program.** State plainly how it supports, complicates, or is neutral to your current work.
<!-- CUSTOMIZE: name your active programs/targets so relevance is judged against them. -->

## Output
```markdown
# Paper Summary
**Title:** <title>  ·  **Authors:** <first et al., year>  ·  **Venue:** <journal / preprint server>
**Type:** <peer-reviewed | preprint>  ·  **Link:** <DOI / URL>

## Question
<one sentence>

## Methods
<design, system/model, key assays; sample size>

## Key results (with numbers)
- <result — value, n, CI/p, figure ref>
- <result — value, n, CI/p>

## Limitations
- <sample size / controls / confounders / generalizability>

## Relevance to your program
<supports / complicates / neutral — and why, in 1–2 sentences>

<!-- Research aid — verify numbers against the source PDF before citing. Not clinical guidance. -->
```

## Customize this skill
- Set the standard readouts to always extract for your assay types.
- Add your program/target list so relevance is scored consistently.
- Adjust how strictly preprints are flagged vs. peer-reviewed work.

## Related skills
- **literature-search** — find papers worth summarizing.
- **target-prioritization** — feed a paper's evidence into a target dossier.
- **pathway-analysis** — expand on the biology a paper describes.
