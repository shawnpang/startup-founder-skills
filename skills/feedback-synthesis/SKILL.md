---
name: feedback-synthesis
description: When the user needs to analyze, categorize, or extract actionable insights from customer feedback across multiple sources, especially feature requests.
related: [user-research-synthesis, churn-analysis, prd-writing]
reads: [startup-context]
---

# Feedback Synthesis

## When to Use
Activate when a founder or product lead needs to make sense of customer feedback from multiple sources -- support tickets, NPS surveys, user interviews, app store reviews, social media, sales call notes, feature request logs, spreadsheets, or CSVs. This includes prompts like "analyze our customer feedback," "what are users asking for most," "prioritize feature requests," "triage this backlog," or "what themes are showing up in our support tickets."

## Context Required
- **From startup-context:** product type, customer segments, current product roadmap priorities, company stage, strategic goals, and product objectives.
- **From the user:** the raw feedback data (or access to it), the sources being analyzed, the time period, the product goal or desired outcomes guiding prioritization, and the decision this analysis will inform.

## Workflow
1. **Understand the goal** -- Confirm the product objective and desired outcomes that will guide prioritization. Feedback analysis without a strategic lens produces noise, not signal.
2. **Collect and normalize** -- Gather feedback from all sources. If data is in structured formats (CSV, spreadsheet), create summary tables. Each piece of feedback becomes a row with source, date, customer segment, verbatim quote, and sentiment.
3. **Categorize into themes** -- Group related requests and feedback together. Name each theme. Focus on identifying the underlying opportunity (problem) rather than the surface-level feature request.
4. **Assess strategic alignment** -- For each theme, evaluate how well it aligns with the stated product goals and company strategy.
5. **Score with Opportunity Score** -- Use the Opportunity Score framework (Dan Olsen): Opportunity Score = Importance x (1 - Satisfaction), normalized to 0-1. This prioritizes problems that matter most and are least well-served today.
6. **Prioritize top opportunities** -- Select the top 3 themes based on impact (customer value and breadth of users affected), effort (development and design resources required), risk (technical and market uncertainty), and strategic alignment (fit with product vision).
7. **Deep-dive top items** -- For each top opportunity, document: rationale, alternative solutions worth considering, high-risk assumptions, and how to test those assumptions with minimal effort.
8. **Present findings** -- Deliver a structured synthesis with executive summary first, supporting data second, and recommended actions third.

## Output Format

### Synthesis Report Template
```
# Customer Feedback Synthesis -- [Period]

## Executive Summary
3-5 key findings. Lead with the most surprising or actionable insight.

## Product Goal Alignment
The stated product objective and how feedback themes map to it.

## Theme Map
| Theme | Frequency | Segments Affected | Opportunity Score | Strategic Alignment | Priority |
|-------|-----------|-------------------|-------------------|---------------------|----------|
| [Theme] | [Count] | [Segments] | [Score] | [High/Med/Low] | [H/M/L] |

## Top 3 Opportunities (Deep Dives)
### Opportunity 1: [Theme Name]
- **Rationale:** Customer needs and strategic alignment
- **Representative quotes:** Direct user language
- **Alternative solutions:** Other ways to address this need
- **High-risk assumptions:** What must be true
- **Cheapest test:** How to validate with minimal effort

## Quick Wins
Actions that address frequent feedback with low implementation effort.

## Not Prioritized (and Why)
Themes explicitly deprioritized with reasoning.

## Appendix: Raw Data Summary
Breakdown by source, segment, and time period.
```

## Frameworks & Best Practices

### Opportunities Over Features
Never let customers design solutions. Prioritize opportunities (problems), not features. When a user says "I want a Gantt chart," the underlying opportunity might be "I need to visualize project timelines and communicate status to stakeholders." Always dig for the job-to-be-done behind the request.

### Opportunity Score (Dan Olsen)
Score each theme: Opportunity Score = Importance x (1 - Satisfaction), normalized to 0-1. This surfaces problems that are both important and underserved. A high-importance, high-satisfaction area is already well-served and should not be prioritized over a high-importance, low-satisfaction gap.

