---
description: Summarize what you missed across chat and email since a given time.
argument-hint: "[since when, e.g. 'yesterday']"
---

# Catch Up

Summarizes activity you missed across ~~chat and ~~email. Uses the **daily-brief** skill's "needs a reply" logic to flag what's actually waiting on you.

## Instructions

1. Read `$ARGUMENTS` for the time window (e.g. "yesterday", "since Friday", "last 3 days"). Default to the last 24 hours if empty.
2. Scan ~~chat and ~~email over that window. Group by conversation or sender; skip newsletters, automated notices, and pure FYIs.
3. Separate **needs a reply from you** from **just context**. For each reply item, note who's waiting and on what.
4. If no tools are connected, ask the user to paste the threads to summarize.
5. Return a short digest: what happened, what needs your reply, and anything time-sensitive. Offer to draft replies — the user approves before anything sends.
