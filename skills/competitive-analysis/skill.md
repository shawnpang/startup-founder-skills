---
name: competitive-analysis
trigger: When the user needs to evaluate competitors, understand the competitive landscape, or position their product against alternatives.
related: [market-research, prd-writing]
reads: [startup-context]
---

# Competitive Analysis

## When to Use
Activate when a founder or PM needs to map the competitive landscape, evaluate specific competitors, or determine how to differentiate their product. Trigger phrases include "who are our competitors," "analyze this competitor," "how do we compare to X," "competitive landscape," "feature comparison," "how should we position against," or "what's our moat." Also activate before fundraising (investors will ask) or before entering a new market segment.

## Context Required
- **From startup-context:** company's product, target market, current positioning, key differentiators, pricing model.
- **From the user:** specific competitors to analyze (or request to identify them), dimensions of comparison that matter most, the strategic question driving the analysis (positioning, pricing, feature gaps, etc.).

## Workflow
1. **Identify the competitive set** — List direct competitors (same problem, same customer), indirect competitors (same problem, different approach), and alternatives (including the status quo of doing nothing or using spreadsheets).
2. **Gather intelligence** — For each competitor, collect data across the 6 analysis dimensions: product, pricing, positioning, distribution, team, and traction.
3. **Build feature comparison matrix** — Create a detailed feature-by-feature comparison for the capabilities that matter to the target customer segment.
4. **Map positioning** — Plot competitors on a 2x2 positioning matrix using the two dimensions most relevant to the user's market.
5. **Identify gaps and opportunities** — Find underserved areas where no competitor excels, over-served areas where competitors over-invest, and table-stakes features where parity is required.
6. **Formulate strategic recommendations** — Translate findings into positioning, feature, and go-to-market recommendations.

## Output Format

### Competitive Landscape Overview
One paragraph summarizing the market structure: how many players, how fragmented, major categories of solutions.

### Competitor Profiles
For each competitor (typically 3-6):

| Dimension | Details |
|---|---|
| **Product** | Core features, UX quality, platform/integrations, technical architecture (if known) |
| **Pricing** | Model (freemium, usage, seat-based), price points, free tier limits, enterprise deals |
| **Positioning** | Tagline, target persona, key messaging, category they claim |
| **Distribution** | Primary channels (PLG, sales-led, partnerships), content strategy, community presence |
| **Team** | Founders' backgrounds, team size, key hires, domain expertise |
| **Traction** | Funding raised, estimated revenue/users (from public data), growth signals, notable customers |

### Feature Comparison Matrix
| Feature | Your Product | Competitor A | Competitor B | Competitor C |
|---|---|---|---|---|
| Feature 1 | Full / Partial / None | Full / Partial / None | ... | ... |
| Feature 2 | ... | ... | ... | ... |

Use icons or labels: Full (complete implementation), Partial (limited), None (absent), Beta (in development).

### Positioning Matrix
A 2x2 grid with the two most strategically relevant axes (e.g., "ease of use vs. feature depth" or "SMB-focus vs. enterprise-focus"). Place each competitor and your product on the grid.

### Strategic Insights
Numbered list of findings:
1. **Gaps** — Where no competitor serves the need well.
2. **Table stakes** — What every competitor has that you must match.
3. **Over-served areas** — Where competitors over-invest and customers don't care.
4. **Differentiation opportunities** — Where you can credibly win.

### Recommendations
Specific actions for product, positioning, and go-to-market based on the analysis.

## Frameworks & Best Practices
- **The 6-dimension framework** (Product, Pricing, Positioning, Distribution, Team, Traction) ensures a holistic view. Product-only comparisons miss half the competitive picture.
- **Compete on a different axis.** If incumbents compete on features, compete on simplicity. If they compete on price, compete on experience. Winning means changing the criteria, not beating incumbents at their own game.
- **Status quo is your biggest competitor.** For most startups, the real competitor is "do nothing" or "use a spreadsheet." Analyze this alternative with the same rigor as named competitors.
- **Signal vs. noise in traction data.** Funding raised is not traction. Revenue, user count, and growth rate are traction. A well-funded competitor with flat growth is weaker than an unfunded one growing 20% month-over-month.
- **Positioning matrix rules.** Choose axes that (a) matter to customers and (b) create a quadrant where your product lives alone or with few others. If every competitor clusters in one quadrant, the axes are wrong.
- **Feature comparison honesty.** Mark your own product's gaps honestly. An internal competitive analysis that overstates your strengths is useless. The purpose is to find truth, not to feel good.
- **Refresh cadence.** Competitive landscapes change. Update this analysis quarterly for fast-moving markets, semi-annually for slower ones.
- **Primary sources over secondhand.** Use the competitor's own product (sign up for free trials), pricing page, job postings (reveal strategy), and customer reviews (G2, Capterra) over analyst reports and blog posts.
- **Job postings as strategy signals.** A competitor hiring ML engineers signals AI investment. Hiring enterprise sales reps signals upmarket movement. Hiring in a new geography signals expansion.

## Related Skills
- `market-research` — Combine competitive analysis with market sizing to understand both the landscape and the prize.
- `prd-writing` — Use competitive gaps to inform the Solution section of a PRD — build what competitors miss.
- `user-research-synthesis` — Ground competitive feature comparisons in what customers actually value, not what competitors assume they value.

## Examples

### Example 1: Direct competitor deep-dive
**User:** "Analyze how we compare to Competitor X. We keep losing deals to them."

**Good output excerpt:**
> **Key finding:** Competitor X wins on perceived enterprise readiness (SOC 2 badge, SSO, audit logs) even though their core product scores lower on usability in G2 reviews. You're losing deals not on product quality but on a compliance checkbox.
>
> **Recommendation:** Achieve SOC 2 Type II within the next quarter. This removes the objection without requiring you to match their feature set. In parallel, lead sales conversations with your usability advantage — demo head-to-head to shift evaluation criteria.

### Example 2: Landscape mapping for fundraising
**User:** "I need a competitive landscape slide for our Series A deck."

**Good output should include** a clean 2x2 positioning matrix showing clear whitespace where the startup sits, a brief profile of 4-5 competitors highlighting their weaknesses relative to the startup's strengths, and a narrative about why the competitive dynamics favor the startup's approach.
