---
name: feedback-synthesis
trigger: When the user needs to analyze, categorize, or extract actionable insights from customer feedback across multiple sources.
related: [user-research-synthesis, churn-analysis, prd-writing]
reads: [startup-context]
---

# Feedback Synthesis

## When to Use
Activate when a founder or product lead needs to make sense of customer feedback from multiple sources — support tickets, NPS surveys, user interviews, app store reviews, social media, sales call notes, or feature request logs. This includes prompts like "analyze our customer feedback," "what are users asking for most," "synthesize these interview notes," "prioritize feature requests," or "what themes are showing up in our support tickets."

## Context Required
- **From startup-context:** product type, customer segments, current product roadmap priorities, company stage, and strategic goals (to evaluate feedback against).
- **From the user:** the raw feedback data (or access to it), the sources being analyzed, the time period, any specific hypotheses to test, and the decision this analysis will inform (e.g., "What should we build next quarter?" or "Why is NPS dropping?").

## Workflow
1. **Collect and normalize** — Gather feedback from all sources. Standardize format: each piece of feedback becomes a row with source, date, customer segment, verbatim quote, and sentiment.
2. **Code and categorize** — Apply the two-level taxonomy: first by theme (what area of the product), then by type (bug, feature request, UX friction, praise, confusion). Use consistent labels across sources.
3. **Quantify patterns** — Count frequency of each theme-type combination. Weight by customer segment value (enterprise feedback may carry more revenue weight; high-volume segment feedback may signal broader patterns).
4. **Extract insights** — Move from "what did they say" to "what does it mean." Identify root causes behind surface-level requests. Group related requests that point to the same underlying need.
5. **Prioritize action items** — Apply the Impact-Effort-Evidence framework to rank what to act on. Separate quick wins from strategic bets.
6. **Present findings** — Deliver a structured synthesis with the executive summary first, supporting data second, and recommended actions third.

## Output Format
A structured feedback synthesis report with these sections:

### Synthesis Report Template
```
# Customer Feedback Synthesis — [Period]

## Executive Summary
3-5 key findings. Lead with the most surprising or actionable insight.

## Methodology
Sources analyzed, volume, time period, any filters applied.

## Theme Map
| Theme | Frequency | Segments Affected | Sentiment | Priority |
|-------|-----------|-------------------|-----------|----------|
| [Theme] | [Count] | [Segments] | [Pos/Neg/Mixed] | [H/M/L] |

## Deep Dives
### Theme 1: [Name]
- **Pattern:** What users are saying (with representative quotes)
- **Root cause:** Why this is happening
- **Impact:** What it costs (churn risk, support load, expansion blocker)
- **Recommendation:** Specific action to take

### Theme 2: [Name]
...

## Quick Wins
Actions that address frequent feedback with low implementation effort.

## Strategic Recommendations
Larger initiatives suggested by the feedback patterns.

## Appendix: Raw Data Summary
Breakdown by source, segment, and time period.
```

## Frameworks & Best Practices

### The Feedback Taxonomy
Use a consistent two-level coding system:

**Level 1 — Theme (Product Area):**
- Core workflow
- Onboarding / Getting started
- Integrations
- Performance / Reliability
- Pricing / Billing
- UI / UX
- Missing capability
- Documentation / Support

**Level 2 — Type:**
- Bug report (something is broken)
- Feature request (something is missing)
- UX friction (something is confusing or slow)
- Praise (something works well — track this too)
- Confusion (user does not understand how something works)

### The Impact-Effort-Evidence Framework
Score each action item on three dimensions:

| Dimension | Score 1 | Score 3 | Score 5 |
|-----------|---------|---------|---------|
| **Impact** | Affects few users, low severity | Affects a segment, moderate severity | Affects most users, high severity or revenue impact |
| **Effort** | Weeks of engineering work | Days of work | Hours or config change |
| **Evidence** | 1-2 mentions, single source | 5-10 mentions, multiple sources | 20+ mentions, consistent across sources |

