---
name: privacy-policy
trigger: When the user needs to draft, review, or update a privacy policy for their product, or needs to understand data privacy obligations across jurisdictions.
related: [terms-of-service, soc2-prep]
reads: [startup-context]
---

# Privacy Policy

## When to Use
Activate when a founder needs to create a privacy policy for a new product launch, update an existing policy to cover new data practices, expand into a new jurisdiction (EU, California, etc.), or assess whether their current data handling is properly disclosed. Also activate when the user asks about GDPR, CCPA, CPRA, or general data privacy compliance.

## Context Required
- **From startup-context:** product type, platform (web/mobile/API), target customer segments, geographic markets, business model, tech stack.
- **From the user:** what personal data is collected, how it is used, what third-party services process data (analytics, payment processors, CRMs), whether the product targets minors, whether data is sold or shared for advertising, and any existing privacy documentation.

## Workflow
1. **Data mapping** — Identify all categories of personal data collected, the purpose for each, the legal basis for processing, retention periods, and all third parties who receive the data. Produce a structured data inventory table.
2. **Jurisdiction analysis** — Based on where users are located and where the company operates, determine which privacy frameworks apply (GDPR, CCPA/CPRA, PIPEDA, LGPD, etc.). Flag specific obligations per jurisdiction.
3. **Gap assessment** — Compare current data practices against legal requirements. Identify missing disclosures, absent consent mechanisms, or data processing without a valid legal basis.
4. **Policy drafting** — Write the privacy policy using plain language, organized by the section template below. Avoid legalese where possible while remaining legally precise.
5. **Implementation checklist** — Produce a concrete list of technical and operational steps needed to comply (cookie banners, opt-out mechanisms, data deletion workflows, DPA agreements with vendors).
6. **Compliance flagging** — Highlight areas of elevated risk in red/yellow format. Red = likely non-compliant and needs immediate action. Yellow = ambiguous or depends on interpretation, recommend legal review.

## Output Format
A privacy policy document with the following sections, plus a separate compliance summary.

### Policy Sections
1. **Introduction** — Who you are, what this policy covers, effective date.
2. **Data We Collect** — Categories of personal data, organized by collection method (directly provided, automatically collected, third-party sources).
3. **How We Use Your Data** — Purposes of processing, mapped to legal bases (consent, contract performance, legitimate interest).
4. **How We Share Your Data** — Categories of third-party recipients, purpose of sharing, whether data is sold (CCPA definition).
5. **Data Retention** — How long each category is retained and why.
6. **Your Rights** — Rights by jurisdiction (access, deletion, portability, opt-out of sale, correction, restriction of processing).
7. **Cookies & Tracking** — What tracking technologies are used, purposes, and how to manage preferences.
8. **International Transfers** — Whether data crosses borders, transfer mechanisms (SCCs, adequacy decisions).
9. **Children's Privacy** — COPPA/age-gating disclosures if applicable.
10. **Security Measures** — High-level description of safeguards (encryption, access controls).
11. **Changes to This Policy** — How users will be notified of updates.
12. **Contact Information** — Data controller identity, DPO contact if applicable, supervisory authority.

### Compliance Summary (separate document)
- Data inventory table
- Jurisdiction applicability matrix
- Red/yellow flag list with recommended actions
- Implementation checklist with priority ordering

## Frameworks & Best Practices

### GDPR Core Requirements
- Lawful basis required for each processing activity (Art. 6).
- Data Protection Impact Assessment for high-risk processing (Art. 35).
- 72-hour breach notification to supervisory authority (Art. 33).
- Data Processing Agreements with all processors (Art. 28).
- Right to erasure ("right to be forgotten") with defined exceptions (Art. 17).
- Privacy by design and by default (Art. 25).

### CCPA/CPRA Core Requirements
- "Do Not Sell or Share My Personal Information" link required if applicable.
- Right to know, delete, correct, and opt out of sale/sharing.
- 12-month lookback for data collection disclosures.
- Sensitive personal information: right to limit use and disclosure (CPRA addition).
- Service provider vs. contractor vs. third party distinctions matter for data sharing.

### Plain Language Principles
- Write at an 8th-grade reading level. Use short sentences.
- Define technical terms on first use.
- Use concrete examples: "We collect your email address when you sign up" rather than "We may process identifiers."
- Organize with clear headings and bullet points.
- Avoid "may" when you mean "do." Be specific about actual practices.

### Common Startup Pitfalls
- Copying another company's privacy policy (their data practices are not yours).
- Listing data collection categories you do not actually perform (over-disclosure invites scrutiny).
- Missing analytics and advertising SDKs in your disclosures (Google Analytics, Mixpanel, Facebook Pixel all collect personal data).
- No mechanism to actually fulfill deletion requests in your codebase.
- Assuming B2B means no privacy obligations (you still process individual user data).

## Related Skills
- `terms-of-service` — Draft alongside the privacy policy; they should cross-reference each other and use consistent definitions.
- `soc2-prep` — SOC 2 Trust Service Criteria for Privacy directly overlaps with privacy policy commitments. Align both.
- `security-review` — Security measures described in the privacy policy must reflect actual technical controls.

## Examples

### Example 1: New SaaS product launching in US and EU
**User:** "We're launching our project management SaaS next month. We have users signing up from the US and Europe. We use Stripe for payments, Mixpanel for analytics, and AWS for hosting. Need a privacy policy."

**Good output excerpt:**
> **Data Inventory:**
>
> | Data Category | Collection Method | Purpose | Legal Basis (GDPR) | Third Parties | Retention |
> |---|---|---|---|---|---|
> | Email, name | Registration form | Account creation | Contract performance | None | Account lifetime + 30 days |
> | Payment card (tokenized) | Checkout flow | Payment processing | Contract performance | Stripe | Per Stripe retention policy |
> | Usage events, IP address | Automatic collection | Product analytics | Legitimate interest | Mixpanel | 12 months |
>
> **Jurisdiction Analysis:**
> - GDPR applies: you have EU users. You need a lawful basis for each processing activity, a mechanism for cross-border transfer (AWS US regions), and a DPA with Stripe and Mixpanel.
> - CCPA applies if you meet thresholds (annual revenue >$25M, or >100K consumers, or >50% revenue from selling data). Monitor as you scale.
>
> **Red Flags:**
> - Mixpanel collects IP addresses and device identifiers. You need this disclosed and a DPA in place.
> - No cookie consent mechanism described. EU users require opt-in consent for analytics cookies.

### Example 2: Updating policy after adding AI features
**User:** "We just added an AI assistant to our product that processes customer messages to generate responses. Do we need to update our privacy policy?"

**Good output excerpt:**
> **Yes, update required.** AI processing of customer messages introduces new data processing that must be disclosed. Key additions needed:
> - New data category: message content processed by AI models.
> - New purpose: automated response generation.
> - New third party: if using OpenAI/Anthropic API, disclose the AI provider as a sub-processor.
> - New legal basis analysis: legitimate interest or consent depending on how integral the AI feature is.
> - GDPR Art. 22 consideration: if the AI makes decisions with legal or significant effects, users have the right not to be subject to solely automated decision-making.

---

**Disclaimer:** This skill generates draft privacy policies and compliance guidance for educational and planning purposes only. It does not constitute legal advice. Privacy law is jurisdiction-specific and evolving rapidly. Always have a qualified attorney licensed in your relevant jurisdictions review your final privacy policy before publication. Regulatory non-compliance can result in significant fines (up to 4% of global annual revenue under GDPR).
