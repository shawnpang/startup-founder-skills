---
name: terms-of-service
description: When the user needs to draft, review, or update terms of service for their SaaS product or web application.
related: [privacy-policy, contract-review]
reads: [startup-context]
---

# Terms of Service

## When to Use
Activate when a founder needs to create terms of service for a product launch, update existing terms to reflect new features or business model changes, or assess whether current terms adequately protect the company. Also activate when the user asks about acceptable use policies, liability limitations, or user agreement structures.

## Context Required
- **From startup-context:** product type, platform, business model, pricing structure, target customer (B2B vs B2C), geographic markets, company legal entity and jurisdiction.
- **From the user:** what the product does, how users interact with it, whether users create or upload content, whether the product integrates with third-party services, payment/subscription structure, any past disputes or known risk areas, and whether the audience includes enterprise customers who will negotiate terms.

## Workflow
1. **Scope assessment** — Determine the product type (SaaS, marketplace, API, mobile app) and audience (consumers, SMBs, enterprise). This dictates the tone, enforceability approach, and which clauses are essential.
2. **Risk identification** — Map the key liability scenarios for this specific product: data loss, service outages, user-generated content issues, integration failures, billing disputes.
3. **Draft terms** — Write each section using the template below. Use plain language with legally precise phrasing. Avoid unnecessary jargon while maintaining enforceability.
4. **Enforceability review** — Flag clauses that may be unenforceable in certain jurisdictions (e.g., blanket liability exclusions are limited in the EU, mandatory arbitration is restricted in some states and countries).
5. **Presentation guidance** — Recommend how to present the terms (clickwrap vs browsewrap), versioning strategy, and how to notify users of changes.

## Output Format
A terms of service document with the following sections.

### Section Template
1. **Agreement to Terms** — How acceptance works (clickwrap recommended), age requirements, authority to bind an organization.
2. **Description of Service** — What the product does, what it does not guarantee, service levels if applicable.
3. **Account Registration & Security** — Account creation requirements, user responsibilities for credentials, account sharing policy.
4. **Acceptable Use Policy** — Prohibited activities (abuse, scraping, reverse engineering, illegal use, competitive benchmarking). Be specific to the product.
5. **User Content & Data** — Who owns user-uploaded content, license grants the company needs to operate the service, what happens to data on termination.
6. **Data Ownership & Portability** — Clarify that customer data belongs to the customer. Describe export capabilities and formats.
7. **Intellectual Property** — Company retains ownership of the platform, trademarks, proprietary algorithms. User gets a limited license to use the service.
8. **Payment & Billing** — Subscription terms, billing cycles, price change notice periods, refund policy, what happens on failed payments.
9. **Free Trials & Freemium** — Terms specific to free tiers, conversion expectations, feature limitations, data retention after trial expiry.
10. **Service Availability & SLAs** — Uptime commitments (or lack thereof), scheduled maintenance windows, force majeure.
11. **Limitation of Liability** — Cap on damages (typically limited to fees paid in prior 12 months), exclusion of consequential/indirect damages.
12. **Indemnification** — User indemnifies company for misuse, content violations, third-party claims arising from user's use.
13. **Termination** — How either party can terminate, what happens to data post-termination (retention period, deletion timeline), survival clauses.
14. **Dispute Resolution** — Governing law, jurisdiction, arbitration clause if applicable, class action waiver if applicable.
15. **Modifications to Terms** — How changes are communicated, notice period (30 days recommended), continued use as acceptance.
16. **Miscellaneous** — Severability, entire agreement, assignment, waiver, notices.

## Frameworks & Best Practices

### Plain Language Approach
- Write so a non-lawyer customer can understand their obligations and rights.
- Use "you" and "we" consistently. Define them once at the top.
- Use short paragraphs and bullet points for lists of prohibited activities.
- Bold or highlight the most impactful clauses (liability caps, auto-renewal, arbitration).
- Provide a "key terms summary" sidebar or header for each section with a one-line plain English explanation.

