---
name: lead-scoring
trigger: When a founder needs to define their ideal customer profile, build a lead scoring model, set MQL criteria, or design pipeline stages. Activate when the user mentions lead scoring, ICP, MQL, SQL, lead qualification, or pipeline design.
related: [cold-outreach, sales-script]
reads: [startup-context]
---

# Lead Scoring

## When to Use
Activate when a founder needs to define who their best customers are, build a system for scoring and prioritizing leads, establish MQL/SQL definitions, or design pipeline stages. Also use when the user says "which leads should I focus on," "how do I qualify leads," "define my ICP," "set up lead scoring," or "my pipeline is a mess."

## Context Required
From `startup-context` or the user:
- **GTM motion** — Product-led, sales-led, or hybrid
- **ACV range** — Average contract value or deal size
- **Current customers** — Who are your best customers today and why
- **Lead volume** — How many leads per month do you generate
- **Sales cycle** — Average days from first touch to closed-won
- **Current stack** — CRM, marketing automation, enrichment tools
- **Current state** — How leads are managed today. What is working and what is broken

Work with whatever the user provides. If they have a clear problem area, start there. Do not block on missing inputs.

## Workflow
1. **Gather context** — Read startup-context if available. Ask about current customers, lead sources, and pain points in the qualification process.
2. **Define the ICP** — Build the ideal customer profile based on best existing customers and target market data.
3. **Design explicit scoring** — Assign point values to firmographic and demographic attributes (who they are).
4. **Design implicit scoring** — Assign point values to behavioral signals (what they do).
5. **Add negative scoring** — Define disqualifying signals that subtract points or auto-disqualify.
6. **Set MQL threshold** — Define the score at which a lead is marketing-qualified and handed to sales.
7. **Design pipeline stages** — Define stage entry/exit criteria, owners, and SLAs from MQL through closed-won.

## Output Format
Deliver these documents:
1. **ICP definition** — Firmographic and demographic criteria with priority tiers
2. **Scoring model** — Complete point-value table for explicit, implicit, and negative signals with MQL threshold
3. **Pipeline stage document** — Stage definitions with entry/exit criteria, owners, and SLAs
4. **Implementation notes** — Platform-specific guidance if CRM is known

## Frameworks & Best Practices

### ICP Definition Framework

Build your ICP from your best existing customers, not your aspirations. Analyze closed-won deals and identify patterns across five dimensions: company size, industry, revenue, tech stack, and geography.

- **Tier 1 (perfect fit):** Matches all 5 dimensions. Prioritize aggressively.
- **Tier 2 (good fit):** Matches 3 of 5 dimensions with strong engagement signals. Worth pursuing.
- **Tier 3 (marginal fit):** Matches 1-2 dimensions. Lower priority, typically lower LTV or longer cycle.

### Explicit Scoring (Fit) — Who They Are

Assign points based on how closely the lead matches your ICP:

| Attribute | Strong Match | Partial Match | No Match |
|-----------|-------------|---------------|----------|
| Company size | +20 | +10 | 0 |
| Industry | +15 | +5 | 0 |
| Job title/seniority | +20 | +10 | 0 |
| Department | +10 | +5 | 0 |
| Geography | +10 | +5 | 0 |
| Tech stack | +10 | +5 | 0 |

**Total possible fit score: ~85 points**

### Implicit Scoring (Engagement) — What They Do

Assign points based on buying-intent signals:

| Behavior | Points | Rationale |
|----------|--------|-----------|
| Visited pricing page | +15 | Strongest intent signal on most websites |
| Requested demo/trial | +20 | Direct buying intent |
| Visited case studies | +10 | Evaluating social proof |
| Downloaded gated content | +5 | Interest, but not necessarily buying intent |
| Attended webinar | +5 | Engagement, but could be educational |
| Opened 3+ emails | +5 | Active engagement with nurture |
| Clicked email CTA | +8 | Deeper engagement |
| Returned to site 3+ times | +10 | Sustained interest |
| Visited careers page | -10 | Likely a job seeker, not a buyer |

