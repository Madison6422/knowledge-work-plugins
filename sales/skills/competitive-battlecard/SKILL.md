---
name: competitive-battlecard
description: Build a battlecard for a competitor you're up against — positioning, their strengths and weaknesses, landmines to set, and objection handling. Pulls from web research plus competitive intelligence and your knowledge base when connected. Trigger with "build a battlecard for [competitor]", "how do I beat [competitor]", "competitive prep against [vendor]".
---

# Competitive Battlecard

Get ready to win against a specific competitor with a one-page, sales-ready battlecard.

## What it does
Builds a focused battlecard for a competitor you're facing in a deal: how they position, where they're genuinely strong, where they're weak, the landmines you can set early, and crisp responses to the objections their reps will raise. Always works from web research, and gets sharper with competitive intelligence and your own internal knowledge base.

## Connectors it uses
| Category | Placeholder | What it adds |
| --- | --- | --- |
| Competitive intelligence | `~~competitive intelligence` | Traffic, positioning shifts, and market signals on the competitor |
| Knowledge base | `~~knowledge base` | Your team's internal win/loss notes and approved counters |

> **No connectors?** Name the competitor and Claude builds the card from public web research. Connectors add market signal and, importantly, your own team's proven counters and win/loss learnings.

## How it works
1. Take the competitor you name (and the deal context, if you share it).
2. **Web research (always):** summarize their positioning, target market, pricing signals, and recent moves.
3. **Connected — competitive intelligence:** if `~~competitive intelligence` is available, add traffic trends and positioning shifts.
4. **Connected — knowledge base:** if `~~knowledge base` is available, fold in your team's win/loss notes and approved messaging so counters stay on-brand.
5. **Assemble the card:** strengths, weaknesses, landmines to set, and objection handling — each response short enough to use live on a call.
<!-- CUSTOMIZE: state your own differentiators so "landmines" plant questions only you win -->

## Output
```markdown
# Battlecard: <You> vs <Competitor>
**Their positioning:** <one-liner> · **Best against:** <where you win> · **Watch out:** <where they win>

## Their strengths
- <strength> → <how we neutralize it>

## Their weaknesses
- <weakness> → <how we exploit it>

## Landmines to set
- "<question to plant that favors us>"

## Objection handling
| They say | You say |
| --- | --- |
```

## Customize this skill
- Add your differentiators and proof points under step 5.
<!-- CUSTOMIZE: keep a list of competitors and refresh each card as the market moves -->
- Paste your approved competitive messaging so responses stay compliant.
<!-- CUSTOMIZE: note any claims legal has told you NOT to make about competitors -->

## Related skills
- **call-prep** — bring the battlecard into a specific competitive call.
- **account-research** — see whether a competitor is already in the account.
- **draft-outreach** — write displacement messaging against an incumbent.
