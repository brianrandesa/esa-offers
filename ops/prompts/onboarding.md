# New Client Onboarding — Build the ClickUp Board + Kickoff

Use this prompt when a new client closes. Inputs you need before starting.
If client name or event date is missing, post what's missing to #esa-admin
and stop. Do not build a partial board.

- **Client name** (used for the board/list name)
- **Close date** (Day 0 — defaults to today)
- **Event date** (drives all due-date math)
- **Event type** (virtual or live)
- **Contract end date** (defaults to close date + 90 days unless specified)

## Step 1 — Build the ClickUp client board

1. Read `ops/checklist.csv`. It contains the full 15-phase, 165-task client
   journey with columns: Phase #, Phase Name, Timeline, Phase Owner, Gate to
   Advance, Task, Task Owner, Track.
2. In the ESA ClickUp workspace, create a new list/board named for the
   client (match the naming convention of existing client boards — check the
   workspace hierarchy first).
3. Write a machine-readable block into the list description (the daily
   sweep and Friday report read their dates from here):

   ```
   CLOSE_DATE: YYYY-MM-DD | EVENT_DATE: YYYY-MM-DD | EVENT_TYPE: virtual/live | CONTRACT_END: YYYY-MM-DD
   ```

   `CONTRACT_END` is close date + 90 days unless specified.
4. Create one task per CSV row, grouped by phase (use the phase as the
   section/status grouping or a `Phase N — Name` prefix, matching how other
   client boards are structured). Include the Gate to Advance in each
   phase's first task description or as a phase-level task so the gate is
   visible.
5. **Due dates are calculated backward from the client's event date**, using
   each phase's Timeline column:
   - "Day X–Y" timelines anchor forward from the close date (Day 0), but
     verify the resulting schedule still lands before the event date. If the
     event date is too close for the standard Day 0–20 build, compress
     proportionally and flag the compression in the kickoff summary.
   - "T-N" references (e.g., reactivation at T-14, client ad account at T-7)
     anchor backward from the event date.
   - "Event day" tasks get the event date itself; "T+N" post-event tasks
     anchor forward from the event date.
   - Phase 14 (Renewal) anchors to 30 days before contract end; Week 10 of
     the engagement is the mandatory renewal-conversation date.
6. **A2P tasks are Day 0 priority.** Every task mentioning A2P (collection
   of A2P business details in Phase 1, A2P 10DLC submission in Phase 3) gets
   urgent/highest priority and a due date no later than Day 2. The 72hr+
   approval clock is the #1 bottleneck — these never slip.
7. Assign task owners per the CSV's Task Owner column using the ESA owner
   mapping in `CLAUDE.md` (CSM=Michaela, Tech=Shah, Funnel=Hamza, Auto=Jawad,
   Ads=Mal/Zoe, Content=Sohaib, Sales=Emanuela/closers, Data=Kim & Kim).
   Tag `Client`-owned tasks so they're filterable — client delays move the
   event date day-for-day, not our timeline.
8. Apply the Track column as tags: `M` = marketing track, `S` = sales track,
   blank = both.

## Step 2 — Post the kickoff summary to Slack

Post to **#esa-admin** a kickoff summary containing:

- Client name, close date, event date, event type
- Link to the new ClickUp board
- The milestone schedule by phase (phase name → due window)
- **Owner tags by milestone**: tag each phase owner on their phase
  (Michaela on Onboarding/CSM phases, Shah on Tech Setup, Hamza on Funnel
  Build, Jawad on Automations, Mal/Zoe on Creative & Launch, Sohaib on
  Content, Emanuela on Sales phases, Kim & Kim on Data/Reporting)
- Call out explicitly: A2P submission deadline (Day 2 at the latest) and the
  ads-live deadline (within 72 hours of close)
- Reminder that the scope document is due to the client within 24 hours

## Step 3 — Generate the scope document

Follow `ops/prompts/scope-doc.md`, then include the scope doc link in the
kickoff Slack post from Step 2.

## Guardrails

- Don't create duplicate boards — search the workspace for the client name
  first; if a board already exists, stop and report instead.
- If client name or event date is missing, post what's missing to
  #esa-admin and stop — never build a partial board or guess dates.
- All ESA rules in `CLAUDE.md` apply.
