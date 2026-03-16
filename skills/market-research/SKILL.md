---
name: market-research
description: When the user needs to estimate market size, understand market dynamics, or validate that a market opportunity is large enough to pursue.
related: [competitive-analysis, prd-writing]
reads: [startup-context]
---

# Market Research

## When to Use
Activate when a founder needs to size a market opportunity using TAM/SAM/SOM, validate market assumptions for a pitch deck, understand growth trends, evaluate market entry, or prepare for investor conversations about addressable market. Trigger phrases include "how big is our market," "TAM/SAM/SOM," "market size," "market opportunity," "is this market big enough," "market trends," "help me with the market slide," or "validate our market assumptions."

## Context Required
- **From startup-context:** product description, target customer segments, pricing model, geographic scope, business model.
- **From the user:** the market or segment to analyze, known data points (industry reports, customer counts, pricing benchmarks), geographic and industry constraints, whether this is for internal decision-making or external presentation (investor deck), and any specific hypotheses about market dynamics.

## Workflow
1. **Define market boundaries** -- Specify the problem space, customer segments, geography, and constraints. "Project management tools" is a different market than "team collaboration software." Precision determines whether the analysis is useful.
2. **Top-down estimation** -- Start from total industry size using industry reports, public company revenues, and government statistics. Narrow to the relevant segment by applying filters for geography, customer type, and product category.
3. **Bottom-up estimation** -- Build independently from unit economics: (number of potential customers) x (price per customer) x (purchase frequency). Cross-validate against the top-down estimate.
4. **Scope the SAM** -- Identify which portion of TAM is realistically serviceable given current product capabilities, pricing, distribution channels, and geographic reach.
5. **Estimate the SOM** -- Project achievable market share in 1-3 years based on competitive position, go-to-market capacity, and current traction.
6. **Project growth** -- Forecast how TAM, SAM, and SOM evolve over 2-3 years. Identify key growth drivers, technology shifts, regulatory changes, and demographic trends.
7. **Map assumptions** -- Surface every critical assumption underlying each estimate. Rate confidence levels and identify how to validate the most uncertain assumptions.

## Output Format

### Market Definition
One paragraph defining the problem space, customer need, geographic and segment boundaries, and key scoping decisions.

### TAM / SAM / SOM

| Metric | Current Estimate | 2-3 Year Projection | Method | Confidence |
|---|---|---|---|---|
| **TAM** | $X | $Y | Top-down + Bottom-up | High/Med/Low |
| **SAM** | $X | $Y | Filtered from TAM | High/Med/Low |
| **SOM** | $X | $Y | Penetration model | High/Med/Low |

### Sizing Methodology
**Top-Down:** Step-by-step calculation from industry totals to target segment. Show every filter and assumption applied.

**Bottom-Up:** Step-by-step calculation from unit economics up. Show: (number of target customers) x (expected conversion rate) x (annual contract value).

**Reconciliation:** Comparison of both approaches, explanation of any gaps, and reconciled estimate. If they diverge by more than 3x, investigate the assumptions driving the gap.

### Growth Drivers & Trends
Key factors that could expand or contract the market -- technology shifts, regulatory changes, demographic trends, behavioral changes, and emerging adjacent segments.

### Key Assumptions & Risks
| Assumption | Impact if Wrong | Confidence | Validation Method |
|---|---|---|---|
| Description | What changes in the estimate | High/Med/Low | How to test this |

### Strategic Implications
Numbered list of what the market data means for product, pricing, and go-to-market decisions.

## Frameworks & Best Practices
- **Always do both top-down and bottom-up.** Top-down is fast but abstract. Bottom-up is precise but assumption-heavy. The truth is where they converge. Providing both triangulates and builds credibility with investors.
- **Beware vanity TAMs.** "The global software market is $500B" is not useful. Define the market narrowly enough that you can name the buyer persona, their budget line item, and what they pay today.
- **The "who writes the check" test.** Market size should be based on the actual budget your product replaces or claims. A $50/month tool's market is (number of buyers) x ($600/year), not the total revenue of the industry you serve.
- **Growth rate matters more than current size.** A $500M market growing 40% annually is more attractive than a $5B market growing 3%. Investors and founders should optimize for tailwinds.
- **Distinguish value-based from volume-based sizing.** Revenue-based (dollars) and volume-based (users/units) tell different stories. Be explicit about which you are using and why.
- **Assumption sensitivity analysis.** Identify the 2-3 assumptions that most affect your estimate. Show what happens if each is 50% lower. If the market is still attractive at the pessimistic end, the thesis is robust.
- **Source hierarchy for credibility:** (1) Government statistics and census data, (2) Public company filings and earnings calls, (3) Industry association reports, (4) Analyst reports (Gartner, Forrester, IDC), (5) Startup databases (PitchBook, Crunchbase), (6) Your own primary research and customer data.
- **Cite sources for market data.** Avoid unsupported numbers. Label what is an estimate vs. what is sourced data. Flag where estimates have wide confidence intervals.
- **Geographic specificity.** Global TAMs are meaningful only if you plan to sell globally from day one. Start with the geography and segment you will actually target first.
- **Adjacent market expansion.** After sizing the core market, identify 1-2 adjacent markets you could expand into. This shows a growth path beyond the initial wedge.
- **Consider currency and purchasing power parity** for international market sizing.

## Related Skills
- `competitive-analysis` -- Pair market sizing with competitive landscape analysis to understand both the size of the prize and how contested it is.
- `prd-writing` -- Use market segment data to ground the Market Segments section of a PRD in real numbers.
- `roadmap-planning` -- Use growth trend analysis to time roadmap investments. Build for fast-growing segments first.

## Examples

### Example 1: Market sizing for a pitch deck
**User:** "Help me size the market for our developer productivity tool. We need the TAM/SAM/SOM for our Series A deck."

**Good output excerpt:**
> **TAM:** $[X]B -- Global developer tools market (source: [industry report], includes IDEs, testing, CI/CD, monitoring, and productivity tools).
>
> **SAM:** $4.2B -- Code review and collaboration segment, filtered to teams of 10-500 developers at companies with >$5M revenue in North America and Europe.
>
> **SOM:** $85M -- 2% penetration of SAM over 4 years, based on current growth rate of 15% QoQ and average ACV of $18K.
>
> **Bottom-up cross-check:** 23,000 target companies x 12% expected conversion at maturity x $18K ACV = $49.7M.

### Example 2: New segment validation
**User:** "We're thinking about expanding from SMB to mid-market. Is that market big enough?"

**Good output should** size the mid-market segment separately, compare unit economics (higher ACV but longer sales cycle), estimate the investment required to serve the segment (enterprise features, sales team), and calculate whether the segment-level SOM justifies the investment within the planning horizon.
