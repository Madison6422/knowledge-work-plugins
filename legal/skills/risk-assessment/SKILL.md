---
name: risk-assessment
description: Assess the legal risk of a proposed action or deal — likelihood, impact, mitigations, and a go / caution / no-go recommendation. Claude drafts the analysis; a qualified attorney reviews and approves. This is not legal advice. Trigger with "assess the legal risk of...", "should we do this deal", "what could go wrong legally with...".
---

# Risk Assessment

Structured legal-risk analysis of a proposed action or deal, ending in a clear go / caution / no-go recommendation.

> **Not legal advice.** Claude assists with structuring the analysis only. A qualified attorney must review the risks, weightings, and recommendation and approve before any decision is made.

## What it does

Takes a described action, deal, or decision and works through the material legal risks — contractual, regulatory, IP, liability, reputational — rating each by likelihood and impact. It proposes mitigations for the significant risks and rolls the analysis up into a **go / caution / no-go** recommendation with the reasoning and the conditions that would change it.

## Connectors it uses

| Category | Placeholder | What it adds |
| --- | --- | --- |
| Knowledge base | `~~knowledge base` | Pulls prior risk assessments, precedent, and standard positions |
| Document management | `~~document management` | Retrieves the underlying contract, deal terms, or diligence materials |
| Chat | `~~chat` | Shares the assessment with stakeholders and captures decisions |

> **No connectors?** Describe the action or paste the deal terms and Claude structures the risk analysis from that plus general legal-risk practice. Connect `~~knowledge base` / `~~document management` so it can ground the analysis in your precedent and the actual deal documents.

## How it works

1. **Frame the question.** What action/deal is being assessed, and what outcome is intended?
2. **Gather context.** Connected: pull related docs and prior assessments from `~~document management` / `~~knowledge base`. Standalone: use what the user provides.
3. **Identify risks.** Enumerate material legal risks across contract, regulatory, IP, liability, and reputational dimensions.
<!-- CUSTOMIZE: the risk categories your team tracks, and any industry-specific ones -->
4. **Rate each.** Likelihood × impact, using your team's scale.
<!-- CUSTOMIZE: your likelihood/impact scale and what counts as "high" risk -->
5. **Propose mitigations.** For each significant risk, a concrete way to reduce likelihood or impact.
6. **Recommend.** Go / Caution / No-go, with the key drivers and the conditions that would flip the call. Escalate high-impact items to the attorney.

**You approve before it goes out.** Claude drafts the assessment and a recommendation; a qualified attorney reviews and approves. The decision rests with the attorney and business owner, not Claude.

## Output

```markdown
# Legal Risk Assessment — [Action / Deal]

**Assessed:** [date] · **Recommendation:** GO / CAUTION / NO-GO
**Attorney sign-off:** ☐ pending

## Context
- What's proposed / intended outcome: ...

## Risk register
| Risk | Category | Likelihood | Impact | Mitigation | Residual |
| --- | --- | --- | --- | --- | --- |
| Uncapped liability | Contract | Med | High | Negotiate cap | Med |
| Regulatory approval gap | Regulatory | Low | High | File before launch | Low |

## Recommendation
- **[GO / CAUTION / NO-GO]** because ...
- Would change if: ...

_Draft prepared by Claude. Not legal advice — attorney review and approval required._
```

## Customize this skill

- Edit the risk categories in step 3 for your industry and team.
- Set your likelihood/impact scale and thresholds in step 4.
<!-- CUSTOMIZE: who must approve a GO on high-impact deals -->
- Point context-gathering at your real `~~knowledge base` / `~~document management` locations.
- Adjust the recommendation labels if your team uses a different rubric.

## Related skills

- **contract-review** — deep-dive the contract that underlies the deal.
- **compliance-check** — test the action against a specific policy or regulation.
- **clause-library** — find protective language that mitigates flagged risks.
