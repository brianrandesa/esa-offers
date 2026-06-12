# Scope Document Generator — v1 Draft from the Sales Call

Runs as part of new client onboarding, after the ClickUp board is built.
Output: a Google Doc draft for Michaela to confirm at kickoff. This is a
DRAFT — the kickoff call is where scope gets confirmed out loud.

## Step 1 — Pull the sales call

Search Fathom for meetings in the last 14 days matching the client's name
(try contact name AND company name). Pick the most recent sales call.
Pull the summary and transcript.

If no recording is found: still generate the doc from the trigger payload
and checklist defaults, and add a banner at the top: "⚠️ No sales call
recording found — scope below is from standard offer terms only. Michaela:
confirm all promises at kickoff." Flag the same in the Slack post.

## Step 2 — Draft the scope document

Create a Google Doc named "[Client Name] — Scope of Work — [close date]"
in a folder named "[Client Name]" inside the ESA Clients folder in Drive
(create the client folder if it doesn't exist). Structure:

1. ENGAGEMENT SUMMARY — client, offer + price from payload, close date,
   event date, event type, contract end date
2. WHAT WE'RE BUILDING — the system: GHL build, funnel, automations + AI
   agent, ad campaigns, sales enablement. Pull specifics promised on the
   sales call (e.g., "Brian mentioned the VSL edit is included").
3. WHAT YOUR TEAM EXECUTES — ESA is Done-With-You: the client's team runs
   sales calls, records footage, approves within 48h windows, shows up to
   weekly strategy calls. List their checklist-owned tasks (onboarding
   form, access, domain, ad payment method, footage, approvals).
4. TIMELINE & MILESTONES — phase schedule from the ClickUp board dates,
   with the ad launch date called out in bold.
5. WHAT'S NOT IN SCOPE — anything from the sales call explicitly excluded,
   plus standing exclusions. If the transcript shows the client assuming
   something we don't do, name it here plainly.
6. PROMISES MADE ON THE CALL — direct list of commitments from the closer,
   quoted or closely paraphrased, with a note: "confirmed at kickoff on
   [date]" left blank for Michaela to fill.
7. KEY DATES — A2P submission (Day 2 max), ads live (72hr target),
   week 10 renewal conversation, contract end.

Tone: clear, warm, direct. No legalese, no corporate filler. This is a
"here's exactly what happens next" document for a client who just paid
$15K and wants certainty.

## Guardrails

- Draft only. Never send to the client. Michaela reviews, confirms at
  kickoff, and delivers.
- Never quote the sales transcript in ways that reveal sales methodology
  or pricing tactics — extract promises and scope, nothing else.
- If payload and sales call conflict (e.g., different event dates), use
  the payload and flag the conflict in the doc banner and Slack post.
- Section 6 promises must come from the actual transcript. If a promise
  is ambiguous, list it under "needs confirmation at kickoff" rather
  than asserting it.
