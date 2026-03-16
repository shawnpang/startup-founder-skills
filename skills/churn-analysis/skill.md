---
name: churn-analysis
trigger: When the user needs to understand why customers are leaving, reduce churn rate, design cancellation flows, build health scores, or create win-back campaigns.
related: [feedback-synthesis, onboarding-flow, email-marketing]
reads: [startup-context]
---

# Churn Analysis

## When to Use
Activate when a founder needs to diagnose churn drivers, reduce customer attrition, design cancellation or save flows, recover failed payments, analyze retention by cohort, or re-engage lost customers. This includes prompts like "our churn is too high," "why are customers canceling," "design a cancel flow," "build a customer health score," "set up dunning emails," or "create a win-back campaign."

## Context Required
- **From startup-context:** business model (B2B/B2C, subscription/usage-based), current churn rate (logo and revenue), customer segments, pricing tiers, contract terms, product usage data availability, and current retention tooling.
- **From the user:** the churn rate and trend, available data sources (billing system, product analytics, CRM, support tickets), whether churn is primarily voluntary (cancellation) or involuntary (payment failure), any exit survey data, and the specific churn problem to solve.

## Workflow
1. **Baseline and benchmark** — Establish current churn rate (monthly and annual, logo and revenue). Compare against benchmarks for the business type (see targets below).
2. **Segment the churn** — Break down churn by customer segment, cohort, plan tier, acquisition channel, and tenure. Churn is never uniform; find where it concentrates.
3. **Diagnose root causes** — Analyze cancellation reasons, support ticket patterns pre-churn, product usage decline signals, and exit survey data. Categorize into the churn driver taxonomy.
4. **Build the health score** — Create a composite score from usage, engagement, support, and billing signals that predicts churn risk 30-60 days in advance.
5. **Design interventions** — For each churn driver, design the appropriate intervention: product fix, CS outreach, cancel flow save offer, dunning sequence, or win-back campaign.
6. **Measure and iterate** — Track save rate, recovery rate, and net churn impact of each intervention. Run A/B tests on save offers and dunning sequences.

## Output Format
A churn analysis deliverable tailored to the specific request. This may be a diagnostic report, a health score model, a cancel flow design, a dunning email sequence, or a win-back campaign — or a comprehensive plan combining several.

## Frameworks & Best Practices

### Churn Rate Targets
| Business Type | Good Monthly Churn | Great Monthly Churn | Red Flag |
|---------------|-------------------|--------------------| ---------|
| B2C subscription | < 5% | < 3% | > 8% |
| B2B SMB SaaS | < 3% | < 1.5% | > 5% |
| B2B Mid-market SaaS | < 2% | < 1% | > 3% |
| B2B Enterprise SaaS | < 1% | < 0.5% | > 1.5% |

Revenue churn should be lower than logo churn if expansion revenue is healthy. **Net revenue retention > 100%** means expansion outpaces churn.

### The Churn Driver Taxonomy
Categorize every churn event into one of these buckets:

1. **Value gap** — The product does not solve the problem well enough. Signals: low usage, feature complaints, competitor mentions in exit surveys.
2. **Onboarding failure** — The customer never reached the aha moment. Signals: churn concentrated in first 30-60 days, incomplete setup, low activation rate.
3. **Support failure** — The customer had a bad experience getting help. Signals: high ticket volume pre-churn, negative CSAT, escalations.
4. **Price sensitivity** — The customer finds the product too expensive relative to perceived value. Signals: churn spikes after price changes, downgrades before cancellation, "too expensive" in exit survey.
5. **Champion departure** — The internal champion left the customer's company. Signals: contact change followed by cancellation, no other engaged users.
6. **Business change** — The customer's needs changed (acquisition, pivot, shutdown). Signals: external news, "no longer need this" in exit survey.
7. **Involuntary churn** — Payment failure, not a conscious decision to leave. Signals: failed charges, expired cards, no cancellation request filed.

### Customer Health Score Model
Build a composite score (0-100) from these signal categories:

| Signal Category | Weight | Inputs | Scoring Logic |
|----------------|--------|--------|---------------|
| **Product usage** | 30% | DAU/MAU ratio, core feature adoption, login frequency | Score against segment benchmarks |
| **Engagement depth** | 25% | Features used, data volume, integrations connected | More breadth = stickier |
| **Support sentiment** | 15% | Ticket volume trend, CSAT scores, escalation count | Rising tickets = declining health |
| **Billing signals** | 15% | Payment failures, downgrades, discount usage | Failed payment = immediate risk |
| **Relationship** | 15% | NPS score, executive sponsor engagement, expansion conversations | Multi-threaded relationships churn less |

**Health score thresholds:**
- **80-100 (Healthy):** Monitor quarterly. Candidates for expansion.
- **60-79 (Watch):** Flag for CS review. Investigate any declining signals.
- **40-59 (At Risk):** CS outreach within 1 week. Intervention plan required.
- **0-39 (Critical):** Executive-level outreach within 48 hours. Save offer preparation.

### Cancel Flow Design
The cancellation experience is your last chance to retain a customer and your best chance to learn why they are leaving.

