---
description: Review a contract against your playbook — summary, risk flags, and suggested redlines.
argument-hint: "[contract file or paste]"
---

# Review Contract

Runs the **contract-review** skill on the contract you provide.

## Instructions

1. Take the contract from `$ARGUMENTS` — a file path, a link, or pasted text. If nothing is provided, ask for the contract.
2. Run the **contract-review** skill: load the team playbook from `~~document management` / `~~knowledge base` if connected (otherwise use the standard positions the user provides), then summarize key terms and flag risky or non-standard clauses — liability, indemnity, termination, auto-renew, IP.
3. Draft suggested redlines tied to the playbook position for each flagged clause.
4. Present the summary, flags, and redlines for the attorney to review. Do not send anything to the counterparty.
5. Close with the reminder: draft prepared by Claude, not legal advice — a qualified attorney must review and approve.
