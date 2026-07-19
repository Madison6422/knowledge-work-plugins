---
name: insight-story
description: Turn an analysis into a stakeholder-ready narrative — headline finding, evidence, so-what, and recommended action — with numbers validated before sharing. Trigger with "write this up for leadership", "turn this into a story", "what's the takeaway", "make this stakeholder-ready".
---

# Insight Story

Turn a chart or an analysis into a decision — headline, evidence, so-what, and a clear recommended action.

## What it does
Takes the output of an analysis and shapes it into a narrative a busy stakeholder can act on: a one-line headline finding, the supporting evidence, the "so what" for the business, and a concrete recommended action. Before anything ships, it re-validates the key numbers against the source so the story rests on figures that hold up.

## Connectors it uses

| Category | Placeholder | What it adds |
|---|---|---|
| Data warehouse | `~~data warehouse` | Re-runs the headline numbers against the source to confirm they're right before sharing |
| Chat | `~~chat` | Posts the summary to the right channel or teammate once you approve it |

> **No connectors?** Paste the analysis and the key figures. Claude drafts the narrative and lists exactly which numbers to re-verify; you confirm them and share manually.

## How it works
1. Find the single most important finding — the headline — and write it as a sentence with a number in it.
2. **Validate before sharing:** re-check the headline figure(s) against `~~data warehouse` (or ask you to confirm the source). Fix or flag anything that doesn't reconcile.
   <!-- CUSTOMIZE: which numbers always require a second source or a teammate's sign-off before they leave the team -->
3. Lay out the evidence: 2–4 supporting facts or a chart, at the altitude the audience needs.
   <!-- CUSTOMIZE: your audiences and their altitude — exec (one number + action) vs analyst (methods + caveats) -->
4. State the **so-what**: what this means for the business and the decision on the table.
5. Recommend a concrete next action with an owner and a rough size of the opportunity/risk.
   <!-- CUSTOMIZE: your headline/summary template and house tone -->
6. **You approve before it goes out.** Claude drafts; once you sign off, it can post to `~~chat`. The human sends anything that reaches stakeholders.

## Output
```markdown
**Headline:** Paid Search drove 38% of Q2 revenue — up from 24% in Q1.

**Evidence**
- Paid Search revenue grew +58% QoQ ($1.2M → $1.9M); all other channels flat.
- Lift is concentrated in the new "high-intent" campaigns (validated against warehouse: $1.90M ✓).
- Blended CAC held steady, so the growth was efficient.

**So what:** One channel is now our growth engine — and a concentration risk.

**Recommended action:** Shift 15% of Q3 budget into high-intent Paid Search (owner: Growth), while testing one diversification channel to reduce dependence. Upside ≈ $300K/quarter.

<!-- Draft — validated headline numbers. You approve before this goes to leadership. -->
```

## Customize this skill
- Set which numbers require a second source or sign-off in step 2.
- Define your audiences and their altitude in step 3.
- Set your summary template and house tone in step 5.

## Related skills
- **statistical-analysis** — make sure the finding is real before you sell it.
- **build-visualization** — the chart that carries the evidence.
- **write-query** — re-pull any number that needs validating.
