---
name: process-docs
trigger: When the user needs to create SOPs, playbooks, runbooks, or other operational documentation that defines how a recurring process should be executed.
related: [support-docs, board-update]
reads: [startup-context]
---

# Process Documentation

## When to Use
Activate when a founder or operator needs to document an internal process so it can be executed consistently by anyone on the team. This includes prompts like "write an SOP for X," "create a runbook for incident response," "document our onboarding playbook," "how do we standardize this process," or any request to turn tribal knowledge into a repeatable procedure.

## Context Required
- **From startup-context:** company stage, team size, current tools and systems, organizational structure, compliance requirements.
- **From the user:** the process to document, who owns and executes it, current pain points or failure modes, frequency of execution, tools involved, and whether this replaces an existing (undocumented) process or is net-new.

## Workflow
1. **Identify document type** — Determine whether this is an operational SOP (routine procedure), an incident runbook (reactive response), or an onboarding playbook (sequential learning path). Each uses a different template.
2. **Map the process end-to-end** — Walk through every step from trigger event to completion. Identify inputs, outputs, decision points, handoffs, and escalation paths.
3. **Define ownership and RACI** — Assign a single owner (Responsible), identify who Approves, who is Consulted, and who is Informed for each major step.
4. **Draft the document** — Write using the appropriate template below. Use imperative voice ("Open the dashboard," not "The dashboard should be opened").
5. **Add decision trees** — For any step with conditional logic, create explicit if/then branches. Never leave ambiguity at a fork.
6. **Include failure modes** — Document what to do when each step fails. A process doc without error handling is incomplete.
7. **Set review cadence** — Specify when this document should be reviewed and by whom (e.g., quarterly by the process owner).

## Output Format
A structured markdown document following one of the three templates below. Every process doc includes a metadata header, and the body is written so that someone with no prior context can execute the process end-to-end.

### Template 1: Operational SOP
```
# [Process Name] — Standard Operating Procedure
**Owner:** [Name / Role]
**Last Updated:** [Date]
**Review Cadence:** [Quarterly / Monthly]
**Version:** [1.0]

## Purpose
Why this process exists and what business outcome it supports.

## Scope
What this SOP covers and explicitly does not cover.

## Prerequisites
Tools, access, permissions, or context needed before starting.

## Procedure
1. Step with specific action
   - Sub-step with detail
   - **Decision point:** If [condition], go to Step X. Otherwise continue.
2. Next step...

## Escalation Path
| Condition | Escalate To | SLA |
|-----------|------------|-----|
| [Trigger] | [Person/Role] | [Timeframe] |

## Success Criteria
How to verify the process was completed correctly.

## Changelog
| Date | Author | Change |
|------|--------|--------|
```

### Template 2: Incident Runbook
```
# [Incident Type] — Runbook
**Severity:** [P0-P3]
**On-Call Owner:** [Role]
**Last Tested:** [Date]

## Detection
How this incident is identified (alerts, customer reports, monitoring).

## Immediate Actions (First 5 Minutes)
1. Triage step...
2. Communication step...

## Diagnosis
Decision tree for identifying root cause.

## Resolution Steps
Step-by-step fix for each known root cause.

## Post-Incident
Checklist for after the incident is resolved.
```

### Template 3: Onboarding Playbook
```
# [Role/Process] — Onboarding Playbook
**Duration:** [e.g., 2 weeks]
**Buddy/Owner:** [Role]

## Day 1-2: Orientation
Tasks, access setup, key introductions.

## Day 3-5: Core Training
Hands-on exercises, shadowing, tool walkthroughs.

## Week 2: Guided Practice
Supervised execution of real tasks with checkpoints.

## Graduation Criteria
What the person must demonstrate to be considered onboarded.
```

## Frameworks & Best Practices
- **The "bus factor" test.** If the person who usually runs this process is unavailable, can someone else execute it from this document alone? If not, add more detail.
- **Imperative voice only.** Every step starts with a verb. "Click the Deploy button" not "The Deploy button should be clicked."
- **One action per step.** If a step contains "and," split it into two steps. Compound steps get skipped or half-done.
- **Decision points are explicit.** Use if/then language with clear conditions. "If the customer is on an Enterprise plan, skip to Step 7" not "Handle enterprise customers differently."
- **Time estimates matter.** Include expected duration for each major phase. This helps people plan and signals when something has gone wrong (step taking 3x longer than expected = escalate).
- **Screenshots decay fast.** Prefer text descriptions of UI paths (Settings > Integrations > Slack) over screenshots, which break every redesign. Use screenshots only for genuinely complex interfaces.
- **Version and date everything.** A process doc without a last-updated date is assumed to be wrong.
- **Progressive detail.** Lead each section with a one-line summary, then expand. Experienced operators scan; new hires read every word. Serve both.
- **Link, don't duplicate.** If another SOP covers a sub-process, link to it rather than copying steps inline. Duplication causes drift.
- **Test with a newcomer.** The best review is having someone unfamiliar with the process follow the doc and noting where they get stuck.

## Related Skills
- `support-docs` — Chain when the process being documented is customer-facing and needs a corresponding help center article or troubleshooting guide.
- `board-update` — Chain when operational processes need to be summarized for investor or board reporting (e.g., "here is our incident response maturity").

## Examples

### Example 1: Operational SOP
**User:** "Write an SOP for processing customer refunds."

**Good output excerpt:**
> ## Procedure
> 1. **Open the refund request** in Zendesk. Verify the ticket includes: order ID, reason for refund, and customer email.
> 2. **Check eligibility** in Stripe.
>    - **Decision point:** If the order is older than 30 days, escalate to the Support Lead with a note explaining the customer's situation. Do not process the refund.
>    - If within 30 days, continue to Step 3.
> 3. **Issue the refund** via Stripe Dashboard > Payments > [Order ID] > Refund. Select "Full refund" unless partial was approved by the Support Lead.
> 4. **Update the ticket** with the Stripe refund ID and set status to "Solved."
> 5. **Log the refund** in the Refund Tracker spreadsheet (column A: date, B: order ID, C: amount, D: reason code).
>
> **Estimated time:** 5-8 minutes per refund.

### Example 2: Incident Runbook
**User:** "We need a runbook for when our payment processing goes down."

**Good output excerpt:**
> ## Immediate Actions (First 5 Minutes)
> 1. **Acknowledge the alert** in PagerDuty to stop re-escalation.
> 2. **Check Stripe Status Page** (status.stripe.com). If Stripe reports an outage, skip to "External Provider Outage" section.
> 3. **Post in #incidents Slack channel:** "Investigating payment processing failures. Updates every 15 min. DRI: [your name]."
> 4. **Enable the maintenance banner** via Admin > Feature Flags > `payment_maintenance_mode` = true. This shows users "Payments temporarily unavailable, please retry shortly" instead of raw errors.
