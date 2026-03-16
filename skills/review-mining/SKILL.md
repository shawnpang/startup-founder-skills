---
name: review-mining
description: When the user wants to research customer pain points, complaints, or sentiment using review platforms like Trustpilot, G2, Capterra, or app stores. Also use when the user mentions "what are users saying", "competitor reviews", "pain points", or "voice of customer research".
related: [competitive-analysis, user-research-synthesis, feedback-synthesis, cold-outreach]
reads: [startup-context]
---

# Review Mining

## When to Use
- Founder wants to understand real user pain points for a market or competitor product
- Founder wants voice-of-customer language to use in copy, emails, or pitch decks
- Founder wants to validate a product idea by finding recurring complaints
- Founder wants to identify gaps competitors aren't solving
- Founder wants to build a feature comparison based on what users actually care about

## Context Required
- Competitor names or product category to research
- Review platforms to mine (Trustpilot, G2, Capterra, Product Hunt, App Store, Play Store, Reddit)
- What the founder is trying to learn (pain points, switching triggers, feature gaps, use cases)
- The founder's own product positioning (to identify opportunities)

## Workflow

1. **Define research scope** — identify 3-5 competitors or products to analyze and which platforms have the most relevant reviews for the category (B2B → G2/Capterra, B2C → Trustpilot/App Store, developer tools → Reddit/HN).
2. **Collect reviews** — gather 1-3 star reviews (pain points) and 4-5 star reviews (what users love and would miss). Focus on reviews from the last 12 months for relevance. Aim for 50-100 reviews per competitor.
3. **Extract pain point themes** — categorize complaints into recurring themes. For each theme, capture:
   - The pain point in the user's own words (verbatim quotes)
   - Frequency (how many reviews mention it)
   - Severity (annoyance vs. deal-breaker vs. switching trigger)
   - Which competitor(s) it applies to
4. **Extract switching triggers** — find reviews where users explicitly say why they left or are considering leaving. These are gold for positioning and outreach.
5. **Extract "jobs to be done"** — from positive reviews, identify what users are actually hiring the product to do (often different from what the product markets itself as).
6. **Map to opportunities** — cross-reference pain points against your product's capabilities. Identify where you solve problems competitors don't.
7. **Generate artifacts** — produce the pain point report, voice-of-customer swipe file, and positioning recommendations.

## Output Format

```markdown
## Review Mining Report: [Category/Competitors]

### Research Scope
- Competitors analyzed: [list]
- Platforms: [list]
- Reviews analyzed: [count]
- Date range: [range]

### Top Pain Points (ranked by frequency x severity)

#### 1. [Pain Point Theme] — mentioned in [X]% of negative reviews
- **Severity:** [Annoyance / Frustration / Deal-breaker / Switching trigger]
- **Competitors affected:** [list]
- **User quotes:**
  - "[verbatim quote]" — [platform], [star rating]
  - "[verbatim quote]" — [platform], [star rating]
- **Your opportunity:** [how your product addresses or could address this]

#### 2. [Pain Point Theme] ...

### Switching Triggers
| Trigger | Frequency | From → To | Quote |
|---------|-----------|-----------|-------|
| ... | ... | ... | ... |

### Voice of Customer Swipe File
**Words users use for the problem:** [list of exact phrases]
**Words users use for the desired outcome:** [list of exact phrases]
**Emotional language:** [frustration words, relief words]

### Positioning Opportunities
- [Opportunity 1]: [what you can claim based on competitor weakness]
- [Opportunity 2]: [underserved use case you can own]
```

## Frameworks & Best Practices

**Where to mine by product type:**
| Product Type | Best Sources |
|-------------|-------------|
| B2B SaaS | G2, Capterra, TrustRadius |
| B2C / Consumer | Trustpilot, App Store, Play Store |
| Developer Tools | Reddit, Hacker News, GitHub Issues |
| E-commerce / DTC | Trustpilot, Amazon reviews |
| Any | Twitter/X complaints, Reddit threads |

**Review analysis principles:**
- **1-2 star reviews** reveal deal-breakers and switching triggers
- **3 star reviews** reveal "good enough but frustrated" — the most persuadable users
- **4-5 star reviews** reveal what users truly value (defend these in your product)
- **Recent reviews** (last 6-12 months) matter more than old ones
- **Verified purchase/user** reviews carry more weight

**Verbatim language is the output.** The exact words users use to describe their pain are more valuable than your summary. These become headlines, email subject lines, ad copy, and landing page copy.

**Common mistakes:**
- Only reading negative reviews (you miss what users actually value)
- Summarizing instead of quoting (you lose the authentic language)
- Treating all complaints equally (frequency x severity matters)
- Ignoring the context of who's reviewing (enterprise vs SMB, power user vs casual)
- Mining once and never returning (do this quarterly)

## Related Skills
- `competitive-analysis` — for broader competitor research beyond reviews
- `user-research-synthesis` — for synthesizing your own customer interviews
- `feedback-synthesis` — for analyzing feedback from your own users
- `cold-outreach` — use voice-of-customer language in prospecting emails

## Examples

**Prompt:** "I'm building a project management tool. What are the biggest pain points people have with Asana and Monday.com?"

**Good output includes:** Mining Trustpilot, G2, and Capterra for Asana and Monday.com, extracting the top 5-7 pain points with verbatim quotes, identifying switching triggers, and mapping them to positioning opportunities.

**Prompt:** "We're a Trustpilot alternative. Help me understand what businesses hate about Trustpilot."

**Good output includes:** Mining Trustpilot's own reviews (meta!), G2, and Reddit for complaints about Trustpilot, extracting themes like review gating, pricing, fake review handling, and producing a voice-of-customer swipe file the founder can use in outreach.
