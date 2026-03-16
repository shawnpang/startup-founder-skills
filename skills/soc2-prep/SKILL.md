---
name: soc2-prep
description: When the user needs to prepare for SOC 2, build a compliance roadmap, assess security posture, quantify security risk, or says "we need SOC 2", "security audit", "compliance", "enterprise customer wants SOC 2", "CISO advice".
related: [privacy-policy, security-review]
reads: [startup-context]
---

# SOC 2 Prep

## When to Use

Activate when a founder is preparing for SOC 2 certification, has been asked by a customer or prospect for a SOC 2 report, needs to quantify security risk for board or budget discussions, wants to build a compliance roadmap sequenced for business value, or needs to assess overall security posture. Also activate when the user mentions "SOC 2," "compliance audit," "trust service criteria," "security budget," "we need SOC 2 to close this deal," or "CISO."

## Context Required

- **From startup-context:** product type, tech stack, cloud infrastructure provider, team size, current security practices, business model, customer segments (enterprise customers often require SOC 2).
- **From the user:** which Trust Service Criteria are in scope, current state of documentation and policies, existing security tooling (SSO, MDM, monitoring), whether targeting Type I or Type II, desired timeline, budget constraints, whether an auditor is selected, and top 3 prospects' compliance requirements.

## Workflow

1. **Quantify the business case** — Frame security investment in dollars using ALE (Annual Loss Expectancy = Single Loss Expectancy x Annual Rate of Occurrence). Translate to board language: "This risk has $X expected annual loss. Mitigation costs $Y." Security is a sales enabler, not a checkbox.
2. **Scope definition** — Determine which Trust Service Criteria are in scope. Security (Common Criteria) is always required. Availability, Processing Integrity, Confidentiality, and Privacy are optional. Scope based on customer requirements and product type.
3. **Current state assessment** — Inventory existing policies, controls, and tooling. Identify what exists, what partially exists, and what is completely absent. Check the red flags list below.
4. **Gap analysis** — Map current state against each applicable TSC criterion. Produce a gap matrix showing compliant, partially compliant, and non-compliant areas.
5. **Compliance roadmap** — Sequence for business value: SOC 2 Type I (3-6 months) then SOC 2 Type II (12 months from start) then ISO 27001 or HIPAA based on customer demand. Do not pursue certifications before basic hygiene is in place.
6. **Policy generation** — Draft required policies tailored to the company's size. Early-stage startups need practical 2-5 page policies, not 50-page enterprise documents.
7. **Control implementation plan** — For each gap, define the control, the owner, the tooling, and the timeline.
8. **Evidence collection guidance** — Define what the auditor will request for each control and how to collect it systematically.
9. **Readiness review** — Perform a mock assessment before engaging the auditor.

## Output Format

```markdown
# Security & Compliance Assessment: [Company Name]

## Risk Quantification — top risks with ALE, mitigation cost, expected value
## Gap Analysis Matrix — TSC criterion, requirement, current state, gap, priority, remediation
## Compliance Roadmap — sequenced timeline: SOC 2 Type I > Type II > ISO 27001/HIPAA
## Policy Documents — generated as needed, each with purpose/scope/roles/statements/procedures
## Implementation Timeline — phased checklist with milestones
## Evidence Collection Checklist — per-control artifacts, storage location, refresh cadence
## Security Metrics Dashboard — table of key metrics with current values and targets
```

## Frameworks & Best Practices

### Risk Quantification (CISO Approach)

Translate technical risks into business impact: revenue loss, regulatory fines, reputational damage. Use ALE to prioritize.

**Formula:** `ALE = SLE x ARO` (Single Loss Expectancy x Annual Rate of Occurrence)

**Board language:** "A $200K security program preventing a $2M breach at 40% annual probability has $800K expected value. The program pays for itself 4x over."

Frame security spend as risk transfer cost, not overhead.

### Security Metrics

| Category | Metric | Target |
|----------|--------|--------|
| Risk | ALE coverage (mitigated / total) | > 80% |
| Detection | Mean Time to Detect (MTTD) | < 24 hours |
| Response | Mean Time to Respond (MTTR) | < 4 hours |
| Compliance | Controls passing audit | > 95% |
| Hygiene | Critical patches within SLA | > 99% |
| Access | Privileged accounts reviewed quarterly | 100% |
| Vendor | Tier 1 vendors assessed annually | 100% |
| Training | Phishing simulation click rate | < 5% |

### Trust Service Criteria Overview

**Security (Common Criteria -- always in scope):** CC1-CC2 (control environment, communication), CC3 (risk assessment), CC4-CC5 (monitoring, control activities), CC6 (logical/physical access, encryption), CC7-CC8 (system ops, vulnerability mgmt, incident response, change mgmt), CC9 (vendor management, business continuity).

