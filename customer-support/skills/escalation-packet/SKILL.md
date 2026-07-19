---
name: escalation-packet
description: Package a customer issue for engineering or product — repro steps, impact, affected customers, links, and a crisp summary — then file it into the project tracker and notify the right channel. Trigger with "escalate this ticket", "build an escalation packet", "file this to engineering".
---

# Escalation Packet

Turn a messy ticket into a clean, actionable escalation engineering can pick up cold.

## What it does
Assembles everything an engineering or product team needs to act on an issue: clear repro steps, blast radius, affected customers, source links, and a one-paragraph summary. It files the packet into your ~~project tracker and posts a heads-up in ~~chat so nothing stalls in a queue.

> **You approve before it goes out.** Claude drafts the packet and shows you the tracker item and chat message. A human confirms before it's filed or posted.

## Connectors it uses

| Category | Placeholder | What it adds |
| --- | --- | --- |
| Helpdesk | `~~helpdesk` | Pulls the ticket, thread, and any linked duplicate tickets |
| Project tracker | `~~project tracker` | Files the issue as a ticket/task with the packet as the description |
| Chat | `~~chat` | Notifies the engineering/product channel with a link and summary |
| CRM | `~~CRM` | Adds account tier and revenue so impact is weighted correctly |

> **No connectors?** Paste the ticket details. Claude produces the full packet as markdown you can copy into your tracker and paste into chat manually.

## How it works
1. **Gather the source.** Connected: pull the ticket and related tickets from ~~helpdesk. Standalone: use pasted details.
2. **Write clean repro steps.** Numbered, minimal, with expected vs. actual result and environment (plan, browser, version).
3. **Quantify impact.** How many customers, which tiers (from ~~CRM), how often, and whether there's a workaround.
<!-- CUSTOMIZE: set what counts as high impact — e.g. any P1, >5 accounts, or any Enterprise account -->
4. **Collect links.** Ticket URL, screenshots, logs, related tickets, prior escalations.
5. **File it.** Create a ~~project tracker item using your escalation template and required fields.
<!-- CUSTOMIZE: name your tracker project/board, issue type, and required fields (severity, component, owner) -->
6. **Notify.** Post a short summary + link in the right ~~chat channel and tag the on-call/triage owner.
<!-- CUSTOMIZE: name the channel and who to tag for each product area -->

## Output
```markdown
**Escalation: Export times out on large reports**

**Summary:** Pro and Enterprise users can't export reports above ~50k rows; export
spins then fails silently. Started after last week's release. No workaround for large
date ranges.

**Repro:**
1. Open a report with >50k rows
2. Click Export → PDF
3. Expected: file downloads · Actual: spinner, then "Export failed" toast

**Impact:** 7 accounts affected (2 Enterprise, 5 Pro) · recurring · no workaround
**Environment:** Web app v3.4.1, all browsers

**Links:** Ticket #4821 · related #4790, #4805 · console log attached

**Filed:** TRACKER-1188 (Bug · Exports · P2)
**Notified:** #eng-triage — @export-owner
```

## Customize this skill
- Define your **high-impact thresholds** in step 3.
- Set the **tracker project, issue type, and required fields** in step 5.
- Name the **channel and owner to tag** per product area in step 6.

## Related skills
- **ticket-triage** — decide whether a ticket should escalate at all.
- **customer-context** — confirm account tier and history before escalating.
- **draft-response** — tell the customer you've escalated and set expectations.
