---
name: contract-review
description: When the user needs to review an existing contract, assess risk in proposed terms, or evaluate a contract before signing.
related: [terms-of-service, privacy-policy]
reads: [startup-context]
---

# Contract Review

## When to Use
Activate when a founder has received a contract to sign and wants to understand the risks before proceeding. This includes vendor agreements, customer enterprise agreements, partnership deals, investment documents, employment agreements, NDAs, IP assignment agreements, and any other binding legal document. Also activate when the user says things like "review this contract," "is this agreement fair," "what should I push back on," or "flag anything concerning."

## Context Required
- **From startup-context:** company stage, team size, business model, fundraising status, current revenue, and any existing legal counsel.
- **From the user:** the contract text (or key sections), who the counterparty is, the business relationship context (are they a customer, vendor, investor, partner), the user's negotiating leverage, and any specific concerns they have. Also helpful: whether this is a template/standard agreement or has been negotiated.

## Workflow
1. **Contract intake** — Receive the contract text. Identify the contract type, parties, effective date, and term. Create a one-paragraph summary of what the contract does.
2. **Section-by-section analysis** — Walk through each major section, summarizing what it means in plain language and flagging anything noteworthy.
3. **Risk flagging** — Apply the red/yellow/green flagging system (see below) to each clause. Assign a severity and explain why.
4. **Missing protections** — Identify standard protections that are absent from the contract but should be present given the contract type and relationship.
5. **Negotiation recommendations** — For each red and yellow flag, suggest specific alternative language or a negotiation strategy.
6. **Summary report** — Produce a structured risk assessment with prioritized action items.

## Output Format

### Contract Summary (top of report)
- **Contract type:** (e.g., SaaS vendor agreement, MSA, NDA)
- **Parties:** Company name vs. counterparty name
- **Term:** Duration, renewal mechanism
- **Total value:** Financial commitment if applicable
- **Overall risk level:** Red / Yellow / Green with one-sentence rationale

### Clause-by-Clause Analysis Table

| Section | Summary | Flag | Risk | Recommended Action |
|---|---|---|---|---|
| Liability Cap | Capped at fees paid in prior 6 months | Yellow | Low cap for potential damages | Negotiate to 12-month cap |
| IP Assignment | Broad assignment of all work product | Red | Could capture pre-existing IP | Add carve-out for pre-existing IP |

### Missing Protections Checklist
Bulleted list of protections that should be present but are not.

### Prioritized Action Items
Numbered list of what to do, in order of importance.

## Frameworks & Best Practices

### The Red/Yellow/Green Flagging System

**Red Flags — Immediate concern, do not sign without modification:**
- Unlimited liability or liability cap below a reasonable threshold
- Broad IP assignment that could capture pre-existing IP or IP unrelated to the engagement
- Non-compete clauses that are overly broad in scope, geography, or duration
- Unilateral termination rights without cure period for one party only
- Automatic renewal with no opt-out window or unreasonable notice requirements
- Indemnification obligations that are uncapped or wildly asymmetric
- Most-favored-nation clauses that constrain your pricing with other customers
- Exclusivity provisions that limit your ability to work with competitors
- Audit rights with unreasonable scope or no notice requirement
- Governing law in an unfavorable or distant jurisdiction with no negotiation

**Yellow Flags — Worth negotiating, but not necessarily deal-breakers:**
- Liability caps that are low relative to the contract value
- Warranty periods or SLA credits that are below industry standard
- Payment terms exceeding net-60
- Change-of-control provisions that allow termination on acquisition
- Broad confidentiality definitions with long or indefinite survival periods
- Assignment restrictions that prevent assignment in an acquisition scenario
- Force majeure clauses that are overly broad or favor one party
- Data handling terms that are vague about deletion, portability, or sub-processors

**Green Flags — Standard and reasonable:**
- Mutual confidentiality obligations
- Balanced termination rights with cure periods
- Liability capped at 12 months of fees paid
- Standard representations and warranties
- Clear payment terms (net-30)
- Reasonable non-solicitation (employees only, 12 months)

### Negotiation Principles
- **Symmetry first.** Any obligation imposed on one party should apply to both unless there is a clear business reason for asymmetry.
- **Cap everything.** Liability, indemnification, and damages should all have explicit caps.
- **Cure periods.** Both parties should have the opportunity to fix a breach before termination.
- **Specificity over breadth.** Narrow definitions protect both parties. "Confidential Information means everything" protects nothing.
- **Survival clarity.** Specify exactly which clauses survive termination and for how long.

## Related Skills
- `terms-of-service` — When reviewing a customer's redlines to your terms of service, use contract-review to assess their proposed modifications.
- `privacy-policy` — Data processing addendums and DPAs often accompany contracts. Review these for consistency with your privacy commitments.

## Examples

### Example 1: Reviewing a vendor SaaS agreement
**User:** "We're about to sign a contract with a data enrichment vendor. Here are the terms. Can you flag anything concerning?"

**Good output excerpt:**
> **Overall Risk Level: Yellow**
>
> The agreement is mostly standard but has three issues worth negotiating before signing.
>
> | Section | Flag | Issue |
> |---|---|---|
> | 4.2 Data Rights | Red | Vendor claims a "perpetual, irrevocable license to use Customer Data for product improvement and benchmarking." This means they keep and use your data forever, even after termination. **Negotiate to:** license limited to providing the service, terminates on contract end, anonymization required for any aggregate use. |
> | 7.1 Liability | Yellow | Cap is set at "fees paid in the prior 3 months." For a $2K/month contract, that is a $6K cap. If they cause a data breach affecting your customers, your exposure could be much higher. **Negotiate to:** 12 months of fees, with a carve-out for uncapped liability on data breaches and IP infringement. |
> | 9.3 Termination | Yellow | 90-day notice required to cancel, even on annual renewal. Combined with auto-renewal, this means you need to decide 3 months before your renewal date. **Negotiate to:** 30-day notice, or set a calendar reminder now. |
>
> **Missing Protections:**
> - No data deletion timeline after termination
> - No breach notification obligation
> - No sub-processor list or approval rights
> - No SLA or uptime commitment

### Example 2: Reviewing an IP assignment in an employment agreement
**User:** "A new engineer's offer letter has an IP assignment clause. They're concerned about their open-source side projects. Can you review?"

**Good output excerpt:**
> **Section 8 — Invention Assignment: Red Flag**
>
> The current language reads: *"Employee assigns to the Company all right, title, and interest in any invention, improvement, or work of authorship created during the term of employment."*
>
> This is overly broad. It captures the engineer's weekend open-source contributions, personal projects, and anything they create during employment regardless of whether it relates to company business.
>
> **Recommended revision:**
> Add a carve-out: *"...created during the term of employment that (a) relates to the Company's current or reasonably anticipated business, (b) was developed using Company resources, or (c) resulted from work performed for the Company."*
>
> Also add a Schedule A listing the engineer's pre-existing IP and active side projects, explicitly excluded from assignment. Note: California Labor Code Section 2870 already provides some protection, but an explicit carve-out is clearer and avoids disputes.

---

**Disclaimer:** This skill provides contract analysis for educational and planning purposes only. It does not constitute legal advice. Contract interpretation depends on jurisdiction-specific law, the full context of the business relationship, and facts that may not be apparent from the document alone. Always have a qualified attorney review contracts before signing, especially those involving significant financial commitments, IP rights, or liability exposure.
