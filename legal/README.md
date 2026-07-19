# Legal

Speed up contract review, NDA triage, and compliance workflows for in-house legal teams. Draft legal briefs, organize precedent research, and manage institutional knowledge.

> **Not legal advice.** Every skill in this plugin is a drafting and triage aid. Claude assists; a qualified attorney reviews and approves before anything is relied on, sent, or signed. Nothing here is a substitute for counsel.

## What's inside

### Skills

| Skill | What it does |
| --- | --- |
| contract-review | Reviews a contract against your playbook — key-term summary, risk flags, and suggested redlines |
| nda-triage | Fast-triages an inbound NDA with a sign / redline / escalate recommendation |
| compliance-check | Checks a document, process, or request against a named policy/regulation and lists gaps and actions |
| risk-assessment | Assesses legal risk of an action or deal with a go / caution / no-go recommendation |
| clause-library | Maintains and retrieves approved standard clauses and fallback positions |

### Commands

| Command | What it does |
| --- | --- |
| `/legal:review-contract` | Runs contract-review on a contract you provide |
| `/legal:triage-nda` | Runs nda-triage on an inbound NDA |
| `/legal:compliance-check` | Runs compliance-check on a document against a named policy/regulation |

## Connectors

Every skill works standalone with pasted text and gets better when tools are connected. See **CONNECTORS.md** for the full mapping and how the `~~category` placeholders work. Categories used: `~~document management`, `~~knowledge base`, `~~chat`, `~~e-signature`, `~~email`, `~~calendar`.

## Customize for your team

- Replace the `~~category` placeholders' behavior by connecting your actual tools; the prose stays tool-agnostic.
- Edit each skill's `<!-- CUSTOMIZE -->` marks — playbook locations, standard positions, clause checklists, and risk scales.
- Name the attorney or role who must sign off in each skill before anything goes out.
- Point playbook and clause-library storage at your real `~~document management` / `~~knowledge base`.
- Adjust output templates to match your team's memo and review formats.
