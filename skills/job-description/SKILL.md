---
name: job-description
description: When the user needs to write, review, or improve a job posting for a startup role.
related: [interview-kit, sourcing-outreach, employer-brand]
reads: [startup-context]
---

# Job Description

## When to Use
Activate when the user asks to create a new job posting, rewrite an existing one, or get feedback on a draft JD. Also activate when the user is preparing to hire for a new role and needs to define it clearly before sourcing candidates.

## Context Required
- **From startup-context:** Company name, mission statement, stage/funding, tech stack (for eng roles), team size, remote/hybrid/onsite policy, benefits, and equity structure.
- **From user:** Role title, reporting structure, seniority level, key responsibilities, must-have vs. nice-to-have qualifications, compensation range (or willingness to include one), and hiring timeline.

## Workflow
1. **Clarify the role** — Ask the user what problem this hire solves. A JD should start from business need, not a generic title. Confirm level, scope, and team placement.
2. **Draft the hook** — Write a 2-3 sentence opening that connects the company mission to why this role matters right now. Avoid generic openers like "We are looking for a rockstar..."
3. **Structure the body** — Organize into five sections: Mission & Impact, What You'll Do (6-8 bullets), What You Bring (5-7 bullets split into must-have and nice-to-have), What We Offer, and How to Apply.
4. **Apply anti-pattern checks** — Scan the draft for corporate jargon, unrealistic requirement stacking, gendered language, and exclusionary phrasing. Flag and fix.
5. **Add startup-specific framing** — Emphasize ownership, speed of impact, equity upside, learning velocity, and access to leadership. These are startup advantages over big-co offers.
6. **Review comp and inclusivity** — Ensure compensation transparency (range or "we'll share in first conversation"). Confirm language passes inclusive-language guidelines.
7. **Final polish** — Tighten to a scannable length (400-700 words). Ensure the tone matches the company voice from startup-context.

## Output Format
A complete, ready-to-post job description in markdown with the following sections:
- Title and location/remote line
- Opening hook (2-3 sentences)
- About Us (3-4 sentences)
- What You'll Do (bulleted list)
- What You Bring (must-haves and nice-to-haves, clearly separated)
- What We Offer (bulleted list)
- How to Apply (1-2 sentences with clear next step)

## Frameworks & Best Practices

### The HERO Structure
- **Hook:** Why this role matters to the mission right now
- **Expectations:** What the person will actually do day-to-day
- **Requirements:** What they genuinely need to succeed (not a wish list)
- **Offer:** What the company gives back (comp, equity, growth, culture)

### Anti-Patterns to Avoid
- **Requirement inflation:** Listing 15+ requirements signals you don't know what you need. Keep must-haves to 4-5.
- **Corporate jargon:** "Synergy," "leverage," "fast-paced environment" are empty. Use concrete language.
- **Gendered language:** Avoid "ninja," "rockstar," "aggressive." Use tools like the Gender Decoder or Textio guidelines as a reference.
- **Years-of-experience gates:** "7+ years of React" excludes strong candidates. Prefer demonstrated capability over tenure.
- **Hidden role:** If the job is actually three jobs, split it or be honest about the breadth.

### Inclusive Language Guidelines
- Use "you" instead of "the ideal candidate" to feel inviting rather than evaluative.
- Replace "requirements" with "what you bring" to reduce self-screening by underrepresented candidates.
- Include an explicit encouragement to apply even if not a 100% match (research shows this matters for women and minority applicants).
- State accommodation availability for the interview process.

### Compensation Transparency
- Include a salary range. Listings with ranges get significantly more applicants.
- If equity is offered, state the range in percentage or share count and mention the vesting schedule.
- Name benefits explicitly rather than saying "competitive benefits package."

### Startup-Specific Framing
- **Impact:** "You'll be one of the first 10 engineers shaping the product architecture."
- **Ownership:** "You'll own the entire lifecycle of features, from design through production monitoring."
- **Equity:** "We offer meaningful equity because early employees take real risk and deserve real upside."
- **Growth:** "As we scale from 10 to 50, you'll grow into a leadership role if you want it."

## Related Skills
- `interview-kit` — After posting the JD, design the interview loop and scorecards for this role.
- `sourcing-outreach` — Use the JD as the basis for personalized outreach messages to passive candidates.
- `employer-brand` — Ensure the JD tone and content align with your careers page and employer brand narrative.

## Examples

**Prompt:** "We need to hire our first product designer. We're a 12-person B2B SaaS startup, Series A, remote-first."

**Good output snippet:**
```
# Product Designer — Remote (US/Canada time zones)

Join Acme as our founding designer and shape the product experience
from the ground up. You won't be handed a pixel-perfect spec — you'll
partner directly with engineering and customers to figure out what to
build and how it should feel.

## What You'll Do
- Own the end-to-end design process for our core B2B platform
- Run discovery calls with customers weekly to ground designs in real workflows
- Build and maintain our design system as the foundation for a future team
- Collaborate async-first with engineering using Figma and Loom
...
```

**Prompt:** "Review this JD for red flags."

**Good output snippet:**
```
Issues found:
1. "Must have 10+ years in Python" — This filters out strong mid-career
   candidates. Consider "deep fluency in Python" instead.
2. "Fast-paced environment" — This is vague. Replace with something
   concrete: "We ship weekly and iterate based on customer feedback."
3. No salary range listed — Adding a range will increase your applicant
   pool significantly.
```
