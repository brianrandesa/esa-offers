# Daily Fulfillment Sweep — Standup Brief

Run every weekday morning. The brief must be posted to **#esa-admin**
**by 10:00am ET**, ahead of the 10:30am ET fulfillment standup.

## Step 1 — Scan all active client boards

Pull every active client board/list from the ESA ClickUp workspace (skip
archived/off-boarded clients). For each client, read the machine-readable
block from the list description:

```
CLOSE_DATE: YYYY-MM-DD | EVENT_DATE: YYYY-MM-DD | EVENT_TYPE: virtual/live | CONTRACT_END: YYYY-MM-DD
```

Use these dates — do not infer them from task data. If a board is missing
the block, flag it in the brief as a setup gap. Then determine each
client's current phase and task statuses.

## Step 2 — Flag, in this order

1. **🚨 EMERGENCIES — clients 7+ days past close without ads live.** This
   outranks everything. Check the Phase 7 launch tasks ("Launch — Campaign
   1/2/3"); if none are complete and the close date is 7+ days ago, the
   client is an emergency. List these first, with days-since-close and the
   blocking task/owner. (Standard is ads live within 72 hours of close —
   also call out clients in the 3–7 day warning zone.)
2. **A2P misses past Day 2.** Any client whose "SUBMIT A2P 10DLC" task is
   incomplete more than 2 days after close. The 72hr+ approval clock is the
   #1 bottleneck; every day unsubmitted pushes everything downstream.
3. **Overdue client-owned tasks.** Tasks with owner `Client` past their due
   date (onboarding form, access, approvals, footage, domain, payment
   method, etc.). For each, note days overdue and the rule: client delays
   move THEIR event date day-for-day — state the new implied event date.
4. **Blocked phase gates.** Clients stuck at a phase gate (the "Gate to
   Advance" condition unmet while the next phase's window has started).
   Name the gate, the unmet tasks, and the owner who can unblock it.

## Step 3 — Post the standup brief to #esa-admin

Format:

- **Header:** date + count of active clients swept
- **🚨 Emergencies** (if any) — each tagged to Mal/Zoe (Ads) and Michaela
  (CSM), with days-since-close
- **A2P misses** — tagged to Shah (Tech)
- **Client-overdue items** — tagged to Michaela (CSM) to chase, with the
  day-for-day event-date impact
- **Blocked gates** — tagged to the phase owner per the `CLAUDE.md` owner
  mapping
- **All clear** section listing clients with nothing flagged (one line)

Keep it scannable — one line per flag, link each to its ClickUp task. If
there are zero flags across the board, still post the brief saying so.

## Guardrails

- Never skip the post; the standup depends on it.
- Emergencies always go first, regardless of how the rest is ordered.
- Don't mark anything resolved yourself — the sweep reports, owners act.
- All ESA rules in `CLAUDE.md` apply.
