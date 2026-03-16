---
name: roadmap-planning
description: When the user needs to organize product initiatives into a prioritized, time-sequenced plan with outcomes and dependencies.
related: [prd-writing, mvp-scoping]
reads: [startup-context]
---

# Roadmap Planning

## When to Use
Activate when a founder or PM has a set of product ideas, feature requests, or strategic bets and needs to organize them into a coherent roadmap. This includes situations like "help me plan our Q2 roadmap," "prioritize this feature backlog," "what should we build next," or "create a roadmap for the next 6 months." Also activate when an existing roadmap needs restructuring from output-focused (feature lists) to outcome-focused (customer and business impact).

## Context Required
- **From startup-context:** company stage, team size and composition, current product state, business model, key metrics, strategic goals, company OKRs.
- **From the user:** current roadmap or list of candidate initiatives, known customer needs, resource constraints, hard deadlines, strategy documents or company objectives for alignment, and any committed work already in progress.

## Workflow
1. **Gather the current state** -- Collect the existing roadmap or feature list. If the user provides strategy documents or company objectives, review them to understand how the roadmap should align with broader goals.
2. **Transform outputs to outcomes** -- For each initiative, ask: What customer problem are we solving? What business metric will improve? Is there a better way to achieve the same outcome? Rewrite each item as an outcome statement.
3. **Apply outcome statement format** -- Use: "Enable [customer segment] to [desired customer outcome] so that [business impact]." Every roadmap item must pass this test.
4. **Score and prioritize** -- Apply RICE scoring (Reach, Impact, Confidence, Effort) to rank initiatives. Adjust for strategic alignment with company objectives and OKRs.
5. **Identify dependencies and sequencing** -- Map which initiatives depend on others. Note technical, data, design, and business dependencies.
6. **Sequence into time horizons** -- Place initiatives into Now (0-6 weeks), Next (6-12 weeks), and Later (12+ weeks). Use flexible release windows (quarters, not specific dates) for Later items.
7. **Validate capacity** -- Cross-check the plan against team capacity. A roadmap that requires 3x your engineering bandwidth is a wishlist, not a plan.
8. **Add strategic context** -- Document how outcomes align with company strategy, key assumptions about customer needs, and review cadence.

## Output Format

### Strategic Context
One paragraph restating the company's current strategic priorities and how this roadmap serves them. Include key assumptions about customer needs.

### Outcome-Focused Roadmap

#### Now (0-6 weeks) -- Committed
| Initiative | Outcome Statement | Key Metric | Owner | Dependencies |
|---|---|---|---|---|
| Original feature/project | Enable [segment] to [outcome] so that [impact] | Metric + target | Team | List |

#### Next (6-12 weeks) -- High Confidence
Same table format. Items here are planned but may shift based on learnings from Now.

#### Later (12+ weeks) -- Exploratory
Same table format. Items here are directional. Flexible time windows, no owners assigned yet.

### Not Doing (and Why)
Initiatives explicitly excluded with reasoning. This section is as important as the roadmap itself.

### Dependency Map
Visual or textual representation of which initiatives block or enable others.

### Capacity Check
Summary of estimated effort vs. available capacity per time horizon.

### Key Assumptions and Risks
Numbered list of what must be true for this roadmap to succeed.

## Frameworks & Best Practices
- **Outcomes over outputs.** "Build advanced search filters" is an output. "Enable customers to find products 50% faster through intuitive discovery" is an outcome. Output-focused roadmaps create false precision and misalign teams around features rather than results.
- **The outcome statement format.** "Enable [customer segment] to [desired customer outcome] so that [business impact]." This forces clarity on who benefits, what changes, and why it matters.
- **The "So What?" test.** If you cannot articulate the outcome a feature drives, keep asking "So what?" until you reach real customer or business value. Multiple outputs may achieve one outcome -- focus on the outcome.
- **RICE scoring.**
  - **Reach:** How many users/accounts will this affect per quarter?
  - **Impact:** On a scale of 0.25 (minimal) to 3 (massive), how much will this move the target metric?
  - **Confidence:** As a percentage, how sure are you about reach and impact estimates?
  - **Effort:** Person-weeks required.
  - **Score:** (Reach x Impact x Confidence) / Effort.
- **Three-horizon structure.** Now/Next/Later avoids the false precision of Gantt charts. Commit to Now, plan for Next, explore Later.
- **Outcome roadmaps are resilient to change.** Because they describe the "why" rather than the "what," they survive strategy pivots and new information better than feature roadmaps.
- **Say no explicitly.** A roadmap is defined as much by what it excludes. Maintain a "Not Doing" list and share the reasoning.
- **Align with OKRs.** Every outcome statement should map to a company or product OKR. Orphan initiatives signal misalignment.
- **Revisit quarterly.** Roadmaps older than one quarter are stale. Build in review cadences.
- **Stage-appropriate planning.**
  - **Pre-PMF:** Roadmaps should be 4-6 week sprints focused on learning. No 12-month plans.
  - **Post-PMF:** Quarterly roadmaps tied to OKRs. Balance growth features with infrastructure and debt.
  - **Scaling:** Semi-annual roadmaps with cross-team coordination. Dependencies become the hard problem.
- **Avoid roadmap theater.** Do not create elaborate roadmaps to appease stakeholders if the team lacks the capacity or conviction to execute.

## Related Skills
- `prd-writing` -- Once an initiative is committed in the Now horizon, write a PRD to spec it out.
- `mvp-scoping` -- Before placing an initiative on the roadmap, scope its MVP to get a realistic effort estimate.
- `user-research-synthesis` -- Use customer insights to validate which outcomes matter most to your target segments.

## Examples

### Example 1: Output-to-outcome transformation
**User:** "Our Q2 plan says: build advanced search filters, implement AI recommendations, redesign dashboard. Help me turn this into an outcome roadmap."

**Good output excerpt:**
> **Transformation:**
> - Output: "Build advanced search filters" --> Outcome: "Enable customers to find products 50% faster through intuitive discovery"
> - Output: "Implement AI recommendations" --> Outcome: "Increase average order value by 20% through personalized discovery"
> - Output: "Redesign dashboard" --> Outcome: "Help operators monitor all systems with 80% reduction in dashboard load time"
>
> Each outcome is now testable, measurable, and opens the door to alternative solutions beyond the originally specified feature.

### Example 2: Feature backlog to roadmap
**User:** "Here's our feature backlog: Slack integration, SSO, reporting dashboard, mobile app, API v2, onboarding wizard. Help me build a roadmap."

**Good output excerpt:**
> **Now (0-6 weeks):**
> | Onboarding Wizard | Enable new signups to reach first value within 10 minutes so that activation rate increases from 35% to 55% | Activation rate | Growth team | None |
>
> **Not Doing This Quarter:**
> - Mobile app -- Current usage data shows <5% of sessions are mobile. Revisit when mobile demand signal is stronger. Asking "So what?" reveals no compelling customer outcome today.
