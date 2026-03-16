---
name: board-update
description: When the user needs to write a monthly or quarterly investor update, prepare a board deck, or communicate company progress to stakeholders.
related: [process-docs, pitch-deck]
reads: [startup-context]
---

# Board Update

## When to Use

Activate when a founder needs to draft an investor update email, prepare a board meeting deck, or write a quarterly business review. This includes prompts like "write my monthly investor update," "prepare for our board meeting," "draft a quarterly recap," or "how do I communicate bad news to the board." Also activate for fundraising decks where market and vision framing is needed.

## Context Required

- **From startup-context:** company stage, fundraising history, board composition, key metrics (MRR, burn, runway, headcount), current strategic priorities, and previous update cadence.
- **From the user:** reporting period, key wins and losses, metric changes, specific topics requiring board input or approval, any sensitive issues to address, and whether this is an email update or a slide deck.

## Workflow

1. **Determine format and cadence** — Monthly email update (standard for seed/Series A, under 800 words), quarterly board deck (Series A onward, 20-30 slides, sent as pre-read 48 hours ahead), monthly condensed deck (8-12 slides), or ad-hoc update (one page, one topic, sent immediately for material events). Default to monthly email for early-stage.
2. **Collect the 11 sections** — Walk through each section of the framework below. Each section has a designated C-suite owner. For each, apply the "Headline - Data - Narrative - Ask/Next" structure.
3. **Lead with the headline** — Write a 1-3 sentence executive summary that captures the single most important takeaway. Boards see 10+ decks per quarter. Surface key messages by slide three. Some investors read only the summary.
4. **Apply the bad-news protocol** — If any section contains negative developments, use the transparent delivery framework. Never bury bad news. Boards find out eventually. Finding out late makes it worse.
5. **Add specific asks** — Every update ends with concrete, actionable requests. Name the person if possible. Investors who cannot help you cannot add value.
6. **Format for scanability** — Investors spend 3-5 minutes on updates. Bold key numbers, use tables for metrics, keep paragraphs to 2-3 sentences. Cap metrics dashboards at 6-8 KPIs with targets and status.

## Output Format

For email updates, output as markdown ready to paste into email. For board decks, output as structured markdown with one H3 per slide.

### The 11-Section Framework

| # | Section | Owner | What to Include |
|---|---------|-------|-----------------|
| 1 | **Executive Summary** | CEO | Three sentences: current state, major event, next direction |
| 2 | **Key Metrics Dashboard** | COO | 6-8 KPIs in table format with targets and status indicators |
| 3 | **Financial Update** | CFO | P&L summary, cash runway, burn multiple trends, plan variances |
| 4 | **Revenue & Pipeline** | CRO | ARR waterfall, NRR, pipeline stages, top deals with confidence levels |
| 5 | **Product Update** | CPO | Shipped features, upcoming work, user impact evidence, PMF signals |
| 6 | **Growth & Marketing** | CMO | CAC by channel, pipeline contribution, channel testing results |
| 7 | **Engineering & Technical** | CTO | Velocity trends, tech debt ratio, uptime, security status |
| 8 | **Team & People** | CHRO | Headcount vs plan, hiring pipeline, attrition, engagement scores |
| 9 | **Risk & Security** | CISO | Security controls status, compliance deadlines, incidents, top 3 risks |
| 10 | **Strategic Outlook** | CEO | Next quarter priorities ranked, board decisions needed, specific asks |
| 11 | **Appendix** | — | Detailed financials, full pipeline, retention charts, headcount breakdown |

Every section follows: **Headline - Data - Narrative - Ask/Next.**

## Frameworks & Best Practices

### The Four-Act Narrative Structure

Apply this to every section, especially when explaining variances:
1. **Prior targets** — what we said we would do
2. **Current reality** — what actually happened
3. **Gap explanation** — why (owned cause, not excuses)
4. **Remediation** — specific fixes with timeline

This structure works for both positive and negative scenarios.

### Transparent Bad-News Delivery

1. **State the fact plainly.** "We missed our Q3 revenue target by 22%." No euphemisms.
2. **Own the cause.** "Two enterprise deals worth $180K ARR slipped to Q4 due to procurement delays we did not anticipate." Do not lead with context or excuses.
3. **Demonstrate understanding.** Show the analysis that explains the root cause.
4. **Present specific fixes.** "We implemented procurement-tracking in our sales process and added 30 days of buffer to enterprise deal timelines."
5. **Update the forecast.** "Revised Q4 target is $X." Include confidence levels, not single-point estimates: "High confidence $2.6M, upside to $2.9M if two late-stage deals close."
6. **Ask for help if needed.** "A warm intro to their CFO would accelerate procurement."

