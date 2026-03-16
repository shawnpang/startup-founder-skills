---
name: churn-analysis
description: When the user needs to identify at-risk accounts, understand why customers are leaving, reduce churn rate, build health scores, design save plays, or create win-back campaigns.
related: [feedback-synthesis, onboarding-flow, email-marketing]
reads: [startup-context]
---

# Churn Analysis

## When to Use
Activate when a founder needs to identify at-risk accounts before they churn, diagnose churn drivers, build a customer health scoring system, design cancellation or save flows, recover failed payments, or re-engage lost customers. This includes prompts like "our churn is too high," "which customers are about to leave," "why are customers canceling," "build a customer health score," "set up dunning emails," or "create a win-back campaign." Especially relevant for seed/Series A teams managing customers manually without dedicated CS platforms like Gainsight or ChurnZero.

## Context Required
- **From startup-context:** business model (B2B/B2C, subscription/usage-based), current churn rate (logo and revenue), customer segments, pricing tiers, contract terms, product usage data availability, and current retention tooling.
- **From the user:** available data sources (support tickets, Slack channels, NPS scores, usage logs, email logs, billing data), what "healthy" customer behavior looks like, any historical churn patterns, whether churn is primarily voluntary or involuntary, and the specific churn problem to solve.

Work with whatever data is available. Early-stage companies often lack formal CS systems — the skill works with support inboxes, Slack history, and spreadsheets.

## Workflow
1. **Intake and baseline** — Gather all available customer data: customer lists, support tickets, Slack/communication history, NPS scores, usage data, email logs, and billing records. Establish what "healthy" looks like and identify any known churn patterns.
2. **Extract signals** — Analyze four signal categories across every account: support signals, communication signals, usage signals, and commercial signals (see framework below).
3. **Score risk** — Build a composite risk score (0-100) for each account using weighted signal categories. Higher score means higher risk.
4. **Generate save plays** — For high-risk accounts, produce specific interventions: root cause hypothesis, recommended actions, talk tracks for the CS conversation, and escalation triggers.
5. **Build the weekly scorecard** — Compile into a weekly risk report with account-by-account analysis, MRR at risk, trend data, signal distribution, and recommended focus areas.
6. **Design interventions** — For each churn driver identified, design the appropriate intervention: product fix, CS outreach, cancel flow save offer, dunning sequence, or win-back campaign.

## Output Format
A churn risk report tailored to the specific request. This may include:
1. **Weekly risk scorecard** — Every account scored and tiered with signal breakdown
2. **MRR at risk summary** — Total revenue exposure by risk tier
3. **Save play briefs** — For each red/orange account: root cause, recommended action, talk track, escalation trigger
4. **Intervention designs** — Cancel flows, dunning sequences, or win-back campaigns as needed
5. **Trend analysis** — Signal distribution changes over time

## Frameworks & Best Practices

### Signal Extraction Categories
Analyze every account across these four signal types:

**Support signals:** Ticket volume spikes, unresolved tickets, escalation language ("frustrated," "unacceptable," "cancel"), response time degradation, repeat issues on the same topic.

**Communication signals:** Silent accounts (no contact in 30+ days), frequency decline, sentiment shifts in Slack/email, champion disengagement (the main contact goes quiet), new stakeholder asking basic questions (signals champion departure).

**Usage signals:** Login frequency drops, feature abandonment (stopped using features they previously used regularly), shallow usage (logging in but not completing core workflows), no growth in usage over time, export/data download spikes (preparing to migrate).

**Commercial signals:** Discount requests, downgrade inquiries, payment failures, renewal proximity with no expansion discussion, competitor mentions in any channel.

### Risk Scoring Model
Build a composite score (0-100) by weighting individual signals:

| Signal Severity | Points | Examples |
|----------------|--------|----------|
| **Critical** | 25 | Explicit cancel request, competitor migration started, champion left |
| **High** | 15 | Usage dropped 50%+, 3+ unresolved escalations, payment failed twice |
| **Medium** | 8 | Login frequency declining, support sentiment negative, downgrade inquiry |
| **Low** | 3 | Slight usage dip, delayed renewal conversation, single missed payment |

Multiple signals compound. An account with two high signals (30 points) and three medium signals (24 points) scores 54 — solidly in the Orange tier.

