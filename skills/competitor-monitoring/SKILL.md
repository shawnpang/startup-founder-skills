---
name: competitor-monitoring
description: When the user wants to set up ongoing tracking of competitor activity — pricing changes, feature launches, hiring signals, content, or public mentions. Also use when the user mentions "track competitors", "what are competitors doing", "competitor alerts", or "market watch".
related: [competitive-analysis, daily-product-digest, review-mining, market-research]
reads: [startup-context]
---

# Competitor Monitoring

## When to Use
- Founder wants to know when competitors change pricing, ship features, or raise funding
- Founder wants a recurring "what changed this week" scan of competitor activity
- Founder wants to detect strategic shifts from competitor job postings, blog posts, or product updates
- Founder wants to stay informed without manually checking 10 websites daily

This is the **recurring sibling** of `competitive-analysis` (one-time deep dive). Use this skill for ongoing monitoring, not initial research.

## Context Required
- List of 3-7 competitors to track (names, websites, product URLs)
- What the founder cares about most (pricing, features, positioning, hiring, funding, content)
- Monitoring frequency (weekly recommended for early-stage, biweekly for established markets)
- The founder's own positioning (to flag threats and opportunities)

## Workflow

1. **Define the monitoring surface** — for each competitor, identify what to watch:
   - **Pricing page** — plan changes, new tiers, free plan adjustments
   - **Changelog / release notes** — new features, deprecations, platform shifts
   - **Job postings** — engineering roles signal product direction, sales roles signal GTM shifts, exec hires signal strategy changes
   - **Blog / content** — new positioning, case studies (reveal target customers), thought leadership pivots
   - **Social media** — founder posts, company announcements, community reactions
   - **Review sites** — new reviews on G2, Capterra, Trustpilot (sentiment shifts)
   - **Funding / press** — Crunchbase alerts, press releases, media coverage
2. **Set up the monitoring stack** — recommend tools and manual checks:
   - **Automated:** Google Alerts (brand mentions), Visualping or ChangeTower (page change detection), Crunchbase alerts (funding), LinkedIn job alerts
   - **Manual weekly scan:** pricing pages, changelogs, recent blog posts, latest job postings
   - **Quarterly deep dive:** full `competitive-analysis` refresh
3. **Run the scan** — check all sources for the monitoring period and flag changes.
4. **Analyze signals** — for each change detected:
   - What changed (factual description)
   - What it signals (interpretation — are they moving upmarket? entering your segment? struggling with churn?)
   - Threat level (none / watch / respond / urgent)
   - Recommended action (if any)
5. **Generate the report** — produce a concise weekly/biweekly competitor intel brief.

## Output Format

```markdown
## Competitor Intel Brief — Week of [Date]

### Summary
[1-2 sentence overview: "Quiet week. Competitor A shipped a free tier. No pricing changes elsewhere."]

### Changes Detected

**[Competitor A]**
- **What changed:** [factual description]
- **Signal:** [what this likely means strategically]
- **Threat level:** [None / Watch / Respond / Urgent]
- **Recommended action:** [what to do, if anything]

**[Competitor B]**
- No changes detected this period.

### Job Posting Signals
| Competitor | New Roles | Signal |
|-----------|-----------|--------|
| [A] | 3 enterprise AEs, VP Sales | Moving upmarket |
| [B] | ML engineer, data scientist | Building AI features |

### Emerging Patterns
- [Pattern observed across multiple competitors or over time]

### Action Items
- [ ] [Specific action for the founder]
```

## Frameworks & Best Practices

**Reading job postings as strategy signals:**
| Role Type | What It Signals |
|-----------|----------------|
| Enterprise AEs / Sales Engineers | Moving upmarket or launching enterprise tier |
| DevRel / Community Manager | Investing in developer ecosystem or community-led growth |
| ML/AI Engineers | Building AI features or data products |
| International roles / specific geo | Expanding to new markets |
| Product Marketing Manager | Repositioning or launching new product lines |
| Head of Partnerships | Platform/ecosystem strategy |
| Lots of support hires | Scaling fast or struggling with quality |

**Threat level framework:**
- **None:** Routine activity, no impact on you
- **Watch:** Interesting move, could affect you in 3-6 months — add to next strategy discussion
- **Respond:** Directly affects your positioning, pricing, or target market — needs a plan within 2 weeks
- **Urgent:** Launches directly competing feature, undercuts your pricing, or targets your exact ICP — needs immediate response

**Common mistakes:**
- Monitoring too many competitors (pick 3-5, not 15)
- Reacting to every move instead of identifying patterns
- Confusing competitor activity with competitor success (they shipped a feature — doesn't mean it works)
- Ignoring indirect competitors and new entrants
- Not archiving snapshots (you'll want to see how their pricing page looked 6 months ago)

## Related Skills
- `competitive-analysis` — for the initial deep dive and periodic refresh
- `daily-product-digest` — for broader market monitoring beyond specific competitors
- `review-mining` — for tracking competitor sentiment on review platforms
- `market-research` — for understanding market shifts driving competitor behavior

## Examples

**Prompt:** "Set up competitor monitoring for our 4 main competitors in the email marketing space."

**Good output includes:** Monitoring surface for each competitor (pricing pages, changelogs, job boards, blogs), recommended tool stack for automated alerts, and a template for the weekly intel brief.

**Prompt:** "What have our competitors been up to this week?"

**Good output includes:** Scan of changelogs, pricing pages, blog posts, job postings, and social accounts for each tracked competitor. Flagged changes with signal interpretation and threat levels. Actionable summary.
