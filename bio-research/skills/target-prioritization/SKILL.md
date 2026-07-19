---
name: target-prioritization
description: Assemble an evidence dossier for a drug target — genetic association, expression, tractability, safety, and competition — and rank candidates against a chosen indication. Trigger with "build a target brief for [gene] in [disease]", "prioritize these targets", "is [target] worth pursuing for [indication]".
---

# Target Prioritization
An evidence dossier that scores a drug target across the axes that actually decide whether it advances.

## What it does
For one target or a shortlist, pulls together genetic association, tissue/disease expression, tractability (is it druggable, are there tool compounds), safety liabilities, and the competitive landscape — then rolls it into a ranked, evidence-linked recommendation. Every score traces back to a source so the reasoning is auditable.

## Connectors it uses
| Category | Placeholder | What it adds |
|---|---|---|
| Target–disease evidence | `~~target evidence` | Genetic association, expression, and tractability signals for target–disease pairs |
| Compound database | `~~compound database` | Known bioactive compounds, chemical tractability, and existing tool molecules |
| Literature | `~~literature` | Mechanistic and validation evidence behind each axis |
| Clinical trials | `~~clinical trials` | Who else is in the clinic against this target or indication |

> **No connectors?** Give Claude what you know (target, indication, any internal data) and it will structure the dossier and reason from public knowledge and web research. Connecting ~~target evidence and ~~compound database makes the association and tractability scores data-backed rather than qualitative.

## How it works
1. **Define the question.** Confirm the target(s) and the indication — evidence is only meaningful against a specific disease context.
2. **Genetics & association.** From ~~target evidence, gather genetic association strength and directionality for the target–disease pair.
3. **Expression.** Check disease-relevant tissue expression and specificity (on-target-elsewhere risk).
4. **Tractability.** From ~~target evidence and ~~compound database, assess modality options (small molecule, antibody, other) and whether tool compounds exist.
5. **Safety.** Note constraint/essentiality signals and known liabilities; flag anything that needs a tox review.
6. **Competition.** From ~~clinical trials and ~~literature, map who is already pursuing the target/indication and how far along.
7. **Score & rank.** Roll the axes into a scorecard using your weights, with a plain-language recommendation and the open questions.
<!-- CUSTOMIZE: set your scoring weights and pass/fail thresholds per axis (e.g. min genetic evidence, expression specificity cutoff). -->

## Output
```markdown
# Target Brief: <GENE> — <indication>
**Recommendation:** <advance / watch / deprioritize>  ·  **Confidence:** <H/M/L>

| Axis | Signal | Score | Source |
|---|---|---|---|
| Genetic association | <summary> | <●●●○○> | ~~target evidence |
| Expression / specificity | <summary> | <●●○○○> | ~~target evidence |
| Tractability | <modalities, tool compounds> | <●●●●○> | ~~compound database |
| Safety liabilities | <summary> | <●●○○○> | ~~target evidence / ~~literature |
| Competition | <programs in clinic> | <●●●○○> | ~~clinical trials |

## Rationale
<2–4 sentences tying the scores to the recommendation>

## Open questions / next experiments
- <what would change the call>

<!-- Research aid for internal prioritization — verify against primary sources. Not clinical or investment guidance. -->
```

## Customize this skill
- Set per-axis weights and thresholds that match your portfolio strategy.
- Add internal axes (IP position, manufacturability, biomarker availability).
- Choose which modalities your team can actually pursue, so tractability is scored realistically.

## Related skills
- **pathway-analysis** — go deeper on the target's biology and interactors.
- **literature-search** — pull the validation evidence behind an axis.
- **experiment-design** — design the experiment that closes an open question.
