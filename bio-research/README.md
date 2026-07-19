# Bio Research
Connect to preclinical research tools and databases (literature search, genomics analysis, target prioritization) to accelerate early-stage life sciences R&D.

Built for preclinical and early-discovery researchers. Every skill works standalone from what you paste in, and gets sharper when you connect the databases in `.mcp.json`. **Outputs are research aids to be verified against primary sources — not clinical guidance.**

## What's inside

### Skills
| Skill | What it does |
|---|---|
| literature-search | Structured, cited search across papers and preprints with links to primary sources |
| target-prioritization | Evidence dossier scoring a target on genetics, expression, tractability, safety, and competition |
| paper-summary | Numbers-first summary of one paper/preprint: question, methods, results, limits, relevance |
| experiment-design | Preclinical design: hypothesis, controls, sample size/power, readouts, and pitfalls |
| pathway-analysis | Map a gene/pathway: known biology, disease links, and interacting targets |

### Commands
| Command | What it does |
|---|---|
| `/bio-research:lit-search` | Runs literature-search on a question or topic |
| `/bio-research:target-brief` | Runs target-prioritization for a target + indication |
| `/bio-research:summarize-paper` | Runs paper-summary on a DOI, PMID, or pasted abstract |

## Connectors
Skills refer to tools by category using `~~placeholder` names, so any MCP server in a category works. See **[CONNECTORS.md](CONNECTORS.md)** for the full mapping. Categories used: `~~literature`, `~~clinical trials`, `~~compound database`, `~~target evidence`, `~~research data`, `~~lab notebook`, `~~figures`.

## Customize for your team
- Set default search filters (species, model systems, date windows, preprint policy) in **literature-search**.
- Set scoring weights and pass/fail thresholds per axis in **target-prioritization**.
- Add your active programs/targets so **paper-summary** and **pathway-analysis** judge relevance consistently.
- Set standard power/alpha, default controls, and animal-number limits in **experiment-design**.
- Look for `<!-- CUSTOMIZE: ... -->` markers throughout the skills — each flags a spot to add your team's terminology and rules.
