---
name: user-research-synthesis
trigger: When the user has raw customer interview transcripts, survey responses, support tickets, or other qualitative data and needs to extract actionable insights.
related: [prd-writing, competitive-analysis]
reads: [startup-context]
---

# User Research Synthesis

## When to Use
Activate when a founder or PM provides raw qualitative research data and needs it synthesized into structured insights. This includes customer interview transcripts, survey open-ended responses, support ticket logs, NPS verbatims, sales call notes, app store reviews, or community forum posts. Trigger phrases include "summarize these interviews," "what are customers telling us," "synthesize this feedback," or "build personas from this data."

## Context Required
- **From startup-context:** product stage, current customer segments, known hypotheses being tested, existing personas (if any).
- **From the user:** the raw data sources, research questions being investigated, number of participants/responses, any specific hypotheses to validate or invalidate.

## Workflow
1. **Inventory the data** — Catalog what was provided: number of sources, type (interview, survey, ticket), participant demographics, date range.
2. **Code the data** — Read through all sources and tag recurring themes, pain points, desires, behaviors, and quotes. Group by theme.
3. **Apply JTBD framework** — For each major theme, frame it as a Job to Be Done: "When [situation], I want to [motivation], so I can [expected outcome]."
4. **Identify patterns and outliers** — Count theme frequency, note which segments share which themes, and flag surprising outliers that may signal emerging needs.
5. **Build or update personas** — Create evidence-based personas grounded in the data, not assumptions. Each persona gets a JTBD map.
6. **Generate insight statements** — Write actionable insight statements in the format: "We learned that [finding] which means [implication] so we should [recommendation]."
7. **Assess confidence levels** — Rate each insight as high/medium/low confidence based on data volume and consistency.

## Output Format

### Research Summary
- Data sources inventory (type, count, date range)
- Key research questions and whether they were answered

### Jobs to Be Done Map
| Job Statement | Frequency | Segments | Confidence |
|---|---|---|---|
| When [situation], I want to [motivation], so I can [outcome] | X of N sources | Segment names | High/Med/Low |

### Persona Cards (1-3 personas)
For each persona:
- **Name and archetype** (e.g., "Dana the Delegator")
- **Demographics:** role, company size, experience level
- **Primary JTBD:** the most important job they hire the product for
- **Pain points:** top 3, ranked by severity
- **Current workarounds:** what they do today without your product
- **Key quotes:** 2-3 verbatim quotes from the data
- **Willingness to pay signals:** any pricing or value indicators

### Actionable Insights
Numbered list of insight statements with confidence ratings.

### Open Questions
What the data did NOT answer and recommended next research steps.

## Frameworks & Best Practices
- **Jobs to Be Done (JTBD).** Frame every finding as a job the customer is trying to accomplish, not a feature they want. Customers buy outcomes, not products.
- **The "5 Whys" for depth.** When a transcript says "I want a dashboard," ask why five times to reach the real job: visibility, accountability, reporting to stakeholders, etc.
- **Frequency is not importance.** A pain point mentioned by 2 of 10 users may be more critical than one mentioned by 8 if those 2 users represent your ideal customer profile.
- **Separate observation from interpretation.** Tag raw data as observations. Insights are interpretations of patterns across observations. Never present an interpretation as a direct finding.
- **Minimum viable sample.** For qualitative research, 5-8 interviews per segment typically reach thematic saturation. Flag if the sample is below this threshold.
- **Quote selection.** Choose quotes that are specific and vivid, not generic. "I spent 3 hours last Tuesday rebuilding the report my manager needed" beats "Reporting is hard."
- **Bias awareness.** Note recruitment bias (who was NOT interviewed), leading question bias (review the interview script), and survivorship bias (current users vs. churned users).
- **Triangulation.** Cross-reference findings across data types. An insight supported by interviews AND support tickets AND survey data is stronger than one source alone.

## Related Skills
- `prd-writing` — Chain research synthesis directly into the Background and Market Segments sections of a PRD.
- `competitive-analysis` — Combine customer insights with competitive data to identify underserved jobs where competitors fall short.
- `mvp-scoping` — Use JTBD priority to determine which jobs the MVP must address vs. defer.

## Examples

### Example 1: Interview synthesis
**User:** "I just finished 8 customer interviews for our B2B scheduling tool. Here are the transcripts. What are the key takeaways?"

**Good output excerpt:**
> **JTBD #1 (7/8 interviews, High confidence):** "When I'm coordinating meetings across 3+ time zones, I want to see everyone's availability in one view, so I can book a slot without 6 back-and-forth emails."
>
> **Insight:** We learned that multi-timezone scheduling is the primary job, not calendar management broadly. This means our positioning should lead with "global team coordination" rather than "smart calendar." We should prioritize the timezone overlay feature in the next sprint.

### Example 2: Multi-source synthesis
**User:** "Synthesize these 200 support tickets, our latest NPS survey (n=450), and 5 churned-customer interviews."

**Good output excerpt should include** a data inventory table, cross-referenced themes showing which sources each theme appears in, confidence ratings weighted by source diversity, and a clear distinction between "validated insights" (multi-source) and "emerging signals" (single-source).