**Priority = Impact x Effort x Evidence.** High scores act first.

### Signal vs. Noise Rules
- **One customer saying it ≠ a pattern.** Require 3+ independent mentions of a theme before treating it as a signal. Exception: if the one customer is a whale account citing it as a churn risk.
- **Recency bias check.** A flood of recent feedback about one issue can overshadow a persistent problem. Always compare against the prior period.
- **Loudest ≠ most important.** Power users and vocal customers generate disproportionate feedback. Weight by segment size and revenue contribution, not volume alone.
- **Feature requests are symptoms.** When a user says "I want a Gantt chart," the need might be "I need to visualize project timelines." Always dig for the job-to-be-done behind the request.
- **Praise is data too.** Track what users love. Knowing your strengths prevents you from accidentally breaking them during a redesign.

### Source-Specific Guidance
| Source | Strengths | Watch Out For |
|--------|-----------|---------------|
| Support tickets | High signal, specific problems | Skews toward bugs, misses satisfied users |
| NPS/surveys | Broad coverage, quantifiable | Low response rates can bias results |
| User interviews | Deep context, "why" behind behavior | Small sample, interviewer bias |
| App store reviews | Public, includes competitor comparisons | Skews negative, vague complaints |
| Sales call notes | Revenue-adjacent, prospect perspective | Prospects request features they may never use |
| Social media | Unfiltered, emotional, real-time | Noisy, hard to segment, context-free |
| Feature request boards | Organized, vote counts available | Power users dominate voting, popularity ≠ importance |

### Avoiding Common Synthesis Mistakes
- **Cherry-picking quotes** that support a pre-existing hypothesis. Present the full distribution, including contradictory feedback.
- **Conflating frequency with importance.** A low-frequency issue that causes churn matters more than a high-frequency annoyance that users tolerate.
- **Delivering data without recommendations.** A theme map without action items is a report, not a synthesis. Always end with "so what should we do."
- **Ignoring the silent majority.** Users who never complain and never request features are either happy or disengaged. Segment analysis helps distinguish the two.

## Related Skills
- `user-research-synthesis` — Chain when the feedback analysis reveals gaps that need dedicated user research (interviews, usability tests) to fill.
- `churn-analysis` — Chain when feedback themes correlate with churn patterns and need deeper retention analysis.
- `prd-writing` — Chain when a clear feature need emerges from the synthesis and needs to be specced into a PRD.

## Examples

### Example 1: Multi-source synthesis
**User:** "We have 200 support tickets, 50 NPS responses, and notes from 10 customer interviews from last month. What are customers telling us?"

**Good output excerpt:**
> ## Executive Summary
> Three themes dominate across all sources:
> 1. **CSV export is broken for large datasets** (47 support tickets, 8 NPS detractors, 3 interviews). Users hitting the 10K row limit are working around it by splitting exports manually. This is a retention risk for our mid-market segment.
> 2. **Users want Salesforce integration** (12 tickets, 6 NPS mentions, 5 interviews). This is the #1 feature request and was cited as a blocker in 2 expansion conversations worth $36K ARR combined.
> 3. **Onboarding confusion around permissions** (28 tickets, 4 interviews). New admins do not understand the difference between "Editor" and "Contributor" roles, leading to a support ticket within the first week for 15% of new accounts.
>
> **Quick Win:** Increase CSV export limit to 100K rows (engineering estimate: 2 days). Addresses the most painful and frequent complaint immediately.

### Example 2: Feature request prioritization
**User:** "Our feature request board has 150 items. Help me figure out what to build next."

**Good output approach:** Group the 150 items by underlying need (not literal request). Identify 8-12 themes. Score each theme using Impact-Effort-Evidence. Present the top 5 with representative quotes, segment data, and revenue impact estimates. Flag any themes where the request and the underlying need diverge (users asking for X when the real problem is Y).