### Risk Tiers and Response Timelines

| Tier | Score | Timeline | Action |
|------|-------|----------|--------|
| **Red** | 70-100 | Action this week | Executive outreach, save offer prepared, root cause identified |
| **Orange** | 40-69 | Action within 2 weeks | CS outreach, intervention plan, monitor daily |
| **Yellow** | 20-39 | Monitor within 30 days | Check-in scheduled, watch for signal escalation |
| **Green** | 0-19 | Routine check-in | Quarterly review, expansion opportunity assessment |

### The Churn Driver Taxonomy
Categorize every churn event into one of these buckets:
1. **Value gap** — Product does not solve the problem well enough
2. **Onboarding failure** — Customer never reached the aha moment (churn in first 30-60 days)
3. **Support failure** — Bad experience getting help
4. **Price sensitivity** — Too expensive relative to perceived value
5. **Champion departure** — Internal champion left the customer's company
6. **Business change** — Customer's needs changed (acquisition, pivot, shutdown)
7. **Involuntary churn** — Payment failure, not a conscious decision to leave

### Cancel Flow Design
1. **Ask why (required).** Present 5-7 reason options matching the taxonomy. Include free-text. This data is essential.
2. **Offer a targeted save** based on stated reason: "too expensive" gets a discount/downgrade, "missing feature" gets the roadmap, "not using it" gets a billing pause.
3. **Confirm with friction.** One extra click showing what they lose. Show value, not guilt.
4. **Offer a pause.** 30-60 day billing pause saves 15-25% of would-be churners in B2C and 10-15% in B2B.
5. **Offboard gracefully.** Confirmation email with data export and a "we'd love to have you back" message.

A well-designed cancel flow saves 10-20% of users who initiate cancellation.

### Dunning and Payment Recovery
Involuntary churn accounts for 20-40% of total churn and is the easiest to reduce. Retry failed charges 4-6 times over 10-14 days. Send card update links (pre-authenticated). Warn before cards expire (30 and 7 days prior). A good dunning system recovers 30-50% of failed payments.

### Win-Back Campaigns
Target customers who churned 30-90 days ago. Beyond 90 days, response rates drop sharply. Segment by churn reason — users who left for fixable reasons (price, missing feature now shipped) reactivate at 2-3x the average. Expect 5-15% overall reactivation from a well-executed sequence.

## Related Skills
- `feedback-synthesis` — Analyze qualitative feedback from churned customers alongside quantitative churn data
- `onboarding-flow` — When churn analysis reveals early-tenure churn as the primary driver, indicating an activation problem
- `email-marketing` — Build full lifecycle email sequences (dunning, win-back, health-triggered re-engagement)

## Examples

### Example 1: Weekly risk scorecard
**User:** "I manage 45 accounts manually. Help me figure out which ones are about to churn."

**Good output excerpt:**
> ### Weekly Risk Scorecard — March 15, 2026
> **MRR at Risk:** $18,400 (12% of total MRR)
>
> | Account | MRR | Risk Score | Tier | Key Signals |
> |---------|-----|-----------|------|-------------|
> | Acme Corp | $2,400 | 82 | Red | Champion left 3 weeks ago, usage down 60%, no response to last 2 emails |
> | Beta Inc | $1,200 | 55 | Orange | 4 support tickets in 2 weeks (up from 1/month), asked about downgrade |
> | Gamma LLC | $800 | 28 | Yellow | Login frequency declining, approaching renewal with no expansion signals |
>
> **Save Play — Acme Corp:**
> Root cause: Champion departure. New contact has not been onboarded.
> Action: Executive-level outreach to identify new stakeholder. Offer a dedicated re-onboarding session. Prepare a 20% renewal discount if needed.
> Escalation trigger: No response within 5 business days — CEO-to-CEO email.

### Example 2: Churn diagnostic
**User:** "Our monthly churn jumped from 4% to 7% over the last quarter. Help me figure out why."

**Good output approach:** Segment the increase by cohort, plan tier, and acquisition channel. Cross-reference with exit survey data to identify which churn drivers are increasing. Produce a root cause hypothesis linking the spike to specific changes (pricing, acquisition quality, product issues) and recommend targeted interventions for each driver.