**Optional:** Availability (A1), Processing Integrity (PI1), Confidentiality (C1), Privacy (P1-P8).

### Essential Policies (10 minimum)

Information Security, Access Control (MFA, least privilege, access reviews), Change Management (code review, rollback), Incident Response (detection through post-mortem), Risk Assessment (annual, with register), Vendor Management, Data Classification, Business Continuity/DR (RTO/RPO, backup testing), Acceptable Use, HR Security (background checks, onboarding/offboarding).

### Vendor Security Assessment Tiers

| Tier | Data Access | Assessment Level |
|------|------------|-----------------|
| Tier 1 | PII/PHI access | Full assessment annually |
| Tier 2 | Business data | Questionnaire + review |
| Tier 3 | No sensitive data | Self-attestation |

### Red Flags to Surface Proactively

- Security budget justified by benchmarks rather than risk analysis
- Certifications pursued before basic hygiene (patching, MFA, backups)
- No documented asset inventory -- cannot protect what you do not know you have
- IR plan exists but never tested; security reports to IT, not executive level
- Security questionnaire backlog > 30 days -- silently losing enterprise deals
- Vendor with sensitive data access has not been assessed

### Startup-Specific Guidance

**Type I vs Type II:** Type I examines control design at a point in time (3-6 months, good for closing the first enterprise deal). Type II examines control operation over 3-12 months (what sophisticated buyers want, plan 12 months total). Start Type I immediately; begin Type II observation once controls are in place.

**Right-Sizing by Stage:** Seed (5-15): foundational controls, automation-heavy, concise policies, one part-time owner. Series A (15-50): dedicated compliance owner or fractional CISO, formal access reviews. Series B+ (50+): full-time security team, internal audit, GRC platform.

**Cost-Effective Tooling:** Compliance automation (Vanta, Drata, Secureframe — significantly reduces manual effort), SSO (Google Workspace or Okta), MDM (Kandji or Jamf), monitoring (Datadog, PagerDuty), vulnerability scanning (Dependabot, Snyk, Trivy).

### Timeline Templates

- **Type I Aggressive (3 months):** Month 1 scope/gap/policies, Month 2 implementation, Month 3 readiness + audit.
- **Type I Standard (6 months):** Months 1-2 scope/policies, 3-4 implementation, 5 evidence, 6 audit.
- **Type II (12 months):** Months 1-6 complete Type I, 6-12 observation + evidence, Month 12 audit.

### Output Confidence Tagging

All findings tagged before reaching decision-makers: **Verified** (confirmed against evidence), **Medium** (reported but not independently verified), **Assumed** (inferred, needs validation).

## Related Skills

- `privacy-policy` — SOC 2 Privacy criteria (P1-P8) align directly with privacy policy commitments. Ensure consistency.
- `security-review` — Technical security controls from security-review map to SOC 2 Common Criteria (CC6, CC7, CC8). Use findings to inform gap analysis.

## Examples

### Example 1: Enterprise deal requires SOC 2
**User:** "A prospect wants SOC 2 before signing a $200K contract. We have nothing."

**Good output excerpt:**
> **Business case:** This $200K deal justifies a $30-50K compliance investment. At your stage, every enterprise deal blocked by missing SOC 2 has an opportunity cost.
>
> | Area | Status | Key Gaps |
> |------|--------|----------|
> | Access Control | Partial | MFA not enforced on AWS root, no SSO, no formal reviews |
> | Change Management | Partial | GitHub PRs used but no documented policy |
> | Incident Response | Missing | No documented plan, no on-call rotation |
> | Risk Assessment | Missing | No formal risk assessment conducted |
>
> **Recommended approach:** Type I in 3 months, then begin Type II observation.
> **Immediate actions:** (1) Sign up for compliance automation. (2) Enforce MFA everywhere. (3) Select an auditor with startup experience.
> **Interim response to prospect:** Share security questionnaire response, SOC 2 Type I commitment timeline, and a signed mutual NDA with security addendum.

### Example 2: Security posture assessment
**User:** "We already use Okta for SSO and do code reviews. Where are we relative to SOC 2?"

**Good output excerpt:**
> **Gap Analysis Summary: 55% ready**
>
> **Compliant:** CC6.1 Okta SSO with MFA, CC8.1 code reviews via PRs.
> **Partial:** CC6.2 no quarterly access reviews documented, CC7.2 IRP never tested, CC6.3 no formal offboarding checklist.
> **Missing:** CC3.1 no annual risk assessment, CC2.1 no security training, CC9.2 no vendor management, CC4.1 no control monitoring, all 10 required policies need drafting.

---

**Disclaimer:** This skill provides SOC 2 preparation guidance for planning purposes only. It does not constitute legal, audit, or professional compliance advice. SOC 2 reports can only be issued by a licensed CPA firm. Engage a qualified auditor to confirm readiness before scheduling an audit.
