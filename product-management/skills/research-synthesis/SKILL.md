---
name: research-synthesis
description: Synthesizes user interviews, survey responses, and support signals into themes, insights, and recommended bets. Pulls from conversation intelligence, helpdesk, and product analytics. Trigger with "synthesize this research", "what are the themes across these interviews", "turn this feedback into insights".
---

# Research Synthesis
Cut a stack of interviews, survey data, and support tickets down to a few themes and clear next bets.

## What it does
Reads across qualitative and quantitative sources — call transcripts, survey open-ends, support conversations, usage data — and clusters them into recurring themes. For each theme it names the insight, weighs how much evidence backs it, and proposes a recommended bet, so research turns into decisions instead of a document nobody reads.

## Connectors it uses
| Category | Placeholder | What it adds |
| --- | --- | --- |
| Conversation intelligence | `~~conversation intelligence` | Interview and user-call transcripts to pull quotes and patterns from |
| Helpdesk | `~~helpdesk` | Support tickets and conversations that reveal recurring pain and requests |
| Product analytics | `~~product analytics` | Usage and funnel data to size how widespread a theme really is |

> **No connectors?** Paste transcripts, survey exports, and ticket text directly. The skill clusters and synthesizes from what you provide — connectors just widen the evidence net and let it quantify reach.

## How it works
1. Gather sources: transcripts from `~~conversation intelligence`, tickets from `~~helpdesk`, usage from `~~product analytics`, plus anything pasted in.
2. **Cluster** signals into themes; keep verbatim quotes as evidence.
3. For each theme, write the **insight** and rate evidence strength (how many sources, how consistent).
<!-- CUSTOMIZE: set your evidence bar — e.g. a theme needs ≥3 independent sources to be "strong" -->
4. Quantify **reach** with analytics where possible (how many users, what % of the base).
5. Recommend a **bet** per theme and rank them.
<!-- CUSTOMIZE: define your segments so themes can be split by persona/plan/region -->
6. List what's **uncertain** and what research would resolve it.

## Output
```markdown
# Research synthesis: [topic] — [date range]
**Sources:** [n interviews · n tickets · n survey responses]

## Theme 1: [Name]
- **Insight:** [what users actually need and why]
- **Evidence:** [strong/medium/weak] — [n sources], reach ~[%]
- **Representative quote:** "[verbatim]"
- **Recommended bet:** [action]

## Ranked bets
1. [Bet] — [expected impact / effort]

## Still uncertain
- [Open question and how to resolve it]
```

## Customize this skill
- Set your **evidence bar** for what counts as a strong vs. weak theme.
- Define your **user segments** so themes can be sliced by persona, plan, or region.
- Point sources at the **right teams or boards** in helpdesk and conversation tools.

## Related skills
- `write-spec` — turn a recommended bet into a full spec.
- `roadmap-plan` — feed sized insights into impact scoring.
- `competitive-landscape` — check whether a theme is a gap competitors already fill.
