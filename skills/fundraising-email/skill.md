---
name: fundraising-email
trigger: When the user wants to write an email to an investor — cold outreach, warm intro request, follow-up after a meeting, monthly investor update, or thank-you note. Also activates for "intro email", "investor email", "follow up with VC", or "investor update".
related: [pitch-deck, investor-research]
reads: [startup-context]
---

# Fundraising Email

## When to Use

- The founder needs to write a cold outreach email to an investor.
- The founder wants to draft a warm intro request (a "forwardable email").
- The founder needs a follow-up after an investor meeting.
- The founder is writing a monthly investor update.
- The founder wants to send a thank-you or round-closing notification.

## Context Required

From `startup-context`: company one-liner, stage, key traction metrics, fundraising status, and any notable social proof (investors, customers, press).

From the user: email type, recipient (investor name and firm), prior relationship context, and desired outcome (meeting, intro, materials review).

## Workflow

1. **Read startup context** — Pull the company narrative, metrics, and fundraising details from `.agents/startup-context.md`.
2. **Determine email type** — Classify as one of the five types below. Each has different structure, tone, and length.
3. **Draft the email** — Follow the type-specific template. Keep it short — investors scan, they don't read.
4. **Add personalization** — Include at least one specific reference to why this investor is a fit (thesis, portfolio company, blog post). Generic emails get ignored.
5. **Review against principles** — Check the draft against the quality checklist. Trim aggressively.
6. **Deliver the final draft** — Output subject line and email body, ready to copy-paste.

## Output Format

```
**To:** [Investor Name]
**Subject:** [Subject line]

[Email body]
```

For investor updates, output a longer structured email with sections (see type 4 below).

## Frameworks & Best Practices

### The Five Email Types

#### 1. Cold Outreach
**Goal**: Get a 30-minute meeting. **Length**: 5-7 sentences, under 150 words.
- **Line 1**: Why *this* investor specifically (1 sentence).
- **Lines 2-3**: What you do and for whom (no jargon).
- **Lines 4-5**: Strongest traction proof point — one number that makes them lean in.
- **Line 6**: Specific, low-commitment ask ("Would you have 30 minutes this week or next?").
- No attachments on first email. **Subject line formula**: `[Specific hook] — [Company Name]` (e.g., `"$40K MRR in 6 months, AI contract review — Lexara"`).

#### 2. Warm Intro Request (The Forwardable Email)
**Goal**: Make it effortless for your connector to intro you. **Two parts**:
- **Note to connector** (2-3 sentences): "Would you be willing to introduce me to [Partner] at [Firm]? Short blurb below you can forward directly."
- **Forwardable blurb** (4-6 sentences): Written so the connector sends it as-is. Include what the company does, strongest metric, why this firm is relevant, and what you're looking for. If the connector has to rewrite it, they won't send it.

#### 3. Follow-Up After Meeting
**Goal**: Maintain momentum, deliver materials, set next steps. **Length**: 4-8 sentences.
- Thank them and reference one specific thing discussed. Attach requested materials. Address any open question. Propose a specific next step with a date. **Send within 3 hours** — speed signals competence.

#### 4. Monthly Investor Update
**Goal**: Keep current and prospective investors informed. **Length**: 300-500 words.
- **Highlights**: Top 3 wins (metrics-first).
- **KPIs**: Table with this month, last month, MoM change.
- **Challenges**: 1-2 honest struggles (invites help; investors respect candor).
- **Asks**: 1-3 concrete requests (intros to specific customer types, candidates for a role).
- **What's Next**: Top 2-3 priorities for next month.
- Send on the same day each month. Monthly updates are the #1 way to convert a "not yet" into a future "yes".

#### 5. Thank-You / Round Closing Note
**Goal**: Maintain the relationship. **Length**: 3-5 sentences.
- If invested: genuine thanks, confirm logistics, add to update list.
- If passed: thank them, leave the door open, ask if they want monthly updates. Never burn bridges — the investor who passes on seed may lead your Series A.

### Core Principles

1. **Brevity wins** — Investors get 50-100 inbound emails weekly. Over 200 words in a cold email gets skimmed.
2. **Specificity beats superlatives** — "$42K MRR growing 25% MoM" beats "fast-growing revenue".
3. **Social proof early** — Recognizable customer, investor, or accelerator in the first two lines.
4. **One clear CTA** — Every email gets exactly one ask.
5. **Personalization is mandatory** — Reference their thesis, portfolio, or writing. Doubles response rates.
6. **Subject lines are headlines** — Lead with your best metric or most surprising fact.
7. **Send Tuesday-Thursday, 8-10am investor's timezone** — Open rates drop on Mondays and Fridays.

### What Not to Do

- No "disruptive", "revolutionary", "game-changing", or "the Uber of X".
- No NDAs. No reputable investor signs them for startup pitches.
- Don't email multiple partners at the same firm. They compare notes.
- Don't follow up more than twice without new information.
- Don't CC multiple investors on the same email.

## Related Skills

- `pitch-deck` — the email drives the meeting; the deck carries the meeting
- `investor-research` — research determines who to email and what personalization to use

## Examples

**Example prompt**: "Write a cold email to Sarah Chen at Greylock. We're an AI code review startup with $55K MRR."

**Good output**:

> **Subject:** $55K MRR — AI code review, 4 enterprise customers — CodeLens
>
> Hi Sarah,
>
> Your investment in Developer Infrastructure at Greylock — particularly the thesis in your "Next Wave of DevTools" post — is why I wanted to reach out to you specifically.
>
> I'm the CEO of CodeLens. We automate code review for enterprise engineering teams using LLMs, catching security vulnerabilities and logic errors that slip past existing tools.
>
> We launched 5 months ago: $55K MRR, 4 enterprise customers (two Fortune 500), growing 30% MoM. We're raising a $3M seed round.
>
> Would you have 30 minutes this week or next?

**Example prompt**: "Help me write this month's investor update."

**Good output approach**: Pull metrics from startup context, ask the founder for this month's highlights and challenges, then produce the structured update. Flag any missing or stale KPIs.
