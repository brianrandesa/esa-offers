# Friday Client Report — Weekly Updates for Michaela

Run every Friday, early enough that Michaela can deliver updates the same
day. Output: one drafted update per active client + an internal flag list.

## Step 1 — Compile per-client completions and numbers

For every active client board in the ESA ClickUp workspace, first read the
machine-readable block from the list description:

```
CLOSE_DATE: YYYY-MM-DD | EVENT_DATE: YYYY-MM-DD | EVENT_TYPE: virtual/live | CONTRACT_END: YYYY-MM-DD
```

Use these dates — do not infer them from task data. If a board is missing
the block, flag it as a setup gap. Then compile:

1. **Completed this week:** all tasks closed in the last 7 days, grouped by
   phase, in plain client-facing language (what got done, not internal task
   names — e.g., "your registration funnel went live" not "Publish funnel
   live").
2. **The numbers:** read the most recent weekly scorecard in the ESA
   Reports folder in Google Drive; if none exists for this client, flag the
   gap to Kim & Kim instead of estimating. If a client is pre-launch,
   report build progress (phases complete / total) instead.
3. **Up next:** the next phase or milestone and what (if anything) we're
   waiting on from the client — with the reminder that client delays move
   their event date day-for-day.

## Step 2 — Draft the Friday updates for Michaela

For each client, draft a short update **in Michaela's voice, ready to send**
(she delivers it — don't post anything to clients directly):

- Warm one-line opener
- ✅ Completed this week (bullets)
- 📊 The numbers (only metrics that exist for this client's stage)
- ⏭️ What's next + anything we need from them
- Close with the standing invitation to the weekly 1:1

Deliver all drafts to Michaela as a single threaded message in
**#esa-admin** (not a DM) — one top-level message, one thread reply per
client.

## Step 3 — Flag renewal-window clients

Separately, as an internal flag list for Michaela:

- **Clients at Week 10 of their engagement** (counted from `CLOSE_DATE`) —
  the Week 10 renewal conversation is mandatory for every client; flag
  whether it's been scheduled/held, and if not, say so explicitly.
- **Clients within 30 days of `CONTRACT_END`** — Phase 14 (Renewal &
  Ascension) should be active: results presentation, ascension offer
  (ongoing webinars $3K/mo, ads + data $2,500/mo, or live event),
  testimonial + referral asks. Note which Phase 14 tasks are still open.

## Guardrails

- Drafts only — Michaela reviews and sends; never message a client directly.
- Don't invent numbers; if data is missing for a client, flag the gap to
  Kim & Kim instead of estimating.
- All ESA rules in `CLAUDE.md` apply.
