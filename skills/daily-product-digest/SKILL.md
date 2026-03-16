---
name: daily-product-digest
description: When the user wants a summary of what's trending on Product Hunt, Hacker News, Indie Hackers, or other product/startup communities. Also use when the user mentions "what launched today", "trending products", "HN front page", or "keep up with the market".
related: [competitive-analysis, market-research, launch-strategy]
reads: [startup-context]
---

# Daily Product Digest

## When to Use
- Founder wants a daily or weekly summary of what's happening in the startup/product ecosystem
- Founder wants to track competitor launches and market trends
- Founder wants to identify products launching in their space or adjacent spaces
- Founder wants launch inspiration or to study what's getting traction
- Founder wants to spot emerging trends, tools, or technologies relevant to their market

## Context Required
- Founder's product category and market (to filter for relevance)
- Sources to monitor (Product Hunt, Hacker News, Indie Hackers, Reddit, etc.)
- Frequency (daily, weekly, or on-demand)
- What they care about most (competitor activity, market trends, launch tactics, technology shifts)

## Workflow

1. **Define monitoring scope** — based on startup-context, identify:
   - Keywords and categories to track (e.g., "developer tools", "AI", "fintech")
   - Direct competitors to watch for
   - Adjacent markets that could expand into your space
2. **Scan sources** — check each platform for the specified time period:
   - **Product Hunt:** top launches, upvote counts, maker comments, notable hunters
   - **Hacker News:** front page stories, Show HN posts, Ask HN threads, comment sentiment
   - **Indie Hackers:** new launches, revenue milestones, popular discussions
   - **Reddit:** relevant subreddit activity (r/SaaS, r/startups, r/[your-niche])
3. **Filter for relevance** — from everything found, flag items that are:
   - Direct competitors or alternatives to the founder's product
   - In the same category or solving adjacent problems
   - Demonstrating a trend or shift relevant to the founder's market
   - Using interesting launch tactics worth studying
4. **Analyze what's working** — for top-performing launches/posts, note:
   - What made it resonate (positioning, timing, problem framing)
   - Community reaction and sentiment
   - Potential implications for the founder's product or market
5. **Generate the digest** — produce a concise, actionable summary.

## Output Format

```markdown
## Product Digest — [Date or Date Range]

### Relevant to You
Items directly related to your market ([category]).

**[Product/Post Name]** — [one-line description]
- Source: [Product Hunt / HN / etc.] | [upvotes/points] | [link]
- Why it matters: [relevance to founder's product/market]
- Takeaway: [what to learn or watch]

### Competitor Activity
- [Competitor] launched [feature/product] on [platform] — [reaction summary]

### Market Trends
- **[Trend]:** [2-3 sentence summary of what's shifting and why it matters]

### Launch Tactics Worth Noting
- [Product] did [tactic] and got [result] — applicable to your launch because [reason]

### Worth Reading
- [Title] ([source]) — [why it's worth the founder's time]
```

## Frameworks & Best Practices

**Source-specific signals:**
| Source | What to watch | Signal of quality |
|--------|--------------|-------------------|
| Product Hunt | Top 5 daily launches | 500+ upvotes, maker engagement in comments |
| Hacker News | Front page, Show HN | 100+ points, substantive comment threads |
| Indie Hackers | Product launches, milestones | Revenue numbers shared, detailed build stories |
| Reddit | Niche subreddits | High comment-to-upvote ratio, genuine discussion |

**What makes a digest useful:**
- **Ruthless filtering** — a 20-item list is noise. Pick 3-5 items that actually matter to this founder's situation.
- **"So what?" for each item** — don't just report what launched. Explain why the founder should care.
- **Actionable takeaways** — end each item with what the founder could do (watch this competitor, study this tactic, consider this positioning angle).
- **Pattern recognition** — after doing this regularly, highlight emerging patterns ("third AI coding tool this week targeting enterprise — market is heating up").

**Common mistakes:**
- Reporting everything instead of filtering for relevance
- Missing the comments/discussion (often more valuable than the launch itself)
- Treating all sources equally (HN comments are gold for developer sentiment; PH upvotes can be gamed)
- Not connecting findings to the founder's own strategy

## Related Skills
- `competitive-analysis` — for deep competitor research beyond daily monitoring
- `market-research` — for structured market sizing and trend analysis
- `launch-strategy` — to apply launch tactics observed in the wild

## Examples

**Prompt:** "What launched on Product Hunt and Hacker News today that's relevant to my API monitoring startup?"

**Good output includes:** Filtered digest of today's launches related to APIs, monitoring, observability, or developer tools. For each relevant item: what it does, how it performed, community reaction, and whether it's a competitor or adjacent product.

**Prompt:** "Give me a weekly roundup of what's happening in the AI coding tools space."

**Good output includes:** Summary of AI coding launches/updates across PH, HN, and Reddit from the past week, trend analysis (what themes keep recurring), competitor moves, and 2-3 tactical observations the founder can act on.
