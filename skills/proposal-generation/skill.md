---
name: proposal-generation
trigger: When a founder needs to create a sales proposal, statement of work, pricing quote, or formal offer document. Activate when the user mentions proposal, SOW, quote, pricing document, or needs to formalize a deal after a successful sales conversation.
related: [sales-script, cold-outreach]
reads: [startup-context]
---

# Proposal Generation

## When to Use
Activate when a founder needs to produce a formal sales proposal, statement of work (SOW), pricing quote, or service agreement. Also use when the user says "I need to send them a proposal," "write me an SOW," "help me put together a quote," or "how do I formalize this deal."

## Context Required
From `startup-context` or the user:
- **Prospect details** — Company name, contact, industry, size
- **Problem and needs** — What was discussed in discovery/demo, confirmed pain points
- **Proposed solution** — What you will deliver, scope, and timeline
- **Pricing** — Your pricing model, proposed price, any discounts or custom terms
- **Stakeholders** — Decision makers, champions, and blockers
- **Competitive situation** — Who else they are evaluating, if known
- **Timeline** — Their desired start date and decision timeline

## Workflow
1. **Gather requirements** — Read startup-context if available. Ask for prospect details, deal context, and scope.
2. **Define scope** — Clarify exactly what is included and, critically, what is not included. Ambiguous scope is the top source of post-sale conflict.
3. **Structure the proposal** — Choose the appropriate format (full proposal, SOW, or pricing quote) based on deal size and complexity.
4. **Draft the executive summary** — Write a compelling 1-page summary that mirrors the prospect's language from discovery and connects their problem to your solution and expected outcomes.
5. **Detail the solution** — Map each component of your solution to a specific need the prospect expressed.
6. **Build the pricing section** — Present pricing clearly with options when appropriate. Include what is included in each tier.
7. **Finalize with terms and next steps** — Add validity period, payment terms, and a clear path to signing.

## Output Format
Deliver a complete proposal document with these sections:
1. **Cover page** — Prospect company, your company, date, prepared-by
2. **Executive summary** — 1 page maximum
3. **Understanding of needs** — Their situation and challenges in their words
4. **Proposed solution** — What you will deliver, mapped to their needs
5. **Implementation plan** — Timeline, milestones, responsibilities
6. **Pricing and investment** — Clear breakdown with options if applicable
7. **Terms and conditions** — Validity, payment terms, assumptions
8. **Next steps** — Specific actions with dates
9. **Appendix** — Case studies, team bios, technical details (optional)

## Frameworks & Best Practices

### The Mirror-Then-Lead Principle
The first half of a proposal should make the prospect feel deeply understood. Mirror back their exact language, their specific pain points, and their stated goals. Only after they feel heard do you present your solution. Proposals that lead with the vendor's capabilities instead of the buyer's needs get ignored.

### Executive Summary Framework
The executive summary is the most important page. Many decision makers read only this section. Structure it as:
1. **Their challenge** (2-3 sentences) — Restate the problem using their words from discovery
2. **The cost of inaction** (1-2 sentences) — What happens if they do nothing
3. **Your approach** (2-3 sentences) — How you will solve it, at a high level
4. **Expected outcomes** (2-3 bullet points) — Specific, measurable results they can expect
5. **Investment overview** (1 sentence) — Total cost and timeline summary

### Scope Definition Best Practices
- **Be explicit about exclusions.** "This proposal does not include X" prevents scope creep and disputes.
- **Use a deliverables table.** Each deliverable gets a row: description, acceptance criteria, delivery date.
- **Distinguish phases.** Break large projects into phases with clear milestones and go/no-go decision points.
- **Define assumptions.** List what must be true for the timeline and price to hold (e.g., "Client provides API access within 5 business days of kickoff").

| Section | Include | Exclude |
|---------|---------|---------|
| Deliverables | Specific items with acceptance criteria | Vague promises like "ongoing support" |
| Timeline | Dates or durations per milestone | Open-ended timelines |
| Responsibilities | Who does what on each side | Assumptions that one side does everything |
| Assumptions | Conditions the proposal depends on | Hidden dependencies |

