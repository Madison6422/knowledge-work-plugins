---
name: nda-triage
description: Fast-triage an inbound NDA — mutual vs one-way, term, carve-outs, and red flags — with a sign / redline / escalate recommendation against your standard positions. Claude drafts; a qualified attorney reviews and approves. Trigger with "triage this NDA", "is this NDA ok to sign", "check this confidentiality agreement".
---

# NDA Triage

Quick, structured triage of an inbound non-disclosure agreement so routine ones move fast and risky ones get escalated.

> **Not legal advice.** Claude assists with a first-pass triage only. A qualified attorney must review and approve any sign / redline / escalate decision before it is acted on.

## What it does

Reads an inbound NDA, identifies whether it is mutual or one-way, extracts the term, permitted-use scope, and carve-outs, and checks it against your team's standard NDA positions. It surfaces red flags — non-mutual obligations, indefinite terms, missing standard exclusions, broad definitions, assignment or residuals traps — and gives a clear **sign / redline / escalate** recommendation for the attorney to confirm.

## Connectors it uses

| Category | Placeholder | What it adds |
| --- | --- | --- |
| Document management | `~~document management` | Pulls your standard NDA template and approved fallback terms |
| Knowledge base | `~~knowledge base` | Retrieves standard positions and prior NDA decisions |
| E-signature | `~~e-signature` | Routes an approved, attorney-cleared NDA for signature |

> **No connectors?** Paste the NDA text and Claude triages it against general NDA norms plus any standard positions you provide. Connect `~~document management` / `~~knowledge base` so it can compare against your live standard template automatically.

## How it works

1. **Take the NDA.** Read the pasted text or the named file.
2. **Classify.** Mutual vs one-way; who is disclosing; permitted purpose.
3. **Extract the key terms.** Term/duration, definition of Confidential Information, standard carve-outs (public, independently developed, lawfully received, required by law), return/destruction, and any residuals, non-solicit, or assignment clauses.
4. **Check against standard positions.** Connected: pull them from `~~document management` / `~~knowledge base`. Standalone: use the positions the user provides.
<!-- CUSTOMIZE: your standard NDA positions — e.g. mutual only, term ≤ 3 years, standard carve-outs required -->
5. **Recommend.** Output **Sign** (matches standard), **Redline** (fixable deviations, with suggested language), or **Escalate** (material risk / unusual terms) with reasons.
6. **Route.** Present to the attorney; on approval, route via `~~e-signature`. Nothing is signed without attorney approval.

**You approve before it goes out.** Claude recommends; the attorney decides and signs. Claude never executes an NDA on its own.

## Output

```markdown
# NDA Triage — [Counterparty]

**Type:** Mutual / One-way · **Term:** [X years] · **Triaged:** [date]
**Recommendation:** SIGN / REDLINE / ESCALATE
**Attorney sign-off:** ☐ pending

## Snapshot
- Disclosing party / Purpose / CI definition / Carve-outs: ...

## Red flags
| Item | Issue | Standard position | Suggested fix |
| --- | --- | --- | --- |
| Term | Indefinite | ≤ 3 years | Set 3-year term |
| Carve-outs | Missing "independently developed" | Required | Add standard exclusion |

## Why this recommendation
- ...

_Draft prepared by Claude. Not legal advice — attorney review and approval required._
```

## Customize this skill

- Set your standard NDA positions in step 4 (mutuality, max term, required carve-outs).
<!-- CUSTOMIZE: define what auto-qualifies for SIGN vs what must ESCALATE -->
<!-- CUSTOMIZE: name the attorney/role who approves before signature -->
- Point routing at your real `~~e-signature` workflow.
- Adjust the recommendation thresholds to your team's risk tolerance.

## Related skills

- **contract-review** — deeper review for full contracts, not just NDAs.
- **clause-library** — pull approved confidentiality and carve-out language.
- **risk-assessment** — when an NDA sits inside a larger, higher-stakes deal.
