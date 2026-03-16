---
name: onboarding-flow
description: When the user needs to design, improve, or audit a post-signup activation flow to get new users to their first value moment. Activate when activation is lagging, time-to-value feels excessive, or first sessions lack impact.
related: [support-docs, email-marketing, churn-analysis]
reads: [startup-context]
---

# Onboarding Flow

## When to Use
Activate when a founder or product lead needs to design onboarding for new users, improve activation rates, reduce time-to-value, fix drop-off after signup, redesign a guided setup experience, or re-engage users who stalled during onboarding. This includes prompts like "design our onboarding flow," "users are dropping off after signup," "build an activation checklist," "our time-to-value is too long," "how do we get users to their aha moment faster," or "first sessions are not sticking."

Do NOT use for employee onboarding, service process design, or when the product lacks a stable value proposition. This skill is for in-product user activation only.

## Context Required
- **From startup-context:** product type (B2B/B2C/PLG), target user persona, current activation rate, defined "aha moment," product complexity level, existing onboarding steps, and current tools (email platform, analytics, in-app messaging).
- **From the user:** where users currently drop off, the key action that correlates with retention (the activation event), number of steps currently required to reach value, any qualitative feedback from churned users about the setup experience, and what "healthy" first-session behavior looks like.

## Workflow
1. **Intake and goal-framing** — Read startup-context if available. Establish the activation goal, current baseline metrics, and what success looks like. If the user does not know their activation event, help them hypothesize based on product type (see benchmarks below).
2. **Map the current journey** — Document every step from signup to activation event, including screens, emails, wait states, and decision points. Identify friction points, unnecessary steps, and moments of confusion.
3. **Identify friction and drop-off** — Pinpoint where users abandon the flow. Categorize blockers: too many steps, unclear value, technical obstacles, cognitive overload, or missing guidance.
4. **Define behavioral activation moments** — Identify the specific user actions that predict long-term retention. These become the milestones the onboarding flow drives toward.
5. **Design the first experience** — Apply the progressive onboarding framework to restructure the journey. Focus on the "first 30 seconds" experience and minimize steps before first value. Defer non-essential setup.
6. **Build the milestone-based onboarding plan** — Create a "first mile" plan with clear milestones from signup through habit formation, with coordinated in-app and email touchpoints.
7. **Establish measurement and experiments** — Set up tracking for each step in the funnel. Build an experiment backlog prioritized by impact, confidence, and effort. Design A/B tests for the highest-leverage changes.

## Output Format
A comprehensive Onboarding & Activation Pack including:
1. **Activation spec** — Defined activation event with behavioral criteria and baseline metrics
2. **First 30 seconds design** — The immediate post-signup experience optimized for first value
3. **First mile milestone plan** — Stage-by-stage plan from signup through habit formation
4. **Funnel map** — Every step with expected conversion rates
5. **In-app UX specifications** — Checklists, tooltips, empty states, progress indicators
6. **Email sequence copy** — Welcome through re-engagement with timing and triggers
7. **Experiment backlog** — Prioritized list of onboarding experiments (impact/confidence/effort)
8. **Measurement framework** — Leading indicators, tracking plan, and success criteria
9. **Risk documentation** — Open questions, assumptions, and next-step recommendations

### Onboarding Funnel Template
```
Stage 1: Signup -> Profile Setup            (Target: 90%+)
Stage 2: Profile Setup -> First Key Action  (Target: 60-70%)
Stage 3: First Key Action -> Aha Moment     (Target: 50-60%)
Stage 4: Aha Moment -> Habit Formation      (Target: 30-40%)
```

## Frameworks & Best Practices

### The Progressive Onboarding Framework
Structure onboarding in three layers that unlock sequentially:

1. **Layer 1: Immediate Value (Minutes 0-5)**
   - Get the user to one small win before asking for anything.
   - Pre-fill data where possible (import, templates, sample data).
   - Use empty states as onboarding — every blank screen should guide the next action.
   - Ask only for information required to deliver that first win. Defer everything else.

2. **Layer 2: Core Setup (Day 1-3)**
   - Introduce a checklist with 3-5 items (never more than 7). Show progress visually.
   - Each checklist item should unlock a visible capability ("Complete this to enable X").
   - Use contextual tooltips triggered by user behavior, not a grand tour on first login.
   - Send a Day 1 email reinforcing the first win and previewing the next step.

