---
name: startup-context
description: When the user wants to create or update their startup context document. Also use when the user mentions "set up context", "tell you about my startup", or any other skill needs context that doesn't exist yet.
related: []
reads: []
---

# Startup Context

This is the foundation skill. Every other skill reads this context first to produce tailored, specific output instead of generic advice.

## When to Use

- First time a user runs any skill and no context file exists
- When the user says "let me tell you about my startup" or similar
- When any skill detects missing context and needs to gather it

## Workflow

1. **Check for existing context** — look for `.agents/startup-context.md` in the project root
2. **If missing, interview the founder** — ask the questions below, one section at a time
3. **Generate the context file** — write structured markdown to `.agents/startup-context.md`
4. **Keep it updated** — when the user shares new info that changes context, update the file

## Context Document Structure

```markdown
# Startup Context

## Company
- **Name:**
- **One-liner:** (what you do in one sentence)
- **Stage:** (idea / pre-seed / seed / series A / series B / growth)
- **Founded:** (date)
- **Location:** (city/remote)
- **Legal entity:** (Delaware C-Corp, LLC, etc.)

## Product
- **What it does:** (2-3 sentences)
- **Category:** (e.g., developer tools, fintech, healthtech)
- **Platform:** (web app, mobile, API, desktop, hardware)
- **Tech stack:** (languages, frameworks, infra)
- **Current state:** (idea, prototype, beta, launched, scaling)

## Market
- **Target customer:** (who buys / who uses — be specific)
- **ICP:** (ideal customer profile — industry, size, role, pain)
- **TAM/SAM/SOM:** (if known)
- **Competitors:** (top 3-5, how you differ)
- **Positioning:** (why you vs alternatives)

## Business Model
- **Revenue model:** (SaaS, usage-based, marketplace, etc.)
- **Pricing:** (current pricing or planned)
- **Current MRR/ARR:** (if applicable)
- **Key metrics:** (the 3-5 numbers you track most)

## Team
- **Founders:** (names, roles, backgrounds)
- **Team size:**
- **Key hires needed:**
- **Advisors/board:**

## Fundraising
- **Total raised:**
- **Last round:** (amount, date, lead investor)
- **Current runway:** (months)
- **Next raise:** (target amount, timeline, what it's for)

## Goals
- **Next 3 months:**
- **Next 12 months:**
- **Biggest challenge right now:**
```

## Interview Questions

If no context exists, ask these in order (group related questions, don't ask all at once):

**Round 1 — The basics:**
- What does your startup do? Who is it for?
- What stage are you at? (idea through scaling)
- What's your business model?

**Round 2 — Market & traction:**
- Who's your ideal customer? Be as specific as you can.
- Who are your main competitors? What's different about you?
- What traction do you have? (users, revenue, waitlist, LOIs)

**Round 3 — Team & resources:**
- Who's on the team? What are their backgrounds?
- How much have you raised? What's your runway?
- What are you trying to accomplish in the next 3 months?

## Output

Write the completed context to `.agents/startup-context.md` and confirm with the user.

## Notes

- Keep this document factual, not aspirational — other skills need accurate context
- Update it whenever the user shares new information (new hire, funding, pivot, etc.)
- If a field is unknown, mark it as "TBD" rather than guessing
