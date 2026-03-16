---
name: onboarding-flow
trigger: When the user needs to design, improve, or audit a post-signup activation flow to get new users to their first value moment.
related: [support-docs, email-marketing, churn-analysis]
reads: [startup-context]
---

# Onboarding Flow

## When to Use
Activate when a founder or product lead needs to design onboarding for new users, improve activation rates, reduce time-to-value, or re-engage users who stalled during setup. This includes prompts like "design our onboarding flow," "users are dropping off after signup," "build an activation checklist," "write onboarding emails," or "how do we get users to their aha moment faster."

## Context Required
- **From startup-context:** product type (B2B/B2C/PLG), target user persona, current activation rate, defined "aha moment," product complexity level, existing onboarding steps, and current tools (email platform, analytics, in-app messaging).
- **From the user:** where users currently drop off, the key action that correlates with retention (the activation event), number of steps currently required to reach value, and any qualitative feedback from churned users about the setup experience.

## Workflow
1. **Define the activation event** — Identify the single action most correlated with long-term retention. If the user does not know this, help them hypothesize based on product type (see frameworks below).
2. **Map the current flow** — Document every step from signup to activation event, including screens, emails, and wait states. Identify friction points, unnecessary steps, and moments of confusion.
3. **Design the optimized flow** — Apply the progressive onboarding framework to restructure the journey. Minimize steps before first value. Defer non-essential setup.
4. **Build the multi-channel sequence** — Coordinate in-app guidance (checklists, tooltips, empty states) with email/push nudges. Each channel has a role; do not duplicate messages across channels.
5. **Design re-engagement triggers** — Create automated interventions for users who stall at each stage. Different stall points need different messages.
6. **Define metrics and experiments** — Set up tracking for each step in the funnel. Design A/B tests for the highest-leverage changes.

## Output Format
A complete onboarding design document including: funnel map with expected conversion at each step, in-app UX specifications, email sequence copy, re-engagement triggers, and measurement plan.

### Onboarding Funnel Template
```
Stage 1: Signup → Profile Setup     (Target: 90%+ conversion)
Stage 2: Profile Setup → First Key Action  (Target: 60-70%)
Stage 3: First Key Action → Aha Moment     (Target: 50-60%)
Stage 4: Aha Moment → Habit Formation      (Target: 30-40%)
```

## Frameworks & Best Practices

### The Progressive Onboarding Framework
Structure onboarding in three layers that unlock sequentially:

1. **Layer 1: Immediate Value (Minutes 0-5)**
   - Get the user to one small win before asking for anything.
   - Pre-fill data where possible (import, templates, sample data).
   - Use empty states as onboarding — every blank screen should guide the next action.
   - Ask only for information required to deliver that first win. Defer profile completion, preferences, and team invites.

2. **Layer 2: Core Setup (Day 1-3)**
   - Introduce a checklist with 3-5 items (never more than 7). Show progress visually.
   - Each checklist item should unlock a visible capability ("Complete this to enable X").
   - Use contextual tooltips triggered by user behavior, not a grand tour on first login.
   - Send a Day 1 email that reinforces the first win and previews the next step.

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

### Multi-Channel Coordination Rules
- **In-app:** Real-time guidance for users who are active. Checklists, tooltips, progress bars, empty state CTAs.
- **Email:** Async nudges for users who leave. Day 0 welcome, Day 1 first-win reinforcement, Day 3 re-engagement, Day 7 value recap.
- **Push/SMS:** Reserve for high-intent signals only (e.g., "Your report is ready" or "Your teammate just joined"). Never use for generic reminders.
- **Rule:** If the user completed the action in-app, suppress the corresponding email. Nothing kills trust faster than "Complete your setup!" emails sent after setup is already done.

### Email Sequence Template
| Email | Timing | Subject Line Formula | Goal |
|-------|--------|---------------------|------|
| Welcome | Signup + 0 min | "Welcome — here's your first step" | Set expectations, link to first action |
| First Win | Day 1 | "You just [achieved X] — here's what's next" | Reinforce progress, introduce next step |
| Re-engage | Day 3 (if stalled) | "[Name], pick up where you left off" | Remove the specific blocker |
| Social proof | Day 5 (if stalled) | "How [similar company] uses [product]" | Overcome hesitation with proof |
| Last chance | Day 10 (if stalled) | "Need help getting started?" | Offer human assistance (live chat, call) |

### Checklist Design Principles
- **3-5 items maximum.** Research shows completion rates drop sharply above 5 items.
- **First item should be pre-completed.** Starting with visible progress ("1 of 4 done!") increases completion rate by 30%+.
- **Each item takes under 2 minutes.** If a step takes longer, break it into sub-steps or simplify it.
- **Show the reward.** "Connect Slack → Get instant notifications" not just "Connect Slack."
- **Allow skipping with consequences.** Let users skip items but show what they lose ("You can do this later, but notifications won't work until you do").

### Re-Engagement for Stalled Users
Diagnose before prescribing. Different stall points indicate different problems:

| Stall Point | Likely Cause | Intervention |
|-------------|-------------|--------------|
| Signed up, never returned | Unclear value prop or bad timing | Email with a specific use case matching their signup context |
| Started setup, abandoned | Too many steps or hit a blocker | Email linking directly to where they stopped, with help resources |
| Completed setup, never used | No compelling reason to come back | Trigger-based email when something relevant happens in their account |
| Used once, never returned | First experience was not valuable | Ask what they were trying to accomplish; offer guided setup call |

## Related Skills
- `support-docs` — Chain to create help center articles and getting-started guides that support the onboarding flow.
- `email-marketing` — Chain to build the full lifecycle email program beyond onboarding (retention, expansion, win-back).
- `churn-analysis` — Chain when onboarding completion data reveals early churn patterns that need deeper investigation.

## Examples

### Example 1: Designing a new onboarding flow
**User:** "We're a B2B project management tool. Users sign up but only 20% create their first project. Help us fix onboarding."

**Good output excerpt:**
> **Activation Event:** Create first project + add at least one task (correlates with 60-day retention based on comparable tools).
>
> **Current Friction Analysis:**
> After signup, users land on an empty dashboard with no guidance. They must: (1) create a workspace, (2) configure settings, (3) invite team, (4) create a project. That is 4 steps before any value. The fix is to collapse steps 1-2 into auto-provisioning and defer step 3.
>
> **Redesigned Flow:**
> 1. Signup → land on a pre-built sample project (not an empty dashboard)
> 2. Guided prompt: "Create your first real project" with 3 templates to choose from
> 3. After project creation, prompt to add first task with an inline example
> 4. Celebration state: "Your project is live! Now invite your team to collaborate."
>
> **Expected impact:** Reducing pre-value steps from 4 to 2 should increase project creation rate from 20% to 45-55%.

### Example 2: Re-engagement campaign
**User:** "We have 3,000 signups from last month and 60% never completed setup. How do we bring them back?"

**Good output approach:** Segment the 60% by where they stalled. Write 3 different re-engagement emails for each stall point. Include subject lines, body copy, and CTAs that link directly to the step they abandoned. Recommend a sunset policy (stop emailing after 30 days of inactivity to protect deliverability).
