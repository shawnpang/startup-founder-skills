---
name: pitch-deck
description: When the user wants to create, review, or restructure a fundraising pitch deck for seed or Series A. Also activates when the user mentions "deck", "pitch", "investor presentation", or "slide structure".
related: [investor-research, data-room, fundraising-email]
reads: [startup-context]
---

# Pitch Deck

## When to Use

- The founder is preparing a pitch deck for a fundraising round (pre-seed through Series A).
- The founder has an existing deck and wants structural or narrative feedback.
- The founder asks what slides to include or how to tell their story to investors.

## Context Required

From `startup-context`: company one-liner, stage, product description, target customer, business model, traction metrics, team bios, fundraising history, and competitive landscape. If any of these are missing, prompt the founder before drafting slides.

From the user: target round size, target investor type (VC vs. angel), whether this is for a live pitch (fewer words, more visuals) or a send-ahead deck (more self-explanatory text).

## Workflow

1. **Read startup context** — Pull from `.agents/startup-context.md` to populate slide content. Flag any gaps.
2. **Determine deck type** — Ask if this is a live-pitch deck (visual-heavy, 30-40 words per slide max) or a send-ahead deck (can include more explanatory text, 60-80 words per slide).
3. **Draft the narrative arc** — Before writing any slides, outline the story: what is the world like today (problem), what changes with your product (solution), why now, why this team, and what you need to get there.
4. **Write slide-by-slide content** — Produce content for each of the 10-12 slides below. Each slide gets a title, key message, supporting points, and a suggested visual or data element.
5. **Review for investor lens** — Check every slide against the question an investor would ask at that point. Flag weak spots.
6. **Produce final output** — Deliver the deck outline as structured markdown. If the user wants a `.pptx`, chain to the Anthropic pptx skill after content is finalized.

## Output Format

Structured markdown with one H3 per slide. Each slide section contains:
- **Title**: The slide headline (concise, assertion-style, e.g., "Healthcare billing wastes $200B annually")
- **Key message**: The one thing the audience should remember from this slide
- **Content**: Bullet points or narrative text
- **Visual suggestion**: What chart, image, screenshot, or diagram belongs here
- **Investor question this answers**: The implicit question in the VC's mind

## Frameworks & Best Practices

### The 10-12 Slide Framework

| # | Slide | Purpose | Common Mistakes |
|---|-------|---------|-----------------|
| 1 | **Title / Hook** | Company name, one-liner, and a memorable hook stat or image | Burying the one-liner; using a generic tagline |
| 2 | **Problem** | Make the pain visceral and specific to your ICP | Being too abstract; citing a problem everyone already knows |
| 3 | **Solution** | Show what you built and how it eliminates the pain | Feature-dumping; not connecting back to the problem |
| 4 | **Demo / Product** | Screenshot, GIF, or live product walkthrough | Showing the admin panel instead of the user-facing magic |
| 5 | **Market Size** | TAM/SAM/SOM with a credible bottoms-up calculation | Using only top-down "the market is $X trillion" numbers |
| 6 | **Business Model** | How you make money, unit economics, pricing | Not showing actual or projected unit economics |
| 7 | **Traction** | The chart that goes up and to the right | Vanity metrics; hiding the Y-axis; mixing timeframes |
| 8 | **Competition** | Why you win — positioning matrix or comparison table | Claiming "no competitors"; using a 2x2 where you magically own the top-right |
| 9 | **Team** | Founders + key hires, relevant backgrounds | Listing every employee; not explaining founder-market fit |
| 10 | **Go-to-Market** | How you acquire customers today and at scale | Saying "we'll go viral" without a concrete channel strategy |
| 11 | **Financials / Ask** | How much you're raising, use of funds, key projections | Not specifying what milestones the money unlocks |
| 12 | **Closing / Vision** | The big dream — where this goes in 5-10 years | Being too conservative; forgetting contact info |

### Narrative Arc Rules

- **Slide 1-3**: Establish tension. The audience should feel the problem before you show the answer.
- **Slide 4-7**: Build credibility. Prove you have a real product with real traction in a real market.
- **Slide 8-10**: Prove defensibility. Show you can win against alternatives and scale.
- **Slide 11-12**: Make the ask and paint the vision. End with ambition, not logistics.

### Stage-Specific Guidance

- **Pre-seed / Seed**: Emphasize problem depth, founder-market fit, and early signals (waitlist, LOIs, design partners). Financial projections can be lighter.
- **Series A**: Emphasize repeatable go-to-market, unit economics, and a clear path from current traction to 3-5x growth. Investors expect real revenue data.

### Principles

- Every slide title should be an assertion, not a label. "We grew 30% MoM for 6 months" beats "Traction".
- Remove any slide that does not advance the narrative. If you cannot articulate why a slide exists, cut it.
- The deck should be understandable by a partner who reads it at 11pm on their iPad without you presenting.
- Use no more than 3 fonts and 2 brand colors. Clutter kills credibility.
- Data beats adjectives. Replace "fast-growing" with "3x YoY".

## Related Skills

- `investor-research` — use before building the deck to tailor the narrative to specific investor interests
- `data-room` — prepare the backup materials investors will request after seeing the deck
- `fundraising-email` — write the outreach email that accompanies the deck

## Examples

**Example prompt**: "Help me build a seed deck. We're raising $3M for an AI-powered contract review tool for mid-market legal teams. We have $40K MRR and 12 paying customers."

**Good output snippet** (Problem slide):

> ### Slide 2: Problem
> **Title**: Mid-market legal teams review 500+ contracts/month with 1990s tools
> **Key message**: Contract review is the #1 time sink for legal teams at companies with 200-2,000 employees, costing $180K+/year in paralegal hours per company.
> **Content**:
> - 73% of mid-market companies still use manual redlining in Word
> - Average contract review takes 45 minutes; 30 minutes is repetitive clause checking
> - Errors in reviewed contracts cost companies 2-5% of deal value annually
> **Visual suggestion**: Side-by-side showing a paralegal buried in Word docs vs. your product highlighting risks in seconds
> **Investor question this answers**: Is this a real, painful, expensive problem?

**Example prompt**: "Review my existing deck — I keep getting passed on after the first meeting."

**Good output approach**: Read the deck, identify which of the 12 slides are missing or weak, check if the narrative arc has tension, and test every slide against the investor-question framework. Deliver specific rewrites, not vague advice.