### Signal vs. Noise Rules
- **One customer saying it is not a pattern.** Require 3+ independent mentions of a theme before treating it as a signal. Exception: if the one customer is a whale account citing it as a churn risk.
- **Recency bias check.** A flood of recent feedback about one issue can overshadow a persistent problem. Always compare against the prior period.
- **Loudest does not equal most important.** Power users and vocal customers generate disproportionate feedback. Weight by segment size and revenue contribution, not volume alone.
- **Praise is data too.** Track what users love. Knowing your strengths prevents you from accidentally breaking them during a redesign.

### Assumption Testing
For each top-priority opportunity, identify the highest-risk assumption and design the cheapest possible test. Do not build the full solution to validate an assumption that could be tested with a prototype, survey, or Wizard of Oz experiment.

### Source-Specific Guidance
| Source | Strengths | Watch Out For |
|--------|-----------|---------------|
| Support tickets | High signal, specific problems | Skews toward bugs, misses satisfied users |
| NPS/surveys | Broad coverage, quantifiable | Low response rates can bias results |
| Feature request boards | Organized, vote counts available | Power users dominate voting |
| Sales call notes | Revenue-adjacent, prospect perspective | Prospects request features they may never use |
| App store reviews | Public, includes competitor comparisons | Skews negative, vague complaints |
| Social media | Unfiltered, real-time | Noisy, hard to segment |

### Avoiding Common Mistakes
- **Cherry-picking quotes** that support a pre-existing hypothesis. Present the full distribution, including contradictory feedback.
- **Conflating frequency with importance.** A low-frequency issue that causes churn matters more than a high-frequency annoyance users tolerate.
- **Delivering data without recommendations.** A theme map without action items is a report, not a synthesis. Always end with what to do next.
- **Ignoring the silent majority.** Users who never complain may be happy or disengaged. Segment analysis helps distinguish the two.

## Related Skills
- `user-research-synthesis` -- Chain when feedback analysis reveals gaps that need dedicated user research (interviews, usability tests).
- `churn-analysis` -- Chain when feedback themes correlate with churn patterns and need deeper retention analysis.
- `prd-writing` -- Chain when a clear opportunity emerges from the synthesis and needs to be specced into a PRD.

## Examples

### Example 1: Feature request prioritization
**User:** "Our feature request board has 150 items. Help me figure out what to build next quarter."

**Good output excerpt:**
> **Executive Summary:** 150 requests cluster into 9 themes. The top opportunity is not the most-requested feature (SSO, 34 votes) but the most underserved need: "real-time collaboration on shared documents" (Opportunity Score: 0.82). SSO scores lower (0.45) because existing workarounds satisfy most users adequately.
>
> **Opportunity 1: Real-time collaboration**
> - **Rationale:** 22 requests across 4 segments. Cited as expansion blocker in 3 enterprise deals worth $85K ARR. Current satisfaction: 2/10.
> - **Alternative solutions:** (a) Full real-time editing, (b) Lightweight commenting and presence indicators, (c) Async review workflow with notifications
> - **High-risk assumption:** Users want simultaneous editing, not just awareness of others' changes
> - **Cheapest test:** Add presence indicators only (show who is viewing a document) and measure whether collaboration-related tickets decrease

### Example 2: Multi-source synthesis
**User:** "We have 200 support tickets, 50 NPS responses, and notes from 10 customer interviews from last month. What are customers telling us?"

**Good output excerpt:**
> **Theme 1: CSV export broken for large datasets** (Opportunity Score: 0.91)
> - 47 support tickets, 8 NPS detractors, 3 interviews. Users hitting the 10K row limit work around it by splitting exports manually.
> - **Strategic alignment:** High -- data export is core to our "open platform" positioning.
> - **Cheapest test:** Not needed; this is a clear bug/limitation. Fix directly.
> - **Quick win:** Increase CSV export limit to 100K rows (engineering estimate: 2 days).
