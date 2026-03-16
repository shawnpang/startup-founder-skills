---
name: prd-writing
trigger: When the user needs to define a product feature, write a product requirements document, or translate an idea into a structured spec.
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
1. **Clarify scope level** — Ask whether this needs a lightweight PRD (early-stage exploration, 2-3 pages) or a full PRD (committed initiative, 5-8 pages). Default to lightweight if the company is pre-product-market-fit.
2. **Gather inputs** — Collect the problem statement, target users, any existing research, success criteria, and known constraints.
3. **Draft the 8-section PRD** — Write each section sequentially using the template below.
4. **Validate assumptions** — Flag any sections where data is missing and recommend how to fill gaps (user interviews, analytics, competitive research).
5. **Review and refine** — Present the draft, invite feedback, and iterate on specific sections.

## Output Format
A structured PRD document with the following 8 sections:

### Section Template
1. **Summary** — One-paragraph elevator pitch. What is being built and why it matters.
2. **Background** — Context on the problem space, prior attempts, and what changed to make this the right time.
3. **Objective** — Clear statement of goals using the format: "Enable [user segment] to [action] resulting in [measurable outcome]."
4. **Market Segments** — Who this is for. Primary and secondary segments with size estimates and characteristics.
5. **Value Propositions** — What specific value each segment gets. Map value props to segments explicitly.
6. **Solution** — Feature description, user flows, key interactions, wireframe-level detail. Include what is explicitly out of scope.
7. **Release Strategy** — Phased rollout plan. Alpha/beta/GA stages, feature flags, rollback criteria.
8. **Success Metrics** — Primary KPI, secondary metrics, leading indicators. Include targets and measurement timeline.

For lightweight PRDs, sections 2, 6, and 7 can be condensed to 2-3 sentences each.

## Frameworks & Best Practices
- **Problem before solution.** Spend 40% of the document on sections 1-5 (the "why") before touching section 6 (the "what"). A PRD that jumps to the solution is a spec, not a PRD.
- **One objective, not five.** A PRD with multiple objectives is multiple PRDs. Split them. Each PRD should have a single primary metric it moves.
- **Scope creep guard.** Explicitly list what is NOT in scope. This section is as important as what is in scope. Revisit the out-of-scope list when stakeholders propose additions.
- **Measurable success.** Every metric must have a target number and a date. "Improve retention" is not a metric; "Increase D7 retention from 25% to 35% within 8 weeks of launch" is.
- **Audience awareness.** Engineers need technical constraints and edge cases. Designers need user flows and personas. Executives need the summary and metrics. Write for all three audiences in a single document.
- **Living document.** State the PRD version and last-updated date. PRDs that never change were never read. Update after every significant scope decision.
- **Lightweight PRD triggers:** pre-PMF exploration, hackathon projects, internal tools, experiments with <2 week timelines.
- **Full PRD triggers:** cross-team initiatives, features with external dependencies, anything touching payments or compliance.
- **Edge cases belong in the PRD.** Enumerate at least 5 edge cases in the Solution section. What happens when the user has no data? What if they lose connectivity mid-flow? What about permissions for shared resources?
- **Competitor context in Background.** Always mention how competitors handle the same problem (or fail to). This grounds the "why now" and validates the opportunity.
- **Assumption tracking.** List the top 3 assumptions underlying the PRD. For each, state what evidence supports it and what would invalidate it. Link to user research if available.

## Related Skills
- `roadmap-planning` — Chain after writing PRDs to slot the initiative into the broader roadmap with dependencies and timelines.
- `mvp-scoping` — Chain before writing a PRD to determine what to include in v1 vs. defer to later releases.
- `user-research-synthesis` — Chain before writing a PRD to ground the Background and Market Segments sections in real customer data.

## Examples

### Example 1: Lightweight PRD prompt
**User:** "We need a PRD for adding Slack notifications to our project management tool."

**Good output excerpt:**
> **Summary:** Add configurable Slack notifications so that teams using ProjectFlow are alerted to task updates, mentions, and deadline changes without leaving their primary communication tool. This addresses the #1 feature request from our Q3 customer survey (38% of respondents).
>
> **Objective:** Enable team leads on paid plans to receive real-time project updates in Slack, resulting in a 20% reduction in average response time to task assignments within 6 weeks of launch.
>
> **Out of scope:** Microsoft Teams integration, custom notification templates, Slack bot commands.

### Example 2: Full PRD prompt
**User:** "Write a full PRD for our new self-serve onboarding flow. We're losing 60% of signups before they complete setup."

**Good output excerpt:**
> **Background:** Current onboarding requires 7 steps and takes an average of 12 minutes. Hotjar recordings show 45% of users abandon at the "connect data source" step. Competitor X reduced their onboarding to 3 steps in Q2 and reported a 2x improvement in activation. Our support team handles 30+ onboarding tickets per week, costing approximately $4,500/month.
>
> **Release Strategy:**
> - Week 1-2: Internal dogfood with the team
> - Week 3: 10% of new signups (with feature flag)
> - Week 4: 50% rollout if activation rate > 45%
> - Week 5: GA if no P0 bugs and support ticket volume decreases
> - Rollback trigger: activation rate drops below current 40% baseline
>
> **Success Metrics:**
> - Primary: Increase onboarding completion rate from 40% to 65% within 6 weeks of GA
> - Secondary: Reduce median time-to-first-value from 12 minutes to under 5 minutes
> - Leading indicator: Decrease onboarding-related support tickets by 50%
