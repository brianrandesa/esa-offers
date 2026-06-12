# ESA — Event Sales Agency

This repo is the automation backbone for ESA's client fulfillment. The
canonical A→Z client journey lives in `fulfillment-checklist.html` (the
`phases` JS array: 15 phases, 165 tasks) and is exported to
`ops/checklist.csv`. Routine operational prompts live in `ops/prompts/`.

## Non-negotiable ESA rules

These rules override everything else. Apply them to any task touching client
fulfillment, scheduling, reporting, or automation.

1. **A2P 10DLC is submitted Day 0–2.** The 72hr+ carrier approval clock is
   the #1 bottleneck in the entire journey. Nothing that depends on SMS can
   move until it clears, so the submission can never slip.
2. **Ads live within 72 hours of close.** Any client 7+ days without ads
   live is an **EMERGENCY** — flag it above everything else, before any
   other item in any report, brief, or sweep.
3. **Client delays move THEIR event date day-for-day, never our timeline.**
   If a client is late on an approval, asset, or access item, their event
   date shifts by the same number of days. ESA's internal schedule does not
   absorb client slippage.
4. **Everything is tracked in GHL.** No outside checkout or landing pages —
   ever. This protects revenue attribution.
5. **Every new client gets a scope document within 24 hours** of signing.
6. **Daily fulfillment standup is 10:30am ET.** Briefs and sweeps that feed
   it must be ready before then.
7. **The Week 10 renewal conversation is mandatory for every client.** No
   exceptions, no skips.

## Owner mapping

| Role / Function | Owner |
|---|---|
| CSM | Michaela |
| Tech | Shah |
| Funnel | Hamza |
| Auto (automations) | Jawad |
| Ads | Mal / Zoe |
| Content | Sohaib |
| Sales | Emanuela / closers |
| Data | Kim & Kim |

When a checklist task owner is `Both`, it's shared between ESA and the
client. When it's `Client`, the client owns it — and rule 3 applies if they
delay.

## Key files

- `fulfillment-checklist.html` — canonical client journey (source of truth)
- `ops/checklist.csv` — flat export of the journey for building client boards
- `ops/prompts/onboarding.md` — build a new client's ClickUp board + kickoff
- `ops/prompts/daily-sweep.md` — morning sweep of all active client boards
- `ops/prompts/friday-report.md` — weekly client update compilation

If `fulfillment-checklist.html` changes, regenerate `ops/checklist.csv` from
the `phases` array — the CSV must never drift from the HTML.