**Total possible engagement score: ~78 points**

### Negative Scoring — Disqualifying Signals

Subtract points or auto-disqualify for these signals:

| Signal | Action |
|--------|--------|
| Competitor email domain | Auto-disqualify |
| Student or personal email (gmail, yahoo) | -15 points |
| Job title: intern, student, assistant | -20 points |
| Unsubscribed from emails | -10 points |
| Company size below minimum | -15 points |
| No engagement in 90 days | Decay: -5 points/month |
| Spam complaint | Auto-disqualify |
| Known bad-fit industry | -15 points |

### MQL Definition

An MQL requires BOTH fit and engagement. Neither alone is sufficient.

**Recommended threshold model:**
- Minimum fit score: 30 points (must have basic ICP match)
- Minimum engagement score: 20 points (must show some intent)
- Combined minimum: 60 points

A perfect-fit company that never engages is not an MQL. A student downloading every whitepaper is not an MQL. The dual-threshold prevents both failure modes.

### Pipeline Stage Design

| Stage | Entry Criteria | Exit Criteria | Owner | SLA |
|-------|---------------|---------------|-------|-----|
| **Lead** | Identified contact with basic info | Meets minimum fit criteria | Marketing | Enrich within 24 hrs |
| **MQL** | Passes fit + engagement threshold | Sales accepts or rejects | Marketing -> Sales | Sales responds within 4 hrs |
| **SQL** | Sales accepts and qualifies via conversation | Opportunity created or recycled | Sales | Qualify within 48 hrs |
| **Discovery** | Pain confirmed, stakeholders identified | Demo scheduled | Sales | Demo within 7 days |
| **Evaluation** | Demo completed, requirements confirmed | Proposal requested or rejected | Sales | Proposal within 3 days |
| **Proposal** | Proposal delivered and reviewed | Terms agreed or negotiation | Sales | Decision within 14 days |
| **Closed Won** | Contract signed | Handoff to onboarding | Sales -> CS | Kickoff within 5 days |
| **Closed Lost** | Deal lost | Post-mortem logged with reason | Sales | Log within 24 hrs |

### Maintaining and Iterating
- **Recalibrate quarterly.** Pull closed-won data and check if your model correctly predicted winners. Buyer behavior changes.
- **Watch for score inflation.** If 80% of leads become MQLs, the threshold is too low.
- **Track MQL-to-SQL acceptance rate.** If sales rejects more than 30% of MQLs, adjust the model.
- **Start simple.** Begin with 5-10 signals and iterate. Score your first 50-100 leads by hand before automating.
- **Founder intuition matters.** If a lead "feels" right but scores low, your model may be missing a signal.
- **Speed-to-lead is critical.** Contact within 5 minutes is 21x more likely to qualify. After 24 hours, the lead is cold.

## Related Skills
- `cold-outreach` — use the ICP and scoring to prioritize who to reach out to first
- `sales-script` — use pipeline stage definitions to prepare the right script for each stage

## Examples

**Example prompt:** "We are a B2B SaaS startup selling to mid-market engineering teams. Our best customers are 100-500 person SaaS companies. Help me set up lead scoring."

**Good ICP output snippet:**
> ### Tier 1 — Ideal Customer Profile
> - **Company size:** 100-500 employees
> - **Industry:** SaaS, fintech, or developer tools
> - **Target role:** VP Engineering, Engineering Manager, Staff+ Engineer
> - **Tech stack signals:** Uses GitHub, Datadog, or PagerDuty (indicates mature engineering org)
> - **Geography:** US, Canada, UK (primary markets)
> - **Funding:** Series A through Series C (budget available, still growing)

**Good MQL definition output snippet:**
> A lead becomes MQL when fit score >= 30, engagement score >= 20, combined score >= 60, and no disqualifying signals are present.