### SaaS-Specific Considerations
- **Data ownership is non-negotiable.** Customer data must unambiguously belong to the customer. The company gets only the license needed to provide the service.
- **Aggregated/anonymized data.** If you use customer data in aggregate for analytics, benchmarking, or model training, disclose this explicitly and ensure it is truly de-identified.
- **API terms.** If you offer an API, specify rate limits, authentication requirements, and restrictions on redistribution of API output.
- **Integration liability.** Clarify that the company is not responsible for third-party integrations or data passed to third-party services at the user's direction.
- **Sub-processors.** List or link to sub-processors (hosting, payment, analytics). Enterprise customers expect this.

### Enforceability Guardrails
- **Clickwrap over browsewrap.** Require an affirmative action (checkbox, click) to accept terms. Browsewrap ("by using this site you agree") is weakly enforceable.
- **Conspicuous disclosure.** Arbitration clauses, auto-renewal terms, and liability limitations must be prominently displayed to be enforceable in many jurisdictions.
- **Consumer protection limits.** EU and UK consumer law restricts unfair terms. Blanket liability exclusions for negligence are generally unenforceable for consumers.
- **Auto-renewal laws.** California (ARL), FTC guidelines, and EU consumer directives require clear disclosure of auto-renewal and easy cancellation.
- **Unilateral modification.** Courts increasingly scrutinize "we can change these terms at any time" clauses. Provide reasonable notice (30 days) and allow termination if users disagree.

### B2B vs B2C Differences
- **B2B:** Expect negotiation on liability caps, SLAs, indemnification, and data processing terms. Have an enterprise-tier addendum ready.
- **B2C:** Consumer protection laws are more protective. Arbitration may be restricted. Cooling-off periods may apply.
- **Hybrid (self-serve B2B):** Start with standard terms but have a process for enterprise customers to request modifications via a Master Service Agreement.

## Related Skills
- `privacy-policy` — Must be drafted together. Terms should reference the privacy policy for data handling practices. Definitions (like "personal data") should be consistent.
- `contract-review` — When enterprise customers redline your terms, use contract-review to assess their proposed changes.

## Examples

### Example 1: B2B SaaS product
**User:** "We're launching a B2B analytics platform with a freemium tier and paid plans starting at $49/month. We need terms of service."

**Good output excerpt:**
> **6. Data Ownership & Portability**
>
> Your Data is yours. We claim no ownership over any data, content, or information you submit to the Service ("Customer Data"). You grant us a limited, non-exclusive license to use Customer Data solely to provide and improve the Service.
>
> You may export your Customer Data at any time via the dashboard export feature in CSV or JSON format. Upon termination of your account, we will retain your Customer Data for 30 days to allow retrieval, after which it will be permanently deleted from our active systems and removed from backups within 90 days.
>
> We may generate aggregated, anonymized statistics about platform usage ("Aggregated Data") that cannot identify you or any individual user. We own Aggregated Data and may use it for benchmarking, research, and product improvement.

### Example 2: Marketplace with user-generated content
**User:** "Our platform lets freelancers sell digital templates. We need terms covering both buyers and sellers."

**Good output excerpt:**
> **5. User Content**
>
> **For Sellers:** You retain ownership of all templates and digital assets you upload ("Seller Content"). By listing Seller Content on the platform, you grant us a non-exclusive, worldwide license to display, distribute, and promote your Seller Content in connection with operating the marketplace. This license ends 30 days after you remove the content, except for copies already purchased by Buyers.
>
> **For Buyers:** Your purchase grants you a license to use the template as specified in the Seller's license terms. You do not acquire ownership of the underlying intellectual property. Resale, redistribution, or sub-licensing of purchased templates is prohibited unless the Seller's license explicitly permits it.
>
> **Our Responsibilities:** We do not pre-screen Seller Content. We are a platform, not a publisher. However, we reserve the right to remove content that violates these Terms or applicable law.

---

**Disclaimer:** This skill generates draft terms of service for educational and planning purposes only. It does not constitute legal advice. Terms of service must be tailored to your specific product, business model, and applicable jurisdictions. Enforceability varies by jurisdiction and depends on how terms are presented to users. Always have a qualified attorney review your final terms of service before publication.
