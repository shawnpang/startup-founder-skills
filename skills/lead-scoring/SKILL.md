---
name: lead-scoring
description: When a founder needs to qualify inbound leads, define their ICP, build a lead scoring model, set MQL criteria, or route prospects through pipeline stages. Activate when the user mentions lead scoring, ICP, MQL, SQL, lead qualification, inbound leads, or pipeline design.
related: [cold-outreach, sales-script]
reads: [startup-context]
---

# Lead Scoring

## When to Use
Activate when a founder needs to evaluate inbound prospects against ICP criteria, build a systematic qualification workflow, score and route leads, establish MQL/SQL definitions, or design pipeline stages. Also use when the user says "which leads should I focus on," "how do I qualify inbound leads," "define my ICP," "set up lead scoring," or "how do I route leads to the right person."

## Context Required
From `startup-context` or the user:
- **ICP definition** — Who is the ideal customer (company size, industry, stage, geography, use case)
- **Lead sources** — Where inbound leads come from (website, events, content, referrals)
- **CRM and tooling** — Current stack for managing leads and deals
- **Current customers** — Who are the best existing customers and why
- **Pipeline data** — Existing deals, active customers, prior contacts
- **Sales capacity** — Who handles leads and what is their bandwidth

Work with whatever the user provides. If they have a clear problem area, start there. Do not block on missing inputs.

## Workflow
1. **Load ICP and configuration** — Read startup-context if available. Establish the qualification criteria across company attributes, person attributes, and use case fit.
2. **Parse the lead data** — Accept leads in any format (CSV, list, CRM export, single name). Identify data gaps and flag what needs enrichment.
3. **Check pipeline overlap** — Before scoring, check for existing customers (route to upsell), active deals (flag for sales coordination), and prior contacts (note history). Pipeline overlaps are routing flags, not disqualifiers.
4. **Score company fit** — Evaluate against company size, industry, stage, geography, and use case alignment. Weight each dimension based on what predicts closed-won deals.
5. **Score person fit** — Evaluate title, seniority, department, and decision-making authority. A perfect company with the wrong contact still needs routing, not rejection.
6. **Score use case alignment** — Connect the lead's inferred intent to specific product capabilities. Inbound signals (demo requests, pricing page visits) tip borderline cases toward qualification.
7. **Generate composite score and verdict** — Produce a 0-100 composite score and assign a routing recommendation.
8. **Export structured output** — Deliver results in a table or CSV with all qualification data, scores, and routing.

## Output Format
Deliver these documents:
1. **Scored lead report** — Each lead with composite score (0-100), sub-scores by dimension, verdict category, and routing recommendation
2. **ICP definition** — Firmographic and demographic criteria with priority tiers
3. **Scoring model** — Complete point-value table for company, person, and use case dimensions with threshold definitions
4. **Pipeline routing rules** — How each verdict category gets handled

## Frameworks & Best Practices

### Verdict Categories
Assign every lead to one of these routing buckets based on composite score:

| Verdict | Score | Action |
|---------|-------|--------|
| **Qualified — Hot** | 85-100 | Immediate sales outreach. High urgency, strong fit. |
| **Qualified — Warm** | 75-84 | Active pursuit within 24 hours. Good fit, moderate urgency. |
| **Borderline** | 50-74 | Requires human review. Qualified with caveats — flag specific concerns. |
| **Near Miss** | 30-49 | Nurture sequence or referral opportunity. Not ready for sales. |
| **Disqualified** | 0-29 | Does not fit ICP. Includes competitor employees. Polite decline. |

### Handling Unknown Data
Score unknown dimensions at 30 points (out of 100 for that dimension). This acknowledges data absence without automatically rejecting leads. A lead missing company size data is not the same as a lead with the wrong company size. Flag unknowns for enrichment rather than penalizing them.

### Inbound Intent Premium
Prospects who initiate contact demonstrate genuine interest. For borderline cases (scores 50-74), inbound signals should tip the scoring decision toward qualification. A borderline lead who requested a demo is a better prospect than a slightly-above-threshold lead who has never engaged.

### Pipeline Overlap Routing
Before scoring, check for overlaps and route accordingly:
- **Existing customer** — Route to account management for upsell/expansion conversation
- **Active deal in pipeline** — Flag for the assigned sales rep to coordinate, do not create a duplicate
- **Prior contact with no deal** — Note history and score normally, but include context for the sales rep
- **Competitor employee** — Auto-disqualify and log for competitive intelligence

### Multi-Dimensional Scoring

**Company evaluation** — Score against: company size, industry vertical, company stage/funding, geography, and use case fit. Weight dimensions based on which most predict closed-won deals in your data.

**Person assessment** — Score against: job title, seniority level, department alignment, and decision-making authority. A Director of Engineering at a perfect-fit company scores higher than a junior developer at the same company.

**Use case alignment** — Map the lead's stated or inferred needs to specific product capabilities. Strong alignment on the core use case matters more than broad but shallow fit.

### Dual-Threshold MQL Definition
An MQL requires BOTH fit and engagement. Neither alone is sufficient.
- Minimum fit score: 30 points (must have basic ICP match)
- Minimum engagement score: 20 points (must show some intent)
- Combined minimum: 60 points

A perfect-fit company that never engages is not an MQL. A student downloading every whitepaper is not an MQL. The dual-threshold prevents both failure modes.

### Maintaining and Iterating
- **Recalibrate quarterly.** Pull closed-won data and check if the model correctly predicted winners.
- **Watch for score inflation.** If 80% of leads become MQLs, the threshold is too low.
- **Track MQL-to-SQL acceptance rate.** If sales rejects more than 30% of MQLs, adjust the model.
- **Start simple.** Score the first 50-100 leads by hand before automating.
- **Speed-to-lead is critical.** Contact within 5 minutes is 21x more likely to qualify.

## Related Skills
- `cold-outreach` — Use the ICP and scoring to prioritize who to reach out to first
- `sales-script` — Use pipeline stage definitions to prepare the right script for each stage

## Examples

**Example prompt:** "We get 200 inbound leads a month from our website and events. Most go nowhere. Help me build a system to score and route them."

**Good output excerpt:**
> ### Lead Qualification Report (Sample)
> | Lead | Company Score | Person Score | Use Case Score | Composite | Verdict |
> |------|-------------|-------------|---------------|-----------|---------|
> | Jane Smith, VP Eng @ Acme (200 emp, SaaS) | 88 | 85 | 90 | 88 | Qualified — Hot |
> | Bob Lee, Developer @ TinyCo (15 emp, Agency) | 35 | 40 | 50 | 40 | Near Miss |
> | Unknown Title @ MegaCorp (10K emp, Finance) | 60 | 30 (unknown) | 45 | 47 | Near Miss — Enrich |
>
> **Routing:** Jane gets immediate sales outreach (AE assigned within 1 hour). Bob enters nurture sequence. MegaCorp lead flagged for enrichment — title and use case data needed before routing.

**Example prompt:** "A lead from a current customer's company just filled out our demo form. What do I do?"

**Good output approach:** Flag the pipeline overlap — check if this is a new department/team or the same buyer. If same account, route to the existing account manager for upsell coordination. If new department, score normally but include account context. Never create a duplicate deal.
