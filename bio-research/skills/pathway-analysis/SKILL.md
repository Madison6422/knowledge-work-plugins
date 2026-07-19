---
name: pathway-analysis
description: Explore a gene or pathway of interest — known biology, disease links, and interacting targets — pulling from target-evidence and literature sources. Trigger with "walk me through the [gene] pathway", "what interacts with [target]", "disease links for [pathway]".
---

# Pathway Analysis
A guided map of a gene or pathway — its biology, its disease connections, and the neighboring targets worth knowing about.

## What it does
For a gene, protein, or pathway, assembles known function and regulation, disease associations, and the interacting partners and upstream/downstream nodes — then highlights which neighbors are themselves plausible targets. Useful for orienting on unfamiliar biology or expanding a target hypothesis into its network.

## Connectors it uses
| Category | Placeholder | What it adds |
|---|---|---|
| Target–disease evidence | `~~target evidence` | Disease associations, expression, and interaction/pathway membership |
| Literature | `~~literature` | Mechanistic detail and recent findings on the pathway |

> **No connectors?** Claude maps the pathway from public knowledge and web research given the gene/pathway name. Connecting ~~target evidence grounds the disease links and interactors in aggregated data; ~~literature adds current mechanistic evidence.

## How it works
1. **Anchor the node.** Confirm the gene/protein/pathway and the disease context you care about (if any).
2. **Known biology.** Summarize function, localization, and regulation, with sources.
3. **Disease links.** From ~~target evidence, pull associated diseases and the strength/direction of each link.
4. **Interactors & neighbors.** Map upstream regulators, downstream effectors, and direct interactors; note pathway membership.
<!-- CUSTOMIZE: set which interaction/evidence types you trust (e.g. physical vs. predicted, minimum confidence). -->
5. **Spot targetable neighbors.** Flag interactors that are themselves tractable or already-drugged, as hypothesis expansions.
6. **Synthesize.** Present a compact map plus a short narrative, every claim linked to a source.
<!-- CUSTOMIZE: name the diseases/indications your program cares about so disease links are prioritized. -->

## Output
```markdown
# Pathway Analysis: <gene / pathway>
**Context:** <disease/indication, if any>

## Known biology
<function, localization, regulation> [sources]

## Disease links
| Disease | Association | Direction | Source |
|---|---|---|---|
| <disease> | <strength> | <up/down> | ~~target evidence |

## Interactors & neighbors
- Upstream: <nodes>
- Downstream: <nodes>
- Direct interactors: <partners>

## Targetable neighbors
- <interactor> — <why it's interesting: tractable / drugged / genetic support>

<!-- Research aid — verify interactions and disease links against primary sources. Not clinical guidance. -->
```

## Customize this skill
- Set trusted interaction/evidence types and confidence cutoffs.
- List your priority indications so disease links are ranked for you.
- Adjust how far out the network is expanded (direct interactors vs. second-degree).

## Related skills
- **target-prioritization** — score a targetable neighbor you surface here.
- **literature-search** — pull the mechanistic evidence behind a pathway edge.
- **paper-summary** — deep-read a key pathway paper.
