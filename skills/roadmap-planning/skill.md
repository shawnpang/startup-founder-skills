---
name: roadmap-planning
trigger: When the user needs to organize product initiatives into a prioritized, time-sequenced plan with outcomes and dependencies.
related: [prd-writing, mvp-scoping]
reads: [startup-context]
---

# Roadmap Planning

## When to Use
Activate when a founder or PM has a set of product ideas, feature requests, or strategic bets and needs to organize them into a coherent roadmap. This includes situations like "help me plan our Q2 roadmap," "prioritize this feature backlog," "what should we build next," or "create a roadmap for the next 6 months." Also activate when an existing roadmap needs restructuring from feature-centric to outcome-centric framing.

## Context Required
- **From startup-context:** company stage, team size and composition, current product state, business model, key metrics, strategic goals.
- **From the user:** list of candidate initiatives or features, known customer needs, resource constraints, hard deadlines (launches, fundraising, compliance), and any committed work already in progress.

## Workflow
1. **Collect candidate initiatives** — Gather all features, projects, and ideas under consideration. Include source (customer request, internal, strategic bet).
2. **Reframe as outcomes** — Convert each feature-level item into an outcome statement using the format: "Enable [segment] to [outcome] so that [impact]."
3. **Score and prioritize** — Apply RICE scoring (Reach, Impact, Confidence, Effort) to rank initiatives. Adjust for strategic alignment.
4. **Identify dependencies** — Map which initiatives depend on others (technical, data, design, or business dependencies).
5. **Sequence into time horizons** — Place initiatives into Now (0-6 weeks), Next (6-12 weeks), and Later (12+ weeks) buckets. Avoid specific dates for Later items.
6. **Validate capacity** — Cross-check the plan against team capacity. A roadmap that requires 3x your engineering bandwidth is a wishlist, not a plan.
7. **Define milestones and checkpoints** — Add review points where the team reassesses priorities based on new data.

## Output Format

### Strategic Context
One paragraph restating the company's current strategic priorities and how this roadmap serves them.

### Outcome-Focused Roadmap

#### Now (0-6 weeks) — Committed
| Initiative | Outcome Statement | RICE Score | Owner | Dependencies | Success Metric |
|---|---|---|---|---|---|
| Name | Enable [segment] to [outcome] so that [impact] | Score | Team/person | List | Metric + target |

#### Next (6-12 weeks) — High Confidence
Same table format. Items here are planned but may shift based on learnings from Now.

#### Later (12+ weeks) — Exploratory
Same table format. Items here are directional. No dates, no owners assigned yet.

### Dependency Map
Visual or textual representation of which initiatives block or enable others.

### Capacity Check
Summary of estimated effort vs. available capacity per time horizon.

### Key Risks and Assumptions
Numbered list of what must be true for this roadmap to succeed.

## Frameworks & Best Practices
- **Outcomes over features.** "Build Slack integration" is a feature. "Enable distributed teams to receive real-time updates in their existing workflow, reducing response time by 30%" is an outcome. Roadmaps should use the latter.
- **The "Enable [segment] to [outcome] so that [impact]" format.** This forces clarity on who benefits, what changes for them, and why it matters to the business. Every roadmap item must pass this test.
- **RICE scoring.**
  - **Reach:** How many users/accounts will this affect per quarter?
  - **Impact:** On a scale of 0.25 (minimal) to 3 (massive), how much will this move the target metric?
  - **Confidence:** As a percentage, how sure are you about reach and impact estimates?
  - **Effort:** Person-weeks required.
  - **Score:** (Reach x Impact x Confidence) / Effort.
- **Three-horizon structure.** Now/Next/Later avoids the false precision of Gantt charts. Commit to Now, plan for Next, dream about Later.
- **Say no explicitly.** A roadmap is defined as much by what it excludes. Maintain a "Not Doing" list and share the reasoning.
- **Revisit quarterly.** Roadmaps older than one quarter are stale. Build in review cadences.
- **Avoid roadmap theater.** Do not create elaborate roadmaps to appease stakeholders if the team lacks the capacity or conviction to execute. A shorter honest roadmap beats a long aspirational one.
- **Stage-appropriate planning.**
  - **Pre-PMF:** Roadmaps should be 4-6 week sprints focused on learning. No 12-month plans.
  - **Post-PMF:** Quarterly roadmaps tied to OKRs. Balance growth features with infrastructure and debt.
  - **Scaling:** Semi-annual roadmaps with cross-team coordination. Dependencies become the hard problem.

## Related Skills
- `prd-writing` — Once an initiative is committed in the Now horizon, write a PRD to spec it out.
- `mvp-scoping` — Before placing an initiative on the roadmap, scope its MVP to get a realistic effort estimate.
- `user-research-synthesis` — Use customer insights to validate which outcomes matter most to your target segments.

## Examples

### Example 1: Feature list to outcome roadmap
**User:** "Here's our feature backlog: Slack integration, SSO, reporting dashboard, mobile app, API v2, onboarding wizard. Help me build a roadmap."

**Good output excerpt:**
> **Now (0-6 weeks):**
> | Onboarding Wizard | Enable new signups to reach first value within 10 minutes so that activation rate increases from 35% to 55% | RICE: 840 | Growth team | None | Activation rate |
>
> **Not Doing This Quarter:**
> - Mobile app — Current usage data shows <5% of sessions are mobile. Revisit when mobile demand signal is stronger.

### Example 2: Roadmap restructuring
**User:** "Our board wants to see our 2026 roadmap. Right now it's just a list of features in a spreadsheet."

**Good output should** reframe each feature as an outcome statement, group them into strategic themes, apply the three-horizon structure, and include a capacity reality check showing whether the plan is feasible with the current team.
