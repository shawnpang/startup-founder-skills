---
name: prd-writing
description: When the user needs to define a product feature, write a product requirements document, or translate an idea into a structured spec.
related: [roadmap-planning, mvp-scoping]
reads: [startup-context]
---

# PRD Writing

## When to Use
Activate when a founder or PM needs to turn a product idea, feature request, or strategic initiative into a structured Product Requirements Document. This includes situations where the user says things like "write a PRD," "spec out this feature," "define requirements for X," or "I need to document what we're building."

## Context Required
- **From startup-context:** company stage, target customer segments, current product state, team size, technical constraints.
- **From the user:** the feature or initiative to spec, known user problems it addresses, any prior research or customer feedback, desired timeline, and scope preference (lightweight vs. full PRD).

## Workflow
1. **Clarify scope level** -- Ask whether this needs a lightweight PRD (early-stage exploration, 2-3 pages) or a full PRD (committed initiative, 5-8 pages). Default to lightweight if the company is pre-product-market-fit.
2. **Gather inputs** -- Collect the problem statement, target users, any existing research, success criteria, and known constraints. Identify key contacts and their roles.
3. **Draft the 8-section PRD** -- Write each section sequentially using the template below. Use accessible language suitable for a broad audience including engineering, design, and leadership.
4. **Flag assumptions** -- Explicitly list key assumptions underlying each section. For each, state what evidence supports it and what would invalidate it.
5. **Review and refine** -- Present the draft, invite feedback, and iterate on specific sections. State the PRD version and last-updated date.

## Output Format
A structured PRD document with 8 sections:

### Section Template
1. **Summary** -- 2-3 sentence overview of what is being built and why it matters. Write for a broad audience.
2. **Contacts** -- Key stakeholders with their roles and relevant context about their involvement.
3. **Background** -- Context on the problem space: why now, what changed, what enables this initiative. Include competitive context on how others handle the same problem.
4. **Objective** -- Goals, business and customer benefits, and strategic alignment. Define SMART success metrics tied to OKRs. Use the format: "Enable [user segment] to [action] resulting in [measurable outcome]."
5. **Market Segment(s)** -- Define target users by problems and needs, not demographics. Describe primary and secondary segments with size estimates.
6. **Value Proposition(s)** -- Map customer jobs addressed, gains provided, and pain points eliminated. Show competitive differentiation using frameworks like Value Curve analysis.
7. **Solution** -- Feature descriptions, UX/prototypes, wireframes, user flows, and technology details when relevant. Include out-of-scope items explicitly. Document assumptions. Enumerate at least 5 edge cases.
8. **Release** -- Phased rollout plan using relative timeframes (not exact dates). Define MVP vs. future iterations, feature flags, rollback criteria, and review checkpoints.

For lightweight PRDs, sections 2, 3, and 8 can be condensed to 2-3 sentences each.

## Frameworks & Best Practices
- **Problem before solution.** Spend 40% of the document on sections 1-5 (the "why") before touching section 7 (the "what"). A PRD that jumps to the solution is a spec, not a PRD.
- **One objective, not five.** A PRD with multiple objectives is multiple PRDs. Split them. Each PRD should have a single primary metric it moves.
- **Market segments defined by needs.** Describe who this is for based on the problems they face and jobs they hire the product to do, not by demographics or firmographics alone.
- **Value Proposition clarity.** For each segment, explicitly state the customer jobs addressed, gains provided, and pains eliminated. Use the Value Curve to show where you differentiate from competitors.
- **Data-driven specificity.** Replace vague language with specific numbers. "Improve retention" is not a metric; "Increase D7 retention from 25% to 35% within 8 weeks of launch" is.
- **Scope creep guard.** Explicitly list what is NOT in scope. Revisit the out-of-scope list when stakeholders propose additions.
- **Relative timeframes over dates.** Use phases and relative windows rather than exact calendar dates. This prevents false precision and allows flexibility.
- **Assumption tracking.** List the top 3 assumptions underlying the PRD. For each, state supporting evidence and what would invalidate it.
- **Audience awareness.** Engineers need technical constraints and edge cases. Designers need user flows and personas. Executives need the summary and metrics. Write for all three in a single document.
- **Living document.** State the PRD version and last-updated date. PRDs that never change were never read.
- **Lightweight PRD triggers:** pre-PMF exploration, hackathon projects, internal tools, experiments with <2 week timelines.
- **Full PRD triggers:** cross-team initiatives, features with external dependencies, anything touching payments or compliance.

## Related Skills
- `roadmap-planning` -- Chain after writing PRDs to slot the initiative into the broader roadmap with dependencies and timelines.
- `mvp-scoping` -- Chain before writing a PRD to determine what to include in v1 vs. defer to later releases.
- `user-research-synthesis` -- Chain before writing a PRD to ground the Background and Market Segments sections in real customer data.

## Examples

### Example 1: Lightweight PRD prompt
**User:** "We need a PRD for adding Slack notifications to our project management tool."

**Good output excerpt:**
> **Summary:** Add configurable Slack notifications so that teams using ProjectFlow are alerted to task updates, mentions, and deadline changes without leaving their primary communication tool. This addresses the #1 feature request from our Q3 customer survey (38% of respondents).
>
> **Objective:** Enable team leads on paid plans to receive real-time project updates in Slack, resulting in a 20% reduction in average response time to task assignments within 6 weeks of launch.
>
> **Market Segment:** Teams of 10+ coordinating across tools, whose primary pain is context-switching between project management and communication platforms.
>
> **Out of scope:** Microsoft Teams integration, custom notification templates, Slack bot commands.

### Example 2: Full PRD prompt
**User:** "Write a full PRD for our new self-serve onboarding flow. We're losing 60% of signups before they complete setup."

**Good output excerpt:**
> **Background:** Current onboarding requires 7 steps and takes an average of 12 minutes. Hotjar recordings show 45% of users abandon at the "connect data source" step. Competitor X reduced their onboarding to 3 steps in Q2 and reported a 2x improvement in activation. Our support team handles 30+ onboarding tickets per week, costing approximately $4,500/month.
>
> **Value Proposition:** Eliminate the "connect data source" friction by offering a sample dataset that lets users experience core value before committing to integration. Differentiated from Competitor X which still requires immediate data connection.
>
> **Release:**
> - Phase 1: Internal dogfood with the team (2 weeks)
> - Phase 2: 10% of new signups via feature flag
> - Phase 3: 50% rollout if activation rate > 45%
> - Phase 4: GA if no P0 bugs and support ticket volume decreases
> - Rollback trigger: activation rate drops below current 40% baseline
