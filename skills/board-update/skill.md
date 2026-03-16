---
name: board-update
trigger: When the user needs to write a monthly or quarterly investor update, prepare a board deck, or communicate company progress to stakeholders.
related: [process-docs, pitch-deck]
reads: [startup-context]
---

# Board Update

## When to Use
Activate when a founder needs to draft an investor update email, prepare a board meeting deck, or write a quarterly business review for stakeholders. This includes prompts like "write my monthly investor update," "prepare for our board meeting," "draft a quarterly recap for investors," or "how do I communicate bad news to the board."

## Context Required
- **From startup-context:** company stage, fundraising history, board composition, key metrics (MRR, burn, runway, headcount), current strategic priorities, and previous update cadence.
- **From the user:** reporting period, key wins and losses, metric changes, specific topics requiring board input or approval, any sensitive issues to address, and whether this is an email update or a slide deck.

## Workflow
1. **Determine format** — Ask whether this is a monthly email update (most common for seed/Series A), a quarterly board deck (formal, with pre-read), or a mid-cycle ad-hoc update (triggered by a specific event). Default to monthly email for early-stage companies.
2. **Collect the 11 sections** — Walk through each section of the framework below. For each, apply the "Headline - Data - Narrative - Ask" structure.
3. **Lead with the headline** — Write a 1-2 sentence executive summary at the top that captures the single most important takeaway. Investors read this first; some read only this.
4. **Apply the bad-news protocol** — If any section contains negative developments, use the transparent delivery framework (see below). Never bury bad news.
5. **Add specific asks** — Every update should end with concrete requests. Investors who cannot help you cannot add value. Make it easy for them.
6. **Format and send** — Structure for scanability. Investors spend 3-5 minutes on updates. Bold key numbers, use tables for metrics, keep paragraphs to 2-3 sentences.

## Output Format
A structured update following the 11-section framework. For email updates, output as markdown ready to paste into email. For board decks, output as structured markdown with one H3 per slide.

### The 11-Section Framework

| # | Section | What to Include | Time Allocation |
|---|---------|-----------------|-----------------|
| 1 | **TL;DR / Headline** | 2-3 sentence summary of the period. One clear takeaway. | 3 lines max |
| 2 | **Key Metrics Dashboard** | MRR, growth rate, burn, runway, CAC, LTV, churn, NPS. Show vs. prior period and vs. plan. | Table format |
| 3 | **Revenue & Growth** | Revenue trajectory, pipeline, notable deals won/lost, expansion revenue. | 1-2 paragraphs |
| 4 | **Product & Engineering** | What shipped, what is in progress, what slipped and why. Link to roadmap. | Bullet list |
| 5 | **Customers & Market** | New logos, churn events, market shifts, competitive moves, customer quotes. | 1-2 paragraphs |
| 6 | **Team & Org** | Key hires, departures, open roles, org changes, culture initiatives. | Bullet list |
| 7 | **Financial Health** | Cash position, burn rate trend, path to next milestone, any financing activity. | Table + 1 paragraph |
| 8 | **Risks & Challenges** | What keeps you up at night. Be specific and honest. | 2-3 bullets |
| 9 | **Wins & Learnings** | Celebrate what went well. Extract lessons from what didn't. | 2-3 bullets each |
| 10 | **Strategic Questions** | Topics where you genuinely want board input. Frame as decisions, not open-ended asks. | 1-2 questions |
| 11 | **Asks** | Specific requests: intros, candidates, advice, approvals. Name the person if possible. | Numbered list |

### The "Headline - Data - Narrative - Ask" Structure
Apply this to every section:
- **Headline:** One sentence that states the conclusion ("Revenue grew 15% but below our 20% target").
- **Data:** The numbers that support the headline, ideally in a table or bold inline.
- **Narrative:** The 2-3 sentence story explaining why the data looks the way it does.
- **Ask/Next:** What you are doing about it or what you need from the reader.

## Frameworks & Best Practices

