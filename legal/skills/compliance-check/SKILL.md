---
name: compliance-check
description: Check a document, process, or request against a named policy or regulation and list the gaps and required actions, citing the specific policy sections. Claude assists; a qualified attorney reviews and approves — this is not a substitute for counsel. Trigger with "check this against [policy]", "is this compliant with [regulation]", "run a compliance check".
---

# Compliance Check

Structured gap analysis of a document, process, or request against a named policy or regulation, with specific citations and required actions.

> **Not legal advice.** Claude assists with a first-pass compliance review only and is **not a substitute for counsel**. A qualified attorney must review, verify citations, and approve before any conclusion is relied on.

## What it does

Takes the item to check (a document, a described process, or a request) and a named policy or regulation, then maps each relevant requirement to what the item does or fails to do. It reports compliant items, gaps, and unclear areas — each tied to the specific policy section — and lists the concrete actions needed to close each gap.

## Connectors it uses

| Category | Placeholder | What it adds |
| --- | --- | --- |
| Knowledge base | `~~knowledge base` | Pulls the current internal policy text and prior interpretations |
| Document management | `~~document management` | Retrieves the regulation, controls matrix, or the document under review |
| Chat | `~~chat` | Shares findings with the owner and tracks remediation |

> **No connectors?** Paste the item to check and the policy/regulation text (or name the regulation) and Claude works from that plus general knowledge of the named rule. Connect `~~knowledge base` / `~~document management` so it can pull the authoritative, current policy text automatically. Always confirm you are checking against the current version.

## How it works

1. **Take the inputs.** The item to check and the named policy or regulation.
2. **Load the source of truth.** Connected: pull the current policy/regulation from `~~knowledge base` / `~~document management`. Standalone: use the text the user pastes or the named rule.
<!-- CUSTOMIZE: list the policies and regulations your team checks against most often -->
3. **Map requirements.** Break the policy into its testable requirements/sections.
4. **Assess each.** Mark Compliant / Gap / Unclear, quoting or citing the specific section for each.
5. **List required actions.** For every gap, state the concrete step needed to close it and who owns it.
6. **Flag for counsel.** Present findings to the attorney; escalate anything ambiguous or high-stakes.

**You approve before it goes out.** Claude drafts findings and cites sections; a qualified attorney verifies the citations and interpretation and approves before anyone acts or communicates externally.

## Output

```markdown
# Compliance Check — [Item] vs [Policy/Regulation vX]

**Checked:** [date] · **Attorney sign-off:** ☐ pending

## Summary
- Overall: Compliant / Gaps found / Needs counsel
- Policy version/source: ...

## Findings
| Requirement (§) | Status | Evidence | Required action | Owner |
| --- | --- | --- | --- | --- |
| § 4.2 Data retention | Gap | No deletion schedule | Add 90-day purge | IT |
| § 6.1 Consent | Compliant | Consent captured at signup | — | — |

## Escalate to counsel
- ...

_Draft prepared by Claude. Not legal advice and not a substitute for counsel — attorney review and approval required._
```

## Customize this skill

- Populate step 2 with your real policy/regulation locations in `~~knowledge base` / `~~document management`.
<!-- CUSTOMIZE: your citation format (e.g. "§ 4.2" vs "Article 6(1)(a)") -->
<!-- CUSTOMIZE: who owns remediation actions and who must sign off before external reporting -->
- Edit the status labels (Compliant / Gap / Unclear) to match your controls language.
- Add a version-check reminder if your policies change frequently.

## Related skills

- **risk-assessment** — weigh the legal risk of a gap before deciding how to remediate.
- **contract-review** — when the item under review is a contract clause.
- **clause-library** — pull approved compliant language for common requirements.