Investors forgive bad quarters. They do not forgive founders who hide problems until they become crises.

### Metrics Presentation Rules

- **Always show trends.** Current vs. prior period vs. plan. A single number is meaningless.
- **Use consistent timeframes.** Do not mix monthly and annualized numbers in the same table.
- **Highlight variance.** Bold any metric that deviates more than 10% from plan in either direction.
- **Include unit economics.** CAC, LTV, and payback period tell the story top-line revenue cannot.
- **Show runway in months, not dollars.** "14 months at current burn" is more actionable than "$2.1M in the bank."
- **Revenue forecasts need confidence levels.** Never present a single-point estimate.
- **Provide one-sentence explanations for every variance from targets.**

### Cadence Guidelines

| Format | When | Length | Distribution |
|--------|------|--------|-------------|
| Monthly email | Seed through Series A | Under 800 words | First week of following month |
| Quarterly board deck | Series A onward | 20-30 slides | Pre-read 48 hours before meeting |
| Monthly condensed deck | Any stage | 8-12 slides | Metrics, financials, pipeline, risks |
| Ad-hoc update | Material events | 1 page, 1 topic | Immediately |
| Fundraising deck | Pre-raise | Market/vision focus | Closing ask structure |

### Common Mistakes

1. **Excessive length** — keep quarterly decks under 25-30 slides
2. **Metrics without targets** — every number needs a comparison point
3. **No narrative** — data without story is noise
4. **Buried bad news** — surface it in the first three slides
5. **Vague asks** — "any intros would be great" vs. "intro to VP Ops at Stripe"
6. **Unexplained variances** — every miss needs a one-sentence explanation
7. **Stale appendix** — update supporting data every cycle
8. **Deck designed for reading, not presenting** — slides should support conversation, not replace it
9. **Sending updates only when things go well** — creates suspicion during quiet periods
10. **All narrative, no data** — makes it impossible to track progress over time

## Related Skills

- `process-docs` — chain to create an SOP for the internal board-update preparation process, ensuring consistent quality each cycle.
- `pitch-deck` — chain when the board update reveals a need to begin fundraising or when the update doubles as a re-up deck for existing investors.

## Examples

### Example 1: Monthly investor email
**User:** "Write my February investor update. MRR hit $85K (up from $72K), we hired a VP Engineering, but we lost our largest customer."

**Good output excerpt:**
> **TL;DR:** February MRR grew 18% to $85K driven by strong mid-market expansion, but we lost Acme Corp ($12K/mo) due to budget restructuring outside our control. We hired Sarah Chen as VP Engineering (ex-Stripe). Net: ahead on product velocity, slightly behind on net revenue retention. 14 months runway remaining.
>
> **Key Metrics**
> | Metric | Feb | Jan | vs. Plan |
> |--------|-----|-----|----------|
> | MRR | $85K | $72K | +3% |
> | Net New ARR | $156K | $120K | +8% |
> | Gross Churn | $12K | $2K | **-$10K** |
> | Burn | $110K | $105K | On plan |
> | Runway | 14 mo | 15 mo | On plan |
>
> **On the churn:** Acme Corp's new CFO cut all software contracts under $50K ARR during a company-wide cost reduction. We had 30 days notice and attempted a reduced plan; they declined. This was not a product failure, but it exposes revenue concentration risk — Acme was 14% of MRR. We are diversifying our top-10 account exposure.
>
> **Asks**
> 1. Intros to mid-market fintech companies — specifically VP Operations or Head of Compliance contacts.
> 2. Referrals for a Senior Backend Engineer. JD attached.

### Example 2: Communicating a major miss
**User:** "We're going to miss our quarterly target by a lot. Help me write this update."

**Good output approach:** Open with the miss stated plainly in the executive summary. Quantify the gap. Explain root cause in 2-3 sentences using owned language, not excuses. Follow immediately with the remediation plan including timeline and revised forecast with confidence levels. Close with specific asks for help. Never let bad news be the last thing the reader sees — always end with forward momentum and concrete next steps.
