---
name: contract-review
description: Review a contract against your team's playbook — summarize key terms, flag risky or non-standard clauses, and suggest redlines. Claude drafts; a qualified attorney reviews and approves. Trigger with "review this contract", "check this agreement against our playbook", "what's risky in this MSA".
---

# Contract Review

First-pass review of a contract against your team's standard positions, with a plain-English summary, a risk flag list, and suggested redlines.

> **Not legal advice.** Claude assists with a first-pass review only. A qualified attorney must review, correct, and approve every output before it is relied on, shared, or sent externally.

## What it does

Reads a contract you paste or point to, summarizes the key commercial and legal terms, and compares each material clause against your team's playbook of standard and fallback positions. It flags clauses that are risky, missing, or off-market — with attention to liability, indemnity, termination, auto-renewal, and IP — and drafts suggested redline language for the attorney to accept, adjust, or reject.

## Connectors it uses

| Category | Placeholder | What it adds |
| --- | --- | --- |
| Document management | `~~document management` | Pulls the current playbook, standard templates, and prior signed versions |
| Knowledge base | `~~knowledge base` | Retrieves negotiation guidance, approved fallback positions, and prior deal notes |
| Chat | `~~chat` | Shares the flag list with the deal team and routes escalations |

> **No connectors?** Paste the contract text and (optionally) your playbook or standard positions directly into the chat. Claude reviews against what you provide plus general contract-review practice. Connect `~~document management` / `~~knowledge base` so it can pull the live playbook automatically instead.

## How it works

1. **Take the contract.** Read the pasted text or the file the user names.
2. **Load the playbook.** Connected: pull the standard-positions playbook and any relevant template from `~~document management` / `~~knowledge base`. Standalone: use the positions the user pasted, or ask for the 3–5 rules that matter most.
3. **Summarize key terms.** Parties, term, value, renewal, governing law, and the commercial heart of the deal.
4. **Flag clauses.** Compare each material clause to the playbook and mark it standard / negotiate / escalate. Always check liability caps, indemnity, termination, auto-renew, and IP ownership/license.
<!-- CUSTOMIZE: list the exact clause types your team always reviews, and any deal-specific ones -->
5. **Suggest redlines.** Draft replacement or fallback language for each flagged clause, tied to the playbook position.
6. **Route for approval.** Present the summary + flags + redlines to the attorney. Nothing is sent to the counterparty until the attorney approves.

**You approve before it goes out.** Claude produces a draft review and draft redlines. A qualified attorney reviews and approves; the attorney (not Claude) sends anything to the counterparty.

## Output

```markdown
# Contract Review — [Counterparty] [Agreement Type]

**Reviewed:** [date] · **Reviewer (drafting aid):** Claude · **Attorney sign-off:** ☐ pending

## Key terms
- Parties / Term / Value / Renewal / Governing law: ...

## Flags (most material first)
| Clause | Position | Risk | Suggested redline |
| --- | --- | --- | --- |
| Limitation of liability | Off-market | High | Cap at 12 mo fees; carve-outs for... |
| Auto-renewal | Non-standard | Med | Add 60-day non-renewal notice |
| Indemnity | Missing IP indemnity | High | Add mutual IP indemnity... |

## Open questions for the attorney
- ...

_Draft prepared by Claude. Not legal advice — attorney review and approval required._
```

## Customize this skill

- Point step 2 at your real playbook location in `~~document management` / `~~knowledge base`.
- Edit the clause checklist in step 4 to match your team's standard review scope.
<!-- CUSTOMIZE: set your default liability cap, indemnity, and termination fallback positions -->
<!-- CUSTOMIZE: name the attorney or role who must sign off before any redline is sent -->
- Adjust the output template to match your team's review memo format.

## Related skills

- **nda-triage** — fast-triage inbound NDAs against standard positions.
- **clause-library** — retrieve the approved standard and fallback clauses this skill compares against.
- **risk-assessment** — assess overall legal risk of the deal the contract sits inside.