### Transparent Bad-News Delivery
When communicating negative developments:
1. **State the fact plainly.** "We missed our Q3 revenue target by 22%." No euphemisms.
2. **Explain the root cause.** "Two enterprise deals worth $180K ARR slipped to Q4 due to procurement delays we did not anticipate."
3. **Share what you have already done.** "We have implemented a new procurement-tracking step in our sales process and added 30 days of buffer to enterprise deal timelines."
4. **State the updated outlook.** "We expect to close both deals in October. Revised Q4 target is $X."
5. **Ask for help if needed.** "If anyone has contacts at [Company], a warm intro to their CFO would accelerate procurement."

Investors forgive bad quarters. They do not forgive founders who hide problems until they become crises.

### Metrics Presentation Rules
- **Always show trends.** A single number is meaningless. Show current vs. prior period vs. plan.
- **Use consistent timeframes.** Do not mix monthly and annualized numbers in the same table.
- **Highlight variance.** Bold any metric that deviates more than 10% from plan in either direction.
- **Include unit economics.** CAC, LTV, and payback period tell the story that top-line revenue alone cannot.
- **Show runway in months, not dollars.** "14 months of runway at current burn" is more actionable than "$2.1M in the bank."

### Cadence Guidelines
- **Monthly email updates:** Standard for seed through Series A. Keep under 800 words. Send within the first week of the following month.
- **Quarterly board decks:** Standard from Series A onward. Send as a pre-read 3-5 days before the board meeting. 15-20 slides maximum.
- **Ad-hoc updates:** Send immediately when something material happens (key hire, major customer win/loss, pivot decision, runway concern). One page, one topic.

### Common Mistakes
- Sending updates only when things are going well (creates suspicion during quiet periods).
- Writing updates that are all narrative and no data (makes it hard to track progress).
- Not including specific asks (wastes the most valuable resource your investors offer: their network).
- Spending the whole update on product features when the board cares about business outcomes.
- Waiting until the board meeting to surface a problem that has been growing for months.

## Related Skills
- `process-docs` — Chain to create an SOP for your internal board-update preparation process, ensuring consistent quality each cycle.
- `pitch-deck` — Chain when the board update reveals a need to begin fundraising preparation or when the update doubles as a re-up deck for existing investors.

## Examples

### Example 1: Monthly investor email
**User:** "Write my February investor update. MRR hit $85K (up from $72K), we hired a VP Engineering, but we lost our largest customer."

**Good output excerpt:**
> **TL;DR:** February MRR grew 18% to $85K driven by strong mid-market expansion, but we lost Acme Corp ($12K/mo) due to a budget restructuring outside our control. We hired Sarah Chen as VP Engineering (ex-Stripe). Net, we are ahead on product velocity and slightly behind on net revenue retention. 14 months runway remaining.
>
> **Key Metrics**
> | Metric | Feb | Jan | vs. Plan |
> |--------|-----|-----|----------|
> | MRR | $85K | $72K | +3% |
> | Net New ARR | $156K | $120K | +8% |
> | Gross Churn | $12K | $2K | -$10K |
> | Burn | $110K | $105K | On plan |
> | Runway | 14 mo | 15 mo | On plan |
>
> **Risks & Challenges**
> - Acme Corp churned ($12K MRR). Root cause: their new CFO cut all software contracts under $50K ARR during a company-wide cost reduction. We had 30 days notice and attempted to negotiate a reduced plan; they declined. This was not a product or service failure, but it exposes our revenue concentration risk (Acme was 14% of MRR).
>
> **Asks**
> 1. Intros to mid-market fintech companies (our fastest-growing segment). Specifically looking for VP Operations or Head of Compliance contacts.
> 2. Referrals for a Senior Backend Engineer. JD attached.

### Example 2: Bad-news-forward update
**User:** "We're going to miss our quarterly target by a lot. Help me write this update."

**Good output approach:** Open with the miss stated plainly in the TL;DR. Quantify the gap. Explain root cause in 2-3 sentences. Immediately follow with the remediation plan, including timeline and revised forecast. Close with specific asks for help. Never let bad news be the last thing the reader sees — always end with forward momentum.
