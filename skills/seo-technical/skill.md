---
name: seo-technical
trigger: When the user needs a technical SEO audit, on-page optimization guidance, or help resolving crawlability, indexation, or performance issues that affect search rankings.
related: [content-strategy, landing-page]
reads: [startup-context]
---

# SEO Technical

## When to Use
- Running a technical SEO audit on an existing site.
- Diagnosing why pages are not being indexed or ranked.
- Optimizing Core Web Vitals or page speed.
- Setting up proper site architecture (sitemaps, robots.txt, canonicalization).
- Implementing structured data / schema markup.
- Preparing a new site or migration for SEO readiness.
- Reviewing on-page SEO elements (title tags, meta descriptions, heading structure).

## Context Required
- **From startup-context**: product description, target audience, primary keywords or topics, current domain and site structure.
- **From the user**: site URL, access to Google Search Console data (if available), specific pages of concern, known issues, tech stack (static site, SPA, WordPress, etc.), whether the site has been previously audited.

## Workflow
1. **Crawlability audit** — This is the foundation; nothing else matters if search engines cannot crawl the site.
   - Check robots.txt for unintended disallow rules.
   - Verify XML sitemap exists, is submitted to Search Console, and is up to date.
   - Identify crawl errors (4xx, 5xx status codes).
   - Check for orphan pages (no internal links pointing to them).
   - For SPAs/JS-heavy sites: verify server-side rendering or pre-rendering is in place.
2. **Indexation audit** — Ensure crawled pages are actually being indexed.
   - Check `site:domain.com` results vs. expected page count.
   - Look for `noindex` tags applied unintentionally.
   - Identify duplicate content issues and missing canonical tags.
   - Check for thin content pages that may be filtered out.
   - Review index coverage report in Search Console for excluded pages.
3. **Page speed and Core Web Vitals** — Google uses these as ranking signals.
   - **LCP (Largest Contentful Paint)**: target under 2.5 seconds. Common fixes: optimize hero images, implement lazy loading, use CDN, reduce server response time.
   - **INP (Interaction to Next Paint)**: target under 200ms. Common fixes: reduce JavaScript execution time, break up long tasks, optimize event handlers.
   - **CLS (Cumulative Layout Shift)**: target under 0.1. Common fixes: set explicit dimensions on images/embeds, avoid injecting content above existing content, use font-display: swap.
   - Check for render-blocking CSS/JS, unoptimized images, excessive third-party scripts.
4. **On-page SEO audit** — Review individual page optimization.
   - Title tags: unique, under 60 characters, primary keyword near the front.
   - Meta descriptions: compelling, under 155 characters, include a call to action.
   - Heading structure: single H1 per page, logical H2/H3 hierarchy, keywords in headings naturally.
   - URL structure: short, descriptive, hyphenated, no parameters when possible.
   - Internal linking: key pages should have multiple internal links, use descriptive anchor text.
   - Image optimization: descriptive alt text, compressed file sizes, modern formats (WebP/AVIF).
5. **Authority and E-E-A-T signals** — Experience, Expertise, Authoritativeness, Trustworthiness.
   - Author bios on content pages with credentials.
   - About page with company information and team.
   - Clear contact information and physical address (if applicable).
   - Links to authoritative sources within content.
   - Backlink profile review: quality over quantity, relevance of linking domains.
   - HTTPS everywhere, privacy policy, terms of service present.
6. **Schema markup** — Implement structured data for rich results.
   - Organization schema on the homepage.
   - Article/BlogPosting schema on content pages.
   - Product schema on product pages.
   - FAQ schema where applicable (boosts SERP real estate).
   - BreadcrumbList schema for navigation clarity.
   - Review/Rating schema if applicable (with legitimate reviews).
7. **Prioritize and recommend** — Rank all findings by impact and effort.

## Output Format
A prioritized audit report with three sections:
- **Critical issues** (blocking indexation or causing major ranking loss): fix immediately.
- **High-impact improvements** (will meaningfully improve rankings): fix within 2 weeks.
- **Optimizations** (incremental gains): fix within 30 days.

Each item includes: the issue, why it matters, how to fix it, and estimated effort (low/medium/high).

## Frameworks & Best Practices
- **Crawl budget matters at scale**: For sites with fewer than 10,000 pages, crawl budget is rarely an issue. For larger sites, prioritize crawl efficiency by removing low-value pages from the index and fixing redirect chains.
- **Canonical tags are not suggestions**: While Google treats canonicals as hints, properly implemented canonicals are followed in the vast majority of cases. Always self-canonical pages and canonical duplicates to the preferred version.
- **JavaScript SEO**: If the site relies on client-side rendering, critical content must be in the initial HTML response or rendered server-side. Google can render JS but with delays and limitations.
- **Mobile-first indexing**: Google indexes the mobile version of the site. Ensure mobile and desktop content parity. Test with mobile-friendly tools.
- **Redirect chains**: Keep redirects to a single hop. Chains of 3+ redirects waste crawl budget and dilute link equity. Audit and flatten redirect chains regularly.
- **Hreflang for international**: If the site serves multiple languages or regions, implement hreflang tags correctly. Errors here are extremely common and cause indexation issues.
- **Log file analysis**: For advanced audits, server log files reveal what Googlebot is actually crawling vs. what you want it to crawl. This is the ground truth of crawlability.
- **Site speed is a tiebreaker**: Speed alone rarely causes dramatic ranking changes, but it absolutely affects user behavior metrics (bounce rate, time on site) which indirectly impact rankings.

## Related Skills
- `content-strategy` — when the audit reveals content gaps or thin content that needs to be addressed with a broader content plan
- `landing-page` — when key landing pages need both CRO and on-page SEO optimization

## Examples

**Example 1: Full audit**
> "We launched our site 6 months ago and we're barely showing up in Google. Can you audit our SEO?"

Good output: A structured audit following the 7-step workflow. Identifies that robots.txt is blocking the /blog/ directory, sitemap is missing, several pages have duplicate title tags, Core Web Vitals are failing on mobile (LCP at 4.2s due to unoptimized hero image), and no schema markup is implemented. Prioritized fix list with 4 critical items, 6 high-impact items, and 8 optimizations.

**Example 2: Specific issue**
> "Our blog posts were ranking well but traffic dropped 40% last month. What happened?"

Good output: Diagnostic checklist starting with Search Console data review (manual actions, crawl errors, index coverage changes), then checking for algorithm update timing, content cannibalization between similar posts, lost backlinks, and technical regressions (accidental noindex, broken canonical tags, speed degradation). Recommends specific data to gather and steps to isolate the cause.
