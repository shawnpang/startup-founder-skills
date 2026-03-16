---
name: proposal-generation
description: When a founder needs to create a sales proposal, statement of work, contract, NDA, or master service agreement. Activate when the user mentions proposal, SOW, quote, contract, NDA, MSA, or needs to formalize a deal.
related: [sales-script, cold-outreach]
reads: [startup-context]
---

# Proposal Generation

## When to Use
- Starting a new client engagement and need a contract or proposal fast
- Client asks for a proposal with pricing and timeline
- Partnership or vendor relationship requiring an MSA
- Protecting IP or confidential information with an NDA
- Need a Statement of Work with a deliverables matrix
- EU/DACH project requiring GDPR-compliant data clauses

## Context Required
From `startup-context` or the user:
- **Document type** — Contract, proposal, SOW, NDA (mutual/one-way), or MSA
- **Jurisdiction** — US (Delaware), EU (GDPR), UK (post-Brexit), or DACH (German law)
- **Engagement type** — Fixed-price, hourly, or retainer
- **Parties** — Names, roles, business addresses
- **Scope summary** — 1-3 sentences describing the engagement
- **Financial terms** — Total value, hourly rate, or retainer amount
- **Timeline** — Start date, end date or duration, milestone dates
- **Special requirements** — IP assignment, white-label, subcontractors, exclusivity

## Workflow
1. **Gather requirements** — Read startup-context if available. Collect all eight inputs listed above. Flag any missing item as REQUIRED.
2. **Select document type** — Match the engagement to the right format: fixed-price contract, consulting retainer, SaaS partnership, NDA, SOW, or full proposal.
3. **Apply jurisdiction rules** — Select clause variants based on governing law. US uses work-for-hire doctrine; EU requires explicit IP assignment deeds; DACH requires transfer of Nutzungsrechte since authors retain moral rights under BGB.
4. **Draft the document** — Fill all sections using structured Markdown with bracketed placeholders for client-specific data. Include the key clauses table below.
5. **Add GDPR addendum if needed** — For EU/DACH engagements handling personal data, attach a Data Processing Addendum per Art. 28 GDPR covering data categories, sub-processors, and cross-border transfer mechanisms.
6. **Review for common pitfalls** — Check for missing IP assignment language, vague acceptance criteria, no change order process, jurisdiction mismatches, and missing liability caps.
7. **Provide conversion instructions** — Include Pandoc commands for DOCX output with legal-style numbered sections.

## Output Format
Deliver a complete document in structured Markdown containing:
1. **Header block** — Effective date, party names, addresses
2. **Services / scope** — Detailed deliverables with acceptance criteria and dates
3. **Payment terms** — Milestone-based, net-30, or retainer schedule with late payment interest
4. **Intellectual property** — Ownership assignment, pre-existing IP licenses, portfolio rights
5. **Confidentiality** — Duration (2-5 years standard, perpetual for trade secrets)
6. **Warranties** — As-is disclaimer or limited fix warranty (30/90-day)
7. **Liability cap** — 1x contract value standard, 3x for high-risk engagements
8. **Termination** — For cause (14-day cure) and for convenience (30/60/90-day notice)
9. **Dispute resolution** — Jurisdiction-appropriate arbitration (AAA/ICC/LCIA/DIS)
10. **Signature block** — Both parties with date lines

## Frameworks & Best Practices

### Key Clauses Reference

| Clause | Options |
|--------|---------|
| Payment terms | Net-30, milestone-based, monthly retainer |
| IP ownership | Work-for-hire (US), assignment (EU/UK), Nutzungsrechte transfer (DACH) |
| Liability cap | 1x contract value (standard), 3x (high-risk) |
| Termination | For cause (14-day cure), convenience (30/60/90-day notice) |
| Confidentiality | 2-5 year term, perpetual for trade secrets |
| Dispute resolution | AAA (US), ICC (EU), LCIA (UK), DIS (DACH) |

### Jurisdiction-Specific Rules
- **US (Delaware):** Work-for-hire doctrine applies under Copyright Act 101. Arbitration via AAA Commercial Rules. Non-competes enforceable with reasonable scope/time.
- **EU (GDPR):** Must include Data Processing Addendum for any personal data. IP assignment may require separate written deed. Arbitration via ICC.
- **UK (post-Brexit):** Governed by English law. IP under Patents Act 1977 / CDPA 1988. UK GDPR applies. Arbitration via LCIA Rules.
- **DACH:** BGB governs contracts. Written form required for certain clauses (para 126 BGB). Authors retain moral rights — must explicitly transfer Nutzungsrechte. Non-competes max 2 years with compensation required (para 74 HGB). Include Schriftformklausel.

### Pricing Presentation Strategy
Present three tiers to anchor the prospect and make the middle option feel natural:

| | Starter | Recommended | Premium |
|---|---------|-------------|---------|
| Scope | Core deliverables | Core + integrations | Everything + custom work |
| Best for | Teams getting started | Most teams | Enterprise needs |
| Price | $X | $Y | $Z |

Always lead with value before cost. Show ROI math: "This investment of $X saves $Y, paying for itself in Z months."

### SOW-Specific Guidance
A Statement of Work is operational, not persuasive. Key sections:
- **Deliverables table** — Each deliverable gets a row: description, acceptance criteria, delivery date
- **RACI matrix** — Roles and responsibilities for each workstream
- **Change management** — How to handle scope changes and the approval process
- **Payment schedule** — Tied to milestones, not just calendar dates
- **Assumptions** — Conditions the timeline and price depend on

### Common Pitfalls
1. **Missing IP assignment language** — "Work for hire" alone is insufficient in EU; DACH needs explicit Nutzungsrechte transfer
2. **Vague acceptance criteria** — Always define what "accepted" means with written sign-off and rejection windows
3. **No change order process** — Scope creep kills fixed-price projects; add a clause for out-of-scope work
4. **Jurisdiction mismatch** — Choosing Delaware law for a German-only project creates enforcement problems
5. **Missing liability cap** — Without a cap, one bug could mean unlimited damages
6. **Oral amendments** — Always require written amendments signed by both parties

**Disclaimer:** Not a substitute for legal counsel. Use these as strong starting frameworks; review with an attorney for high-value or complex engagements.

## Related Skills
- `sales-script` — Use for the sales conversations that precede the proposal
- `cold-outreach` — Use to generate the initial conversations that lead to proposal-stage deals

## Examples

**Prompt:** "I need a fixed-price contract for a $45K web app project with a German client."

**Good output snippet:**
```
# SOFTWARE DEVELOPMENT AGREEMENT

Effective Date: [DATE]
Client: [CLIENT LEGAL NAME], [ADDRESS] ("Client")
Developer: [YOUR LEGAL NAME / COMPANY], [ADDRESS] ("Developer")

Governing Law: German law (BGB)
Arbitration: DIS Rules, [CITY]

## 2. PAYMENT
Total Fee: EUR 45,000

| Milestone | Amount | Due |
|-----------|--------|-----|
| Contract signing | 50% (EUR 22,500) | Upon execution |
| Beta delivery | 25% (EUR 11,250) | [DATE] |
| Final acceptance | 25% (EUR 11,250) | Within 5 days of acceptance |

## 3. INTELLECTUAL PROPERTY
Upon receipt of full payment, Developer assigns all Nutzungsrechte
(usage rights) in the Work Product to Client. Developer retains moral
rights per German copyright law (UrhG).
```
