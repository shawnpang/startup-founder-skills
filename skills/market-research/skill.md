---
name: market-research
trigger: When the user needs to estimate market size, understand market dynamics, or validate that a market opportunity is large enough to pursue.
related: [competitive-analysis, prd-writing]
reads: [startup-context]
---

# Market Research

## When to Use
Activate when a founder needs to size a market opportunity, validate market assumptions for a pitch deck, understand growth trends in their space, or decide whether a new segment is worth entering. Trigger phrases include "how big is our market," "TAM/SAM/SOM," "market size," "is this market big enough," "market trends," "help me with the market slide," or "validate our market assumptions."

## Context Required
- **From startup-context:** product description, target customer segments, pricing model, geographic scope, business model.
- **From the user:** the market or segment to analyze, known data points (industry reports, customer counts, pricing benchmarks), whether this is for internal decision-making or external presentation (investor deck), and any specific hypotheses about market dynamics.

## Workflow
1. **Define the market boundaries** — Clarify what is and is not included in the market definition. A "project management tool" market is different from a "team collaboration software" market. Precision here determines whether the analysis is useful.
2. **Top-down sizing** — Start with the broadest credible market data (industry reports, public company revenues, government statistics) and narrow to the relevant segment.
3. **Bottom-up sizing** — Calculate independently by estimating: (number of potential customers) x (average revenue per customer) x (expected penetration rate).
4. **Triangulate** — Compare top-down and bottom-up estimates. If they diverge by more than 3x, investigate the assumptions driving the gap.
5. **Analyze growth trends** — Identify growth rate, key drivers of growth, and potential headwinds. Distinguish between cyclical and structural trends.
6. **Assess risks and assumptions** — Document every assumption underlying the estimates and rate its fragility.
7. **Synthesize and recommend** — Present findings with clear confidence intervals and strategic implications.

## Output Format

### Market Definition
One paragraph defining the market boundaries, what's included, what's excluded, and why.

### TAM / SAM / SOM

| Level | Definition | Estimate | Method | Confidence |
|---|---|---|---|---|
| **TAM** (Total Addressable Market) | Total demand for the category if every potential buyer purchased | $X | Top-down / Bottom-up | High/Med/Low |
| **SAM** (Serviceable Addressable Market) | Portion of TAM reachable with your product, pricing, and distribution | $X | Filtered from TAM | High/Med/Low |
| **SOM** (Serviceable Obtainable Market) | Realistic share you can capture in 3-5 years given competition and execution | $X | Penetration model | High/Med/Low |

### Sizing Methodology

#### Top-Down Approach
Step-by-step calculation from industry totals to your segment. Show every filter and assumption.

#### Bottom-Up Approach
Step-by-step calculation from unit economics up. Show: (number of target companies/users) x (expected conversion rate) x (annual contract value).

#### Triangulation
Comparison of approaches, explanation of any gaps, and reconciled estimate.

### Growth Trends
| Trend | Direction | Impact | Timeframe | Source |
|---|---|---|---|---|
| Trend name | Growing/Declining/Stable | High/Med/Low | Years | Data source |

### Key Assumptions and Risks
| Assumption | Impact if Wrong | Fragility | Validation Method |
|---|---|---|---|
| Description | What changes in the estimate | High/Med/Low | How to test this |

### Strategic Implications
Numbered list of what the market data means for product, pricing, and go-to-market decisions.

## Frameworks & Best Practices
- **TAM/SAM/SOM hierarchy.**
  - **TAM** answers: "How big is the entire opportunity?" Use this to show investors the ceiling.
  - **SAM** answers: "How much can we realistically address with our current product and model?" This is your planning number.
  - **SOM** answers: "How much can we actually capture in the next 3-5 years?" This is your forecasting number. SOM should be 1-5% of SAM for most early-stage startups.
- **Top-down vs. bottom-up: always do both.** Top-down is fast but abstract. Bottom-up is precise but requires assumptions about customer counts and conversion. The truth is where they converge.
- **Beware vanity TAMs.** "The global software market is $500B" is not useful. Define the market narrowly enough that you could name the buyer persona, their budget line item, and what they pay today.
- **The "who writes the check" test.** Your market size should be based on the actual budget your product replaces or claims. If you're selling a $50/month tool, your market is (number of buyers) x ($600/year), not the total revenue of the industry you serve.
- **Growth rate matters more than current size.** A $500M market growing 40% annually is more attractive than a $5B market growing 3%. Investors and founders should optimize for tailwinds.
- **Assumption sensitivity analysis.** Identify the 2-3 assumptions that most affect your estimate. Show what happens if each is 50% lower. If the market is still attractive at the pessimistic end, the thesis is robust.
- **Source hierarchy for credibility.**
  1. Government statistics and census data (most credible)
  2. Public company filings and earnings calls
  3. Industry association reports
  4. Analyst reports (Gartner, Forrester, IDC)
  5. Startup databases (PitchBook, Crunchbase)
  6. Your own primary research and customer data
- **Geographic and segment specificity.** Global TAMs are meaningful only if you plan to sell globally from day one. Start with the geography and segment you'll actually target first.
- **Adjacent market expansion.** After sizing the core market, identify 1-2 adjacent markets you could expand into. This shows a growth path beyond the initial wedge.

## Related Skills
- `competitive-analysis` — Pair market sizing with competitive landscape analysis to understand both the size of the prize and how contested it is.
- `prd-writing` — Use market segment data to ground the Market Segments section of a PRD in real numbers.
- `roadmap-planning` — Use growth trend analysis to time roadmap investments. Build for fast-growing segments first.

## Examples

### Example 1: Market sizing for a pitch deck
**User:** "Help me size the market for our developer productivity tool. We need the TAM/SAM/SOM for our Series A deck."

**Good output excerpt:**
> **TAM:** $28B — Global developer tools market (source: IDC 2025, includes IDEs, testing, CI/CD, monitoring, and productivity tools).
>
> **SAM:** $4.2B — Code review and collaboration segment, filtered to teams of 10-500 developers at companies with >$5M revenue in North America and Europe.
>
> **SOM:** $85M — 2% penetration of SAM over 4 years, based on current growth rate of 15% QoQ and average ACV of $18K.
>
> **Bottom-up cross-check:** 23,000 target companies x 12% expected conversion at maturity x $18K ACV = $49.7M. The $85M SOM assumes pricing expansion and geographic growth beyond the initial wedge.

### Example 2: New segment validation
**User:** "We're thinking about expanding from SMB to mid-market. Is that market big enough?"

**Good output should** size the mid-market segment separately, compare unit economics (higher ACV but longer sales cycle), estimate the investment required to serve the segment (enterprise features, sales team), and calculate whether the segment-level SOM justifies the investment within the planning horizon.