**Cancel flow steps:**
1. **Ask why (required).** Present 5-7 reason options matching the churn driver taxonomy. Include a free-text field. This data is gold.
2. **Offer a targeted save** based on their stated reason:
   - "Too expensive" → Discount or downgrade option
   - "Missing feature" → Show roadmap or workaround, offer to notify when shipped
   - "Not using it enough" → Pause option (freeze billing for 1-3 months)
   - "Switching to competitor" → Offer migration help or a competitive offer
   - "Business closing/changing" → Accept gracefully, ask for a referral
3. **Confirm with friction.** Require one extra click and show what they will lose (data, integrations, team access). Do not make it hostile — show value, not guilt.
4. **Offer a pause instead.** 30-60 day billing pause saves 15-25% of would-be churners in B2C and 10-15% in B2B.
5. **Offboard gracefully.** Send a confirmation email with data export instructions and a "we'd love to have you back" message. Leave the door open.

**Cancel flow benchmarks:** A well-designed cancel flow saves 10-20% of users who initiate cancellation.

### Dunning and Payment Recovery
Involuntary churn (failed payments) typically accounts for 20-40% of total churn and is the easiest to reduce.

**Dunning sequence:**
| Step | Timing | Channel | Message |
|------|--------|---------|---------|
| 1 | Payment fails | Email | "Your payment didn't go through — update your card to keep your account active" |
| 2 | +3 days | Email + in-app banner | "Your account is at risk — update payment to avoid service interruption" |
| 3 | +7 days | Email | "Last chance: update your payment method in the next 48 hours" |
| 4 | +10 days | Email | Account downgraded/paused. "Your data is safe — reactivate anytime" |
| Retry | Days 1, 3, 5, 7 | Automatic | Retry the failed charge (different times of day) |

**Recovery best practices:**
- Retry failed charges 4-6 times over 10-14 days before giving up.
- Send the card update link directly (pre-authenticated deep link to billing page).
- Warn before the card expires (30 and 7 days prior) to prevent the failure entirely.
- A good dunning system recovers 30-50% of failed payments.

### Win-Back Campaigns
Target customers who churned 30-90 days ago. Beyond 90 days, response rates drop sharply. Sequence: product updates (Day 14), incentive offer (Day 30), social proof (Day 60), feedback survey as final attempt (Day 90). Segment by churn reason — users who left for fixable reasons (price, missing feature now shipped) reactivate at 2-3x the average. Expect 5-15% overall reactivation from a well-executed sequence.

### Cohort Analysis Framework
Analyze retention by signup cohort to understand whether the product is improving over time:
- **Flatten the curve.** Healthy products show improving retention curves for newer cohorts.
- **Find the cliff.** Identify the month where the sharpest drop occurs (often Month 2 or Month 3). This is where to focus intervention.
- **Segment cohorts.** Compare retention by acquisition channel, plan tier, and activation completeness. The variance between segments often reveals the real lever.

## Related Skills
- `feedback-synthesis` — Chain to analyze qualitative feedback from churned customers alongside quantitative churn data for a complete picture.
- `onboarding-flow` — Chain when churn analysis reveals that early-tenure churn (first 30-60 days) is the primary driver, indicating an activation problem.
- `email-marketing` — Chain to build the full lifecycle email sequences (dunning, win-back, health-triggered re-engagement) identified in the churn analysis.

## Examples

### Example 1: Churn diagnostic
**User:** "Our monthly churn jumped from 4% to 7% over the last quarter. Help me figure out why."

**Good output excerpt:**
> ## Churn Segmentation
> The 3-point increase is not uniform. Breaking down by cohort and segment:
> - **January cohorts:** 9.2% monthly churn (vs. 4.1% for October cohorts at the same tenure). Something changed in the onboarding or acquisition quality in January.
> - **Starter plan:** Churn increased from 6% to 11%. Growth plan: stable at 2.5%.
> - **Churn driver distribution (from exit surveys, n=89):**
>   - "Too expensive": 34% (up from 18% last quarter)
>   - "Not using it enough": 28%
>   - "Missing features": 22%
>   - "Switched to competitor": 16%
>
> **Root Cause Hypothesis:** The January price increase on Starter plans (+20%) combined with a lower-quality acquisition cohort (likely from the holiday promotion offering deep discounts) created a segment of price-sensitive users who never activated fully and churned when they saw the new renewal price.
>
> **Recommended Interventions:**
> 1. **Immediate:** Offer churned Starter users a 3-month revert to their original price (estimated save rate: 15-20%)
> 2. **This month:** Audit January acquisition channels and tighten targeting to reduce low-intent signups
> 3. **This quarter:** Build an onboarding fast-track for Starter plan users focused on time-to-value under 10 minutes

### Example 2: Cancel flow design
**User:** "We don't have a cancel flow — users just email us to cancel. Design one."

**Good output approach:** Design a 4-step in-app cancel flow: reason selection (mapped to churn drivers), targeted save offer based on the selected reason, confirmation screen showing what the user will lose, and a graceful offboarding email. Include wireframe-level descriptions of each screen, copy for save offers, and expected save rates. Also recommend tracking every step as a funnel to measure conversion at each stage.
