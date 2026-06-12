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

1. NEVER create, modify, or add tasks to any folder or list whose name
   contains "TEMPLATE". The template is read-only reference.
2. Create a NEW folder in the Client Success Dept space named per the
   existing client convention (e.g. ess-26-[client-slug]). Inside it,
   create a list named "Launch Roadmap".
3. Create EXACTLY one task per row of ops/checklist.csv — 165 tasks.
   Never combine multiple rows into one task or move tasks into a
   description. Phase gates go in the description of that phase's FIRST
   task only.
4. Task descriptions use real markdown line breaks. Never write literal
   "\n" characters.
5. Group by phase using the same convention as existing boards
   ("01 · Onboarding & Access" etc.).
6. EVERY task gets a due date from the date math (Day X-Y forward from
   close, T-N back from event, T+N forward from event). Zero undated
   tasks allowed.
7. A2P tasks: priority Urgent, due no later than Day 2. Phase-gate
   first-tasks: priority High.
8. Resolve every assignee with the resolve_assignees tool per the
   CLAUDE.md owner mapping. Client-owned tasks: tag "client", assign
   to the CSM.
9. Write the date block into the list description:

   ```
   CLOSE_DATE: YYYY-MM-DD | EVENT_DATE: YYYY-MM-DD | EVENT_TYPE: virtual/live | CONTRACT_END: YYYY-MM-DD
   ```

   `CONTRACT_END` is close date + 90 days unless specified. The daily
   sweep and Friday report read their dates from this block.
10. SELF-AUDIT before Slack: count tasks created, count tasks with due
    dates, count tasks with assignees. If any count is wrong, fix it
    before posting. Include the three counts in the kickoff post.

## Step 2 — Generate the scope document

Follow `ops/prompts/scope-doc.md`. The scope doc link goes into the
kickoff Slack post in Step 3.

## Step 3 — Post the kickoff summary to Slack

Post to **#esa-admin** a kickoff summary containing:

- Client name, close date, event date, event type
- Link to the new ClickUp board
- Link to the scope doc draft from Step 2
- The milestone schedule by phase (phase name → due window)
- **Owner tags by milestone**: tag each phase owner on their phase
  (Michaela on Onboarding/CSM phases, Shah on Tech Setup, Hamza on Funnel
  Build, Jawad on Automations, Mal/Zoe on Creative & Launch, Sohaib on
  Content, Emanuela on Sales phases, Kim & Kim on Data/Reporting)
- Call out explicitly: A2P submission deadline (Day 2 at the latest) and the
  ads-live deadline (within 72 hours of close)
- Reminder that the scope document is due to the client within 24 hours

## Guardrails

- Don't create duplicate boards — search the workspace for the client name
  first; if a board already exists, stop and report instead.
- If client name or event date is missing, post what's missing to
  #esa-admin and stop — never build a partial board or guess dates.
- All ESA rules in `CLAUDE.md` apply.
