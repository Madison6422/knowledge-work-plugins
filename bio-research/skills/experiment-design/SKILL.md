---
name: experiment-design
description: Help design a preclinical experiment — hypothesis, controls, sample size and power, readouts, and common pitfalls — and log the protocol to your notebook. Trigger with "help me design an experiment for [aim]", "what controls do I need for [assay]", "power calculation for [study]".
---

# Experiment Design
A rigorous first-pass design for a preclinical experiment — testable hypothesis, the right controls, a defensible sample size, and the pitfalls to avoid.

## What it does
Works from your aim to a concrete plan: a falsifiable hypothesis, positive/negative and vehicle controls, sample-size and power considerations, primary and secondary readouts, randomization and blinding, and a list of common failure modes for that assay. Optionally logs the finalized protocol to your ~~lab notebook so it is captured before you start at the bench.

## Connectors it uses
| Category | Placeholder | What it adds |
|---|---|---|
| Lab notebook | `~~lab notebook` | Log the protocol, design rationale, and planned analysis as an entry |
| Literature | `~~literature` | Ground controls, doses, and effect-size assumptions in prior work |

> **No connectors?** Claude produces the full design and you paste it into your notebook manually. Connecting ~~lab notebook lets it write the protocol as an entry; ~~literature lets it anchor assumptions (expected effect size, standard controls) in published methods.

## How it works
1. **State the hypothesis.** Convert the aim into a specific, falsifiable prediction with a defined comparison.
2. **Define groups & controls.** Specify treatment arms plus positive, negative, and vehicle/sham controls; note randomization and blinding.
<!-- CUSTOMIZE: list your lab's default control set and model systems per assay type. -->
3. **Size the study.** Estimate sample size from an expected effect size and variability, stating the assumptions and desired power/alpha. Flag when a pilot is the honest answer.
<!-- CUSTOMIZE: set your standard power (e.g. 80%) and alpha, and any welfare/3Rs limits on animal numbers. -->
4. **Choose readouts.** Define the primary readout and secondary/exploratory ones, plus how each is measured.
5. **Plan the analysis.** Name the statistical test and pre-register the comparison before data collection.
6. **List pitfalls.** Call out batch effects, plate/position effects, pseudoreplication, and other common traps for this design.
7. **Log it.** With approval, write the protocol to ~~lab notebook. **You approve before anything is logged** — Claude drafts the entry; you confirm it goes in.

## Output
```markdown
# Experiment Design: <aim>
## Hypothesis
<falsifiable prediction + comparison>

## Groups & controls
| Group | n | Purpose |
|---|---|---|
| Treatment | <n> | test arm |
| Vehicle / sham | <n> | control |
| Positive control | <n> | assay validity |

Randomization: <method>  ·  Blinding: <who/what>

## Sample size & power
<estimate + assumptions: effect size, variability, power, alpha>

## Readouts
- Primary: <readout, method>
- Secondary: <readouts>

## Analysis plan
<test, comparison, pre-registered>

## Pitfalls to avoid
- <batch/plate effects, pseudoreplication, ...>

<!-- Research aid — confirm power calcs and welfare/ethics approvals with your team before running. Not clinical guidance. -->
```

## Customize this skill
- Set default controls, model systems, and readouts per assay type.
- Set your standard power/alpha and any animal-number ceilings.
- Point the logging step at your team's notebook template and required fields.

## Related skills
- **literature-search** — find effect sizes and precedent for your assumptions.
- **paper-summary** — pull methods detail from a reference protocol.
- **target-prioritization** — the open questions a dossier raises often become these experiments.