3. **Layer 3: Expansion (Week 1-2)**
   - Prompt team invites after the individual user has experienced value (not before).
   - Introduce advanced features through progressive disclosure, not feature dumps.
   - Trigger expansion prompts based on usage patterns, not arbitrary timelines.

### Activation Event Benchmarks by Product Type
| Product Type | Common Activation Event | Target Time-to-Value |
|-------------|------------------------|---------------------|
| B2B SaaS (simple) | Complete first core workflow | < 10 minutes |
| B2B SaaS (complex) | Import data + run first report | < 24 hours |
| PLG / Self-serve | Invite first team member + collaborate | < 48 hours |
| Developer tool | First successful API call or deploy | < 30 minutes |
| B2C app | Complete first session/transaction | < 3 minutes |

### Inside-the-Product Onboarding
Prioritize onboarding that happens within the product experience itself, not detached from it. Product tours that overlay the UI without context are less effective than:
- **Empty states that teach** — Every blank screen guides the next action
- **Inline prompts** — Contextual guidance that appears when the user reaches a decision point
- **Progressive disclosure** — Reveal complexity as the user demonstrates readiness
- **Sample data** — Let users experience the product's value before investing their own data

### Multi-Channel Coordination Rules
- **In-app:** Real-time guidance for active users. Checklists, tooltips, progress bars, empty state CTAs.
- **Email:** Async nudges for users who leave. Day 0 welcome, Day 1 reinforcement, Day 3 re-engagement, Day 7 value recap.
- **Push/SMS:** Reserve for high-intent signals only ("Your report is ready," "Your teammate just joined"). Never use for generic reminders.
- **Suppression rule:** If the user completed the action in-app, suppress the corresponding email. Nothing kills trust faster than "Complete your setup!" emails sent after setup is done.

### Checklist Design Principles
- **3-5 items maximum.** Completion rates drop sharply above 5.
- **First item should be pre-completed.** Starting with visible progress significantly increases completion rates (endowed progress effect).
- **Each item takes under 2 minutes.** If longer, break it into sub-steps.
- **Show the reward.** "Connect Slack -> Get instant notifications" not just "Connect Slack."
- **Allow skipping with consequences.** Let users skip but show what they lose.

### Re-Engagement for Stalled Users
Diagnose before prescribing. Different stall points indicate different problems:

| Stall Point | Likely Cause | Intervention |
|-------------|-------------|--------------|
| Signed up, never returned | Unclear value prop or bad timing | Email with specific use case matching signup context |
| Started setup, abandoned | Too many steps or hit a blocker | Email linking directly to where they stopped |
| Completed setup, never used | No compelling reason to return | Trigger-based email when something relevant happens |
| Used once, never returned | First experience was not valuable | Ask what they were trying to accomplish; offer guided call |

### Quality Guardrails
All onboarding designs should include:
- Risk documentation identifying assumptions that could be wrong
- Open questions that need user research to answer
- Explicit next steps with owners and timelines
- Leading indicators to measure before waiting for retention data

## Related Skills
- `support-docs` — Create help center articles and getting-started guides that support the onboarding flow
- `email-marketing` — Build the full lifecycle email program beyond onboarding (retention, expansion, win-back)
- `churn-analysis` — When onboarding completion data reveals early churn patterns needing deeper investigation

## Examples

### Example 1: Designing a new onboarding flow
**User:** "We're a B2B project management tool. Users sign up but only 20% create their first project. Help us fix onboarding."

**Good output excerpt:**
> **Activation Event:** Create first project + add at least one task (correlates with 60-day retention).
>
> **First 30 Seconds Design:**
> After signup, land on a pre-built sample project (not an empty dashboard). The user sees what the product looks like when populated. A single guided prompt says "Create your first real project" with 3 templates to choose from. After project creation, inline prompt to add a first task with an example. Celebration state: "Your project is live! Invite your team to collaborate."
>
> **Expected impact:** Reducing pre-value steps from 4 to 2 should increase project creation from 20% to 45-55%.

### Example 2: Activation is lagging
**User:** "We have 3,000 signups from last month and 60% never completed setup. How do we bring them back?"

**Good output approach:** Segment the 60% by where they stalled. Design different re-engagement emails for each stall point. Include subject lines, body copy, and CTAs linking directly to the abandoned step. Recommend a sunset policy (stop emailing after 30 days to protect deliverability). Build an experiment backlog testing different interventions at each stall point, prioritized by volume of stalled users and estimated recovery rate.
