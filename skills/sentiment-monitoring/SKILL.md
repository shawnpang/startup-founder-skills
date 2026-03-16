---
name: sentiment-monitoring
description: When the user wants to monitor reviews, mentions, and community sentiment about their own product. Also use when the user mentions "track our reviews", "what are people saying about us", "brand monitoring", "reputation management", or "review alerts".
related: [review-mining, feedback-synthesis, churn-analysis, community-discovery]
reads: [startup-context]
---

# Sentiment Monitoring

## When to Use
- Founder wants to track what customers and the public are saying about their product
- Founder wants to catch bad reviews early and respond before they spread
- Founder wants to understand community sentiment trends over time
- Founder wants to monitor specific review platforms for new reviews

This is **different from `review-mining`** (mining competitor reviews for pain points). This skill monitors your OWN product's reputation.

## Context Required
- **Product name** and any common misspellings or abbreviations
- **Platforms to monitor** — the founder must provide the list of places to watch. Common options:
  - Product Hunt (product page reviews and comments)
  - Google Maps / Google Business reviews
  - G2, Capterra, TrustRadius
  - Trustpilot
  - App Store / Play Store
  - Reddit mentions
  - Twitter/X mentions
  - Hacker News mentions
  - Industry-specific forums
- **Monitoring frequency** (daily for post-launch, weekly for steady state)
- **Response policy** — does the founder want draft responses for negative reviews?
- **Escalation threshold** — what severity warrants immediate attention?

## Workflow

1. **Set up the monitoring list** — the founder provides which platforms to watch. For each platform, note:
   - Direct URL to the product's review/listing page
   - Current rating and review count (baseline)
   - How to check for new reviews (RSS, manual, API, or alert tool)
2. **Define the severity scale** — categorize incoming sentiment:
   - **Critical** (respond within 24h): public accusations of data loss, security issues, billing fraud, or legal threats. 1-star reviews with detailed complaints that could go viral.
   - **Negative** (respond within 48h): legitimate complaints about bugs, missing features, poor support, or pricing frustration. 1-2 star reviews.
   - **Mixed** (respond within 1 week): 3-star reviews with constructive feedback. "Good product but..."
   - **Positive** (acknowledge): 4-5 star reviews. Thank the reviewer, ask for referrals.
3. **Scan platforms** — check each platform on the founder's list for new reviews, mentions, or discussions since the last scan.
4. **Analyze each finding** — for every new review or mention:
   - **Platform and date**
   - **Sentiment:** positive / mixed / negative / critical
   - **Core issue:** what specifically is the person saying (quote verbatim)
   - **Validity:** is this a legitimate product issue, user error, or bad-faith review?
   - **Impact:** how visible is this? (high-traffic platform, many upvotes, or buried)
   - **Pattern:** does this match other recent complaints? (signals a systemic issue)
5. **Draft responses** — for negative and critical reviews, draft a response that:
   - Acknowledges the issue without being defensive
   - Shows the complaint was heard and understood
   - Offers a specific next step (DM, email, fix timeline)
   - Is written in the founder's voice, not corporate PR speak
6. **Flag patterns** — if 3+ reviews mention the same issue, escalate it as a product issue, not just a review problem.
7. **Generate the sentiment report** — summary of findings with trends.

## Output Format

```markdown
## Sentiment Report — [Date Range]

### Overview
- **Reviews scanned:** [count across all platforms]
- **New since last scan:** [count]
- **Sentiment breakdown:** [X positive, Y mixed, Z negative, W critical]
- **Average rating trend:** [up/down/stable vs. last period]

### Critical & Negative Items (action required)

**[Platform] — [Star Rating] — [Date]**
> "[Verbatim quote or summary]"
- **Core issue:** [what they're actually complaining about]
- **Validity:** [Legitimate / User error / Bad faith]
- **Pattern:** [First mention / Recurring — also seen on X, Y]
- **Suggested response:**
  > [Draft response in founder's voice]

### Emerging Patterns
| Issue | Mentions This Period | Platforms | First Seen | Trend |
|-------|---------------------|-----------|------------|-------|
| [Issue] | [count] | [platforms] | [date] | [new / growing / stable] |

### Positive Highlights
- [Platform]: "[positive quote]" — consider using as testimonial
- [Platform]: "[positive quote]" — share on social

### Recommended Actions
- [ ] Respond to [N] critical/negative reviews (drafts above)
- [ ] Investigate [issue] — mentioned [N] times across [platforms]
- [ ] Request reviews from happy customers to offset [negative trend]
```

## Frameworks & Best Practices

**Response principles for negative reviews:**
- **Speed matters** — respond within 24-48 hours. Unanswered negative reviews signal "they don't care."
- **Acknowledge, don't argue** — "I hear you" beats "Actually, you're wrong" every time
- **Take it offline** — "I'd love to look into this — can you email me at founder@company.com?" moves the conversation out of public view
- **Be the founder** — sign with your name and title. "— Alex, CEO" hits differently than a generic support reply
- **Fix the issue, then update** — come back to the review after fixing the problem: "We shipped a fix for this last week"

**Platform-specific notes:**
| Platform | Review visibility | Response capability | Notes |
|----------|------------------|--------------------|----|
| Product Hunt | High (launch day) | Comments only | Critical during and after launch. Engage in comments actively. |
| Google Maps | High (local SEO) | Owner response | Directly affects local search ranking. Respond to everything. |
| G2 | High (B2B buyers) | Vendor response | Enterprise buyers read these. Detailed responses matter. |
| Trustpilot | High (consumer) | Business response | Invite happy customers to balance. TrustScore affects visibility. |
| App Store | High (affects downloads) | Developer response | Apple limits response frequency. Be concise. |
| Reddit | Variable | Comment as user | Don't astroturf. Be transparent about who you are. |

**When negative reviews are actually gifts:**
- Specific, actionable complaints point to real product gaps — treat them as free user research
- A pattern of "love the product but X is broken" means you have product-market fit with a fixable issue
- No negative reviews at all usually means no one is using the product

**Common mistakes:**
- Monitoring without responding (worse than not monitoring)
- Getting defensive or arguing publicly with reviewers
- Only monitoring one platform (customers complain wherever they are, not where you're watching)
- Treating all negative reviews equally (a billing fraud accusation ≠ a UI complaint)
- Not feeding review insights back into the product roadmap

## Related Skills
- `review-mining` — for mining COMPETITOR reviews (this skill monitors YOUR reviews)
- `feedback-synthesis` — for synthesizing feedback patterns into product decisions
- `churn-analysis` — negative reviews often correlate with churn signals
- `community-discovery` — to find communities where people discuss your product

## Examples

**Prompt:** "Set up monitoring for our reviews. We're on Product Hunt, G2, Trustpilot, and the App Store."

**Good output includes:** Monitoring checklist for all 4 platforms with current baselines, severity scale customized to the product, and a template for the weekly sentiment report.

**Prompt:** "We got 3 bad reviews on G2 this week. Help me respond."

**Good output includes:** Analysis of each review (core issue, validity, pattern detection), draft responses in the founder's voice, and a flag if the issues point to a systemic product problem.
