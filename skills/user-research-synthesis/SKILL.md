---
name: user-research-synthesis
description: When the user has raw customer interview transcripts, survey responses, support tickets, or other qualitative data and needs to extract actionable insights.
related: [prd-writing, competitive-analysis]
reads: [startup-context]
---

# User Research Synthesis

## When to Use
Activate when a founder or PM provides raw qualitative research data and needs it synthesized into structured insights. This includes customer interview transcripts, survey open-ended responses, support ticket logs, NPS verbatims, sales call notes, app store reviews, or community forum posts. Trigger phrases include "summarize these interviews," "what are customers telling us," "synthesize this feedback," or "help me analyze these customer conversations."

## Context Required
- **From startup-context:** product stage, current customer segments, known hypotheses being tested, existing personas (if any).
- **From the user:** the raw data sources (transcripts, notes, recordings), research questions being investigated, participant background information, any specific hypotheses to validate or invalidate.

## Workflow
1. **Read the complete transcript** -- Before summarizing, read the entire transcript or data source end-to-end. Do not begin summarizing until you have processed all material. This prevents recency bias and ensures nothing is missed.
2. **Capture metadata** -- Record interview date, participants, participant background, and context for the conversation.
3. **Identify current solutions** -- Document what solutions the participant currently uses and their satisfaction level with each. This reveals the competitive landscape from the user's perspective.
4. **Extract problems and pain points** -- Catalog every problem mentioned, using the participant's own language. Separate symptoms from root causes.
5. **Apply Jobs to Be Done framing** -- For each major finding, frame it as a JTBD: "When [situation], I want to [motivation], so I can [expected outcome]." This shifts focus from features to outcomes.
6. **Flag unexpected discoveries** -- Note any surprising insights, contradictions, or findings that challenge existing assumptions. These often hold the most strategic value.
7. **Define follow-up actions** -- List specific next steps with ownership: who should do what based on these findings.
8. **Assess confidence levels** -- Rate each insight as high/medium/low confidence based on data volume and consistency across sources.

## Output Format

### Interview Summary (per transcript)
For each individual transcript or data source:
- **Metadata:** Date, participant name/role, participant background
- **Current solutions:** What they use today and satisfaction level
- **What they like:** Positive signals about current product or workflow
- **Problems identified:** Pain points in their own words, with direct quotes
- **Key discoveries:** Unexpected findings or insights that challenge assumptions
- **Follow-up actions:** Specific next steps with suggested ownership

### Cross-Interview Synthesis (when multiple sources provided)

#### Jobs to Be Done Map
| Job Statement | Frequency | Segments | Confidence |
|---|---|---|---|
| When [situation], I want to [motivation], so I can [outcome] | X of N sources | Segment names | High/Med/Low |

#### Actionable Insights
Numbered list of insight statements using the format: "We learned that [finding] which means [implication] so we should [recommendation]."

#### Open Questions
What the data did NOT answer and recommended next research steps.

## Frameworks & Best Practices
- **Jobs to Be Done (JTBD).** Frame every finding as a job the customer is trying to accomplish, not a feature they want. Customers hire products to make progress in their lives.
- **Read before you summarize.** Always process the complete transcript before writing any summary. Partial reads produce biased synthesis.
- **Plain language over jargon.** Write summaries that are accessible to anyone on the team, including non-technical stakeholders. Avoid PM jargon unless the team uses it consistently.
- **Preserve direct quotes.** The most powerful data points are verbatim quotes that capture the participant's emotion, specificity, and language. "I spent 3 hours last Tuesday rebuilding the report" beats "reporting is hard."
- **Separate satisfaction from problems.** Explicitly track what users like about current solutions alongside what frustrates them. Knowing strengths prevents accidentally breaking them.
- **Current solutions reveal competitors.** Documenting what participants use today (including spreadsheets, manual processes, and workarounds) reveals the true competitive landscape, which is broader than direct product competitors.
- **Frequency is not importance.** A pain point mentioned by 2 of 10 users may be more critical than one mentioned by 8 if those 2 users represent your ideal customer profile.
- **Bias awareness.** Note recruitment bias (who was NOT interviewed), leading question bias (review the interview script), and survivorship bias (current users vs. churned users).
- **Minimum viable sample.** For qualitative research, 5-8 interviews per segment typically reach thematic saturation. Flag if the sample is below this threshold.
- **Triangulation.** Cross-reference findings across data types. An insight supported by interviews AND support tickets AND survey data is stronger than one source alone.
- **Continuous discovery.** Treat interview synthesis as an ongoing practice, not a one-time project. Regular weekly interviews compound into deep customer understanding over time.

## Related Skills
- `prd-writing` -- Chain research synthesis directly into the Background and Market Segments sections of a PRD.
- `competitive-analysis` -- Combine customer insights with competitive data to identify underserved jobs where competitors fall short.
- `feedback-synthesis` -- Chain when you have a mix of structured feedback data (tickets, NPS) alongside interview transcripts.

## Examples

### Example 1: Single interview summary
**User:** "Here's a transcript from our discovery interview with a logistics manager. Summarize it."

**Good output excerpt:**
> **Metadata:** March 10, 2026 | Sarah Chen, Logistics Manager at MidCo (150 employees)
>
> **Current solutions:** Uses a combination of Excel spreadsheets and email chains to coordinate shipments. Satisfaction: 3/10. "It works but I lose about 5 hours a week just keeping everything in sync."
>
> **Problems identified:**
> - No single source of truth for shipment status (mentioned 4 times)
> - Cannot see driver availability in real time; relies on phone calls
> - Reporting to management requires manual data compilation every Friday
>
> **Key discovery:** Sarah's team has built an informal Slack channel as a workaround for real-time updates. This was not anticipated in our research plan and suggests messaging integration may be higher priority than dashboard features.

### Example 2: Multi-interview synthesis
**User:** "I just finished 8 customer interviews for our B2B scheduling tool. Here are the transcripts. What are the key takeaways?"

**Good output excerpt:**
> **JTBD #1 (7/8 interviews, High confidence):** "When I'm coordinating meetings across 3+ time zones, I want to see everyone's availability in one view, so I can book a slot without 6 back-and-forth emails."
>
> **Insight:** We learned that multi-timezone scheduling is the primary job, not calendar management broadly. This means our positioning should lead with "global team coordination" rather than "smart calendar." We should prioritize the timezone overlay feature in the next sprint.
>
> **Open question:** None of the 8 participants were solo users. We still do not know whether the product has value for individuals without teams.
