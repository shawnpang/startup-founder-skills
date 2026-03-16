---
name: mvp-scoping
description: When the user needs to decide what to build, cut, and defer for a first release or minimum viable version of a product or feature.
related: [prd-writing, roadmap-planning]
reads: [startup-context]
---

# MVP Scoping

## When to Use
Activate when a founder or PM has an idea or a full feature spec and needs to distill it down to the smallest version worth building. Trigger phrases include "what's our MVP," "what should we cut," "scope this down," "what do we build first," "we only have 4 weeks," or "help me prioritize what to include." Also activate when a team is struggling with scope creep and needs to draw a clear line between must-have and nice-to-have.

## Context Required
- **From startup-context:** company stage, team size, runway/timeline pressure, existing product (if any), technical stack and constraints.
- **From the user:** the full feature vision or spec, target user segment, the core hypothesis being tested, available timeline and resources, any non-negotiable requirements (compliance, security, contractual commitments).

## Workflow
1. **State the hypothesis** — Define what the MVP is designed to learn or prove. Format: "We believe that [user segment] will [behavior] if we provide [capability], and we'll know we're right when [measurable signal]."
2. **List all candidate features** — Enumerate every feature, capability, and requirement from the full vision.
3. **Apply MoSCoW prioritization** — Classify every item as Must Have, Should Have, Could Have, or Won't Have (this time).
4. **Identify risks** — For each Must Have, identify technical, market, and execution risks. Flag any Must Have that carries high risk and may need a spike or prototype first.
5. **Define the cut line** — Draw a clear boundary. Everything above the line ships in v1. Everything below has a specific trigger for when it gets built.
6. **Estimate and validate** — Rough-size the Must Haves. If they exceed the available timeline by more than 20%, force-rank the Must Haves and demote the lowest.
7. **Write the MVP spec** — Produce a concise scope document with explicit inclusions, exclusions, and deferred items.

## Output Format

### Hypothesis Statement
One sentence stating what the MVP will test and how success is measured.

### MoSCoW Classification

#### Must Have (v1 — ships or the product fails)
| Feature | Rationale | Risk Level | Effort Estimate |
|---|---|---|---|
| Feature name | Why this cannot be cut | Low/Med/High | T-shirt size or days |

#### Should Have (v1.1 — ships within 2-4 weeks after launch)
Same table format. These improve the product meaningfully but are not required for the core hypothesis test.

#### Could Have (v1.2+ — ships if data supports it)
Same table format. These are enhancements contingent on v1 learnings.

#### Won't Have (not this product/quarter)
List with brief reasoning for each exclusion.

### Risk Register
| Risk | Category | Likelihood | Impact | Mitigation |
|---|---|---|---|---|
| Description | Technical/Market/Execution | High/Med/Low | High/Med/Low | Action to reduce risk |

### MVP Scope Summary
Concise paragraph describing what v1 does, who it's for, and what it explicitly does not do.

### Success Criteria
Specific metrics and thresholds that determine whether the MVP validated the hypothesis.

## Frameworks & Best Practices
- **MoSCoW prioritization.**
  - **Must Have:** Without this, the product does not work or the hypothesis cannot be tested. Apply ruthlessly. If more than 40% of features are Must Have, your bar is too low.
  - **Should Have:** Important but the product can launch without it. Users will notice the gap but can work around it.
  - **Could Have:** Nice-to-have. Include only if time permits with zero impact on Must Haves.
  - **Won't Have:** Explicitly out of scope this cycle. Naming these prevents scope creep.
- **The "cupcake, not a layer of cake" principle.** An MVP is a complete, small experience — not an incomplete large one. A cupcake is a whole dessert. A cake layer with no frosting is an unfinished project.
- **Optimize for learning speed.** The MVP's job is to test a hypothesis as fast as possible. Every feature should either be required for the test or removed.
- **Manual before automated.** If a process can be done manually for the first 50 users, do not build automation for it in the MVP. Concierge MVPs and Wizard-of-Oz MVPs are valid.
- **One user segment.** MVPs that try to serve multiple segments serve none well. Pick the segment with the strongest pain and the shortest sales cycle.
- **Hard conversation forcing function.** If the team cannot agree on Must Haves, ask: "If we could only build 3 features, which 3 would we pick?" Start from zero and add, rather than starting from everything and cutting.
- **Deferred is not deleted.** Maintain a deferred backlog with explicit triggers: "Build feature X when metric Y reaches threshold Z." This reassures stakeholders that their requests are heard.
- **Risk-first sequencing.** Build the riskiest Must Have first. If it fails, you learn early and cheaply. If it works, everything else is lower risk.
- **Scope creep signals.** Watch for: "while we're at it," "it would be easy to also," "users will expect," and "competitors have." Each phrase requires the response: "Does this change our hypothesis?"

## Related Skills
- `prd-writing` — After scoping the MVP, write a PRD for the Must Have set.
- `roadmap-planning` — Place Should Have and Could Have items into the roadmap's Next and Later horizons.
- `user-research-synthesis` — Use customer insights to validate which features are truly Must Have vs. assumed Must Have.

## Examples

### Example 1: Scoping a new product MVP
**User:** "We're building a tool that helps freelancers send invoices, track time, manage expenses, handle taxes, and send contracts. We have 6 weeks and 2 engineers."

**Good output excerpt:**
> **Hypothesis:** We believe freelancers earning $50K-$150K/year will send at least 3 invoices in their first month if we provide a simple invoice builder with payment tracking, and we'll know we're right when 40% of signups reach this threshold.
>
> **Must Have:** Invoice creation, payment status tracking, email delivery.
> **Should Have:** Time tracking (linked to invoices), recurring invoices.
> **Won't Have (this cycle):** Expense management, tax calculations, contract management.
>
> **Rationale for cuts:** Time tracking and expenses are adjacent workflows but not required to test the core invoicing hypothesis. Tax and contracts are separate products masquerading as features.

### Example 2: Scoping down an existing feature
**User:** "Our PRD for the analytics dashboard has 15 chart types, custom date ranges, export to PDF/CSV, scheduled reports, and real-time data. Engineering says it's 3 months. We need it in 6 weeks."

**Good output should** classify the 15 chart types into 4-5 Must Have charts that cover 80% of use cases, defer scheduled reports and real-time data, keep CSV export but cut PDF, and identify that custom date ranges are Must Have because every user interview mentioned them.
