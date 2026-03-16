---
name: privacy-policy
description: When the user needs to draft, review, or update a privacy policy for their product, or needs to understand data privacy obligations across jurisdictions.
related: [terms-of-service, soc2-prep]
reads: [startup-context]
---

# Privacy Policy

## When to Use
Activate when a founder needs to create a privacy policy for a new product launch, update an existing policy for new data practices or features, expand into a new jurisdiction (EU, California, etc.), or assess whether current data handling is properly disclosed. Also activate when the user asks about GDPR, CCPA, CPRA, or general data privacy compliance.

## Context Required
- **From startup-context:** product type, platform (web/mobile/API), target customer segments, geographic markets, business model, tech stack.
- **From the user:** product name and URL, company legal name and address, contact email for privacy inquiries, what personal data is collected and how, which third-party services process data (analytics, payment processors, CRMs, AI providers), applicable jurisdictions, whether the product targets minors, and any existing privacy documentation.

## Workflow
1. **Research the product** -- Visit the product website or review the product description. Identify all data collection methods, third-party integrations, and primary features that involve personal data.
2. **Map data collection** -- Categorize all data into: directly provided (forms, account creation), automatically collected (cookies, device info, usage data, IP addresses), third-party sources, and special/sensitive categories. Build a structured data inventory.
3. **Identify applicable laws** -- Based on where users are located and where the company operates, determine which privacy frameworks apply: GDPR, CCPA/CPRA, state privacy laws, COPPA, industry-specific regulations. Note specific obligations per jurisdiction.
4. **Structure the policy** -- Organize using the 15-section template below. Write in plain language at an 8th-grade reading level. Be specific about actual practices -- say "We collect your email address when you sign up" rather than "We may process identifiers."
5. **Flag legal review areas** -- Mark sections requiring attorney review with `[LEGAL REVIEW REQUIRED]` notation. These include legal basis determinations, international transfer mechanisms, and jurisdiction-specific rights.
6. **Provide implementation context** -- Explain why each section matters, what company decisions are needed, and what compliance considerations apply. Include a pre-publication checklist.
7. **Generate compliance summary** -- Produce a separate document with data inventory table, jurisdiction applicability matrix, risk flags, and implementation checklist.

## Output Format
Three-part deliverable:

### Part 1: Quick Reference Summary
Product details, data types collected, applicable jurisdictions, user rights summary, retention overview, and contact information.

### Part 2: Full Policy Document (15 sections)
1. **Preamble** -- Who you are, what this policy covers, effective date, contact methods.
2. **Information We Collect** -- Categories: personal info, usage data, device information, location, payment info, communications, sensitive data.
3. **How We Collect Information** -- Methods: direct entry, automatic tracking, third parties.
4. **How We Use Information** -- Purposes: service provision, support, improvements, analytics, marketing, security, legal compliance.
5. **Legal Basis for Processing** -- Consent, contract performance, legal obligation, vital interests, legitimate interests (GDPR-focused).
6. **Data Sharing and Third Parties** -- Service providers, partners, legal authorities, with specifics on who and why.
7. **International Data Transfer** -- Cross-border transfer mechanisms (SCCs, adequacy decisions), storage locations.
8. **Data Retention** -- Specific timeframes for account data, logs, deleted content.
9. **User Rights** -- Access, deletion, correction, restrict processing, portability, opt-out, complaint procedures -- organized by jurisdiction.
10. **Cookies and Tracking** -- Tools used, purposes, management options, consent requirements.
11. **Security** -- Encryption, access controls, audits, incident response, limitations.
12. **Children's Privacy** -- Parental consent, age gates, COPPA/UK Children's Code compliance.
13. **Contact and Rights Requests** -- Privacy email, address, response timeframes, DPO info.
14. **Policy Changes** -- Notice period, notification methods, user opt-out options.
15. **Additional Provisions** -- Data sale disclosure, third-party link disclaimers, governing law, effective date.

### Part 3: Compliance Notes
- Sections flagged for legal review with rationale
- Jurisdiction-specific considerations
- Pre-publication checklist (see below)
- Recommended modifications by product type

## Frameworks & Best Practices

### GDPR Core Requirements
- Lawful basis required for each processing activity (Art. 6).
- Data Protection Impact Assessment for high-risk processing (Art. 35).
- 72-hour breach notification to supervisory authority (Art. 33).
- Data Processing Agreements with all processors (Art. 28).
- Right to erasure with defined exceptions (Art. 17).
- Privacy by design and by default (Art. 25).

### CCPA/CPRA Core Requirements
- "Do Not Sell or Share My Personal Information" link required if applicable.
- Right to know, delete, correct, and opt out of sale/sharing.
- 12-month lookback for data collection disclosures.
- Sensitive personal information: right to limit use (CPRA addition).
- Service provider vs. contractor vs. third party distinctions matter.

### Plain Language Principles
- Write at an 8th-grade reading level with short sentences.
- Use concrete examples instead of abstract categories.
- Avoid "may" when you mean "do." Be specific about actual practices.
- The policy must match what your product actually does -- no over-disclosure and no under-disclosure.

### Pre-Publication Checklist
- [ ] Attorney review completed
- [ ] Policy matches actual data practices
- [ ] User privacy request processes are accessible and functional
- [ ] Technical security measures implemented
- [ ] Data Processing Agreements in place with all third parties
- [ ] Legal basis documented for each processing activity
- [ ] Cookie consent mechanism implemented (EU users)
- [ ] User notification system for material policy changes

### Common Startup Pitfalls
- Copying another company's privacy policy (their data practices are not yours).
- Missing analytics and advertising SDKs in disclosures (Google Analytics, Mixpanel, Facebook Pixel all collect personal data).
- No mechanism to actually fulfill deletion requests in the codebase.
- Assuming B2B means no privacy obligations (you still process individual user data).
- Listing data categories you do not actually collect (over-disclosure invites scrutiny).

## Related Skills
- `terms-of-service` -- Draft alongside the privacy policy; they should cross-reference each other and use consistent definitions.
- `soc2-prep` -- SOC 2 Trust Service Criteria for Privacy directly overlaps with privacy policy commitments.
- `security-review` -- Security measures described in the privacy policy must reflect actual technical controls.

## Examples

### Example 1: New SaaS product launching in US and EU
**User:** "We're launching our project management SaaS next month with users from the US and Europe. We use Stripe, Mixpanel, and AWS."

**Good output:** A three-part deliverable. The data inventory table mapping each data category to collection method, purpose, legal basis, third parties, and retention. Jurisdiction analysis identifying GDPR applicability and CCPA threshold monitoring. Red flags for Mixpanel IP collection needing disclosure and DPA, and missing cookie consent mechanism for EU users.

### Example 2: Updating policy after adding AI features
**User:** "We added an AI assistant that processes customer messages. Do we need to update our privacy policy?"

**Good output:** Identifies the new data processing (message content processed by AI models), new third party (AI provider as sub-processor), new legal basis analysis needed, and GDPR Art. 22 consideration for automated decision-making. Provides the specific policy sections that need updating with draft language.

---

**Disclaimer:** This skill generates draft privacy policies and compliance guidance for educational and planning purposes only. It does not constitute legal advice. Always have a qualified attorney licensed in your relevant jurisdictions review the final privacy policy before publication. Regulatory non-compliance can result in significant fines (up to 4% of global annual revenue under GDPR).