### Pricing Presentation Strategies

**The Three-Option Framework:**
Present three tiers to anchor the prospect and make the middle option feel like the natural choice.

| | Starter | Recommended | Premium |
|---|---------|-------------|---------|
| **What is included** | Core features | Core + integrations | Everything + custom |
| **Best for** | Teams getting started | Most teams | Enterprise needs |
| **Price** | $X/mo | $Y/mo | $Z/mo |

**Pricing principles:**
- Lead with value, not cost. Frame pricing after the solution and expected outcomes.
- Show ROI math. "This investment of $X will save/generate $Y, paying for itself in Z months."
- Do not bury the price. Prospects lose trust when they have to hunt for it.
- If offering a discount, anchor it. Show the standard price, then the discount with a reason (annual commitment, pilot pricing, early adopter).
- Include what happens at renewal. Surprises at renewal kill retention.

### Proposal Length Guidelines

| Deal Size | Proposal Length | Format |
|-----------|----------------|--------|
| Under $10K | 2-3 pages | Pricing quote or short proposal |
| $10K-$50K | 5-7 pages | Standard proposal |
| $50K-$250K | 8-12 pages | Detailed proposal with appendix |
| $250K+ | 12-20 pages | Full proposal with SOW and appendix |

### SOW-Specific Guidance
A Statement of Work is more operational than a proposal. It focuses on execution, not persuasion. Key sections:
- **Project overview** — Brief summary of the engagement
- **Scope of work** — Detailed deliverables with acceptance criteria
- **Timeline and milestones** — Gantt-style or table with dates
- **Roles and responsibilities** — RACI matrix for each workstream
- **Change management** — How to handle scope changes and the approval process
- **Payment schedule** — Tied to milestones, not just dates

### Founder-Specific Advantages in Proposals
- You can commit to personal involvement — "I will personally lead your onboarding"
- You can offer product roadmap influence — "Your feedback will directly shape our Q3 roadmap"
- You can make pricing decisions in real time without lengthy approval chains
- Reference your founding story — why you built this product connects emotionally in a way a generic vendor proposal does not

### Common Proposal Mistakes
- **Too generic** — If the prospect's name could be swapped out without changing the content, it is not customized enough
- **Feature-focused instead of outcome-focused** — Talk about what changes for them, not what your product does
- **No urgency or validity period** — Always include "This proposal is valid until [date]"
- **Missing next steps** — Every proposal needs a clear "here is how to move forward" section with specific actions
- **Scope ambiguity** — "We will provide support" means something different to every reader. Define it.
- **Sending without a walkthrough** — Always offer to walk the prospect through the proposal live. Do not just email it and hope.

## Related Skills
- `sales-script` — use for the conversations that precede the proposal (discovery, demo, negotiation)
- `cold-outreach` — use to generate the initial conversations that lead to proposal-stage deals

## Examples

**Example prompt:** "I need to send a proposal to Acme Corp for our data pipeline product. They need to migrate from their legacy ETL system. Budget is around $80K/year. Main contact is their VP of Data."

**Good executive summary output:**
> ## Executive Summary
>
> Acme Corp's data team currently spends an estimated 20+ hours per week maintaining legacy ETL pipelines that break during peak load and lack visibility into failure points. This operational burden slows down the analytics team's ability to deliver insights and puts quarterly reporting timelines at risk.
>
> We propose replacing Acme's legacy ETL infrastructure with [Product], providing a managed data pipeline platform that eliminates manual maintenance, offers real-time monitoring, and scales automatically with data volume. Based on our work with similar data teams, we expect Acme to:
>
> - **Reduce pipeline maintenance time by 75%**, freeing ~15 hours/week for the data team
> - **Eliminate unplanned pipeline failures** with proactive monitoring and auto-recovery
> - **Cut quarterly reporting preparation from 2 weeks to 2 days**
>
> The total annual investment is $78,000, with an estimated payback period of 4 months based on engineering time savings alone. Implementation takes 6 weeks, with the first pipelines live in production by week 3.
