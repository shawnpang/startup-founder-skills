---
name: soc2-prep
trigger: When the user needs to prepare for a SOC 2 audit, understand SOC 2 requirements, build compliance policies, or assess their readiness for SOC 2 Type I or Type II certification.
related: [privacy-policy, security-review]
reads: [startup-context]
---

# SOC 2 Prep

## When to Use
Activate when a founder is preparing for SOC 2 certification, has been asked by a customer or prospect for a SOC 2 report, needs to understand what SOC 2 requires, wants to build the policies and controls needed for compliance, or needs to perform a gap analysis against Trust Service Criteria. Also activate when the user mentions "SOC 2," "compliance audit," "trust service criteria," or "we need SOC 2 to close this deal."

## Context Required
- **From startup-context:** product type, tech stack, cloud infrastructure provider, team size, current security practices, business model, customer segments (enterprise customers often require SOC 2).
- **From the user:** which Trust Service Criteria are in scope, current state of documentation and policies, existing security tooling (SSO, MDM, monitoring), whether they are targeting Type I or Type II, desired timeline, budget constraints, and whether they have selected an auditor.

## Workflow
1. **Scope definition** — Determine which Trust Service Criteria (TSC) are in scope. Security is always required. Availability, Processing Integrity, Confidentiality, and Privacy are optional. Recommend scope based on customer requirements and product type.
2. **Current state assessment** — Inventory existing policies, controls, and tooling. Identify what already exists, what partially exists, and what is completely absent.
3. **Gap analysis** — Map current state against each applicable TSC criterion. Produce a gap matrix showing compliant, partially compliant, and non-compliant areas.
4. **Policy generation** — Draft the required policies using templates tailored to the company's size and stage. Early-stage startups need practical, implementable policies, not 50-page enterprise documents.
5. **Control implementation plan** — For each gap, define the specific control to implement, the owner, the tooling needed, and the timeline.
6. **Evidence collection guidance** — Define what evidence the auditor will request for each control and how to systematically collect and organize it.
7. **Readiness review** — Perform a mock assessment to validate that controls are operating and evidence is available before engaging the auditor.

## Output Format

### Gap Analysis Matrix
| TSC Criterion | Requirement | Current State | Gap | Priority | Remediation |
|---|---|---|---|---|---|
| CC6.1 | Logical access controls | AWS IAM in use, no SSO | Partial | High | Implement SSO, enforce MFA |

### Policy Documents (generated as needed)
Each policy follows a standard structure: Purpose, Scope, Roles & Responsibilities, Policy Statements, Procedures, Review Cadence.

### Implementation Timeline
Gantt-style or phased checklist with milestones for Type I readiness and Type II observation period.

### Evidence Collection Checklist
Per-control list of evidence artifacts, where they are stored, and how often they must be refreshed.

## Frameworks & Best Practices

### Trust Service Criteria Overview

**Security (Common Criteria — CC, always in scope):**
- CC1: Control Environment — Governance, organizational structure, board oversight.
- CC2: Communication & Information — Internal and external communication of policies, security awareness.
- CC3: Risk Assessment — Risk identification, fraud risk assessment, change management.
- CC4: Monitoring — Ongoing monitoring of controls, internal audit, deficiency remediation.
- CC5: Control Activities — Policies and procedures, technology controls, segregation of duties.
- CC6: Logical & Physical Access — Authentication, authorization, access provisioning/deprovisioning, encryption.
- CC7: System Operations — Change management, vulnerability management, incident detection and response.
- CC8: Change Management — Change authorization, testing, deployment controls.
- CC9: Risk Mitigation — Vendor management, business continuity, insurance.

**Availability (A1):**
- System availability commitments (SLAs), disaster recovery, backup and restoration, capacity planning.

**Processing Integrity (PI1):**
- Data processing is complete, valid, accurate, timely, and authorized. Input validation, error handling, reconciliation.

**Confidentiality (C1):**
- Identification of confidential information, access restrictions, secure disposal, confidentiality in communications.

**Privacy (P1-P8):**
- Notice, choice/consent, collection, use/retention/disposal, access, disclosure, quality, monitoring/enforcement.

### Essential Policies for SOC 2 (10 required at minimum)
1. **Information Security Policy** — Security framework, roles, management commitment.
2. **Access Control Policy** — Provisioning, deprovisioning, MFA, least privilege, access reviews.
3. **Change Management Policy** — Code review, deployment procedures, rollback plans.
4. **Incident Response Plan** — Detection, classification, containment, recovery, post-mortem.
5. **Risk Assessment Policy** — Annual risk assessment, risk register, treatment plans.
6. **Vendor Management Policy** — Third-party risk assessment, due diligence, monitoring.
7. **Data Classification Policy** — Classification levels, handling requirements, labeling.
8. **Business Continuity / DR Plan** — RTO/RPO definitions, backup procedures, recovery testing.
9. **Acceptable Use Policy** — Employee responsibilities, prohibited activities, BYOD rules.
10. **HR Security Policy** — Background checks, onboarding/offboarding, security training.

### Startup-Specific Guidance

**Type I vs. Type II Decision:**
- **Type I** examines control design at a point in time. Achievable in 3-6 months. Good for: closing that first enterprise deal that requires SOC 2.
- **Type II** examines control operation over a period (minimum 3 months, typically 6-12 months). This is what sophisticated buyers actually want. Plan for 12 months total from start to report.
- **Recommendation:** Start Type I prep immediately. Begin the Type II observation period as soon as Type I controls are in place.

**Right-Sizing for Stage:**
- Seed stage (5-15 people): Focus on foundational controls. Use tooling to automate. Policies can be concise (2-5 pages each). One person can own compliance part-time.
- Series A (15-50 people): Dedicated compliance owner or fractional CISO. More formal access reviews, vendor assessments. Begin segregation of duties.
- Series B+ (50+ people): Full-time security/compliance team. Internal audit function. GRC platform recommended.

**Cost-Effective Tooling Stack:**
- **Compliance automation:** Vanta, Drata, Secureframe, or Thoropass — these cut 40-60% of the manual effort.
- **SSO/Identity:** Google Workspace or Okta for centralized identity and MFA.
- **MDM:** Kandji (Mac) or Jamf for endpoint management and policy enforcement.
- **Monitoring:** Datadog, Sentry, or PagerDuty for system monitoring and alerting.
- **Vulnerability scanning:** Dependabot, Snyk, or Trivy for code/container vulnerabilities.

**Common Audit Findings to Prevent:**
- Users without MFA enabled (especially admin accounts).
- Terminated employees with active access (offboarding gaps).
- No evidence of quarterly access reviews.
- Missing or stale risk assessment (must be at least annual).
- Change management gaps — production changes without review or approval.
- Incomplete vendor inventory (shadow SaaS is the biggest gap).

### Timeline Templates
- **Type I Aggressive (3 months):** Month 1 scope/gap/policies, Month 2 implementation/training, Month 3 readiness review and audit.
- **Type I Standard (6 months):** Months 1-2 scope/policies, Months 3-4 implementation, Month 5 evidence collection, Month 6 audit.
- **Type II (12 months from zero):** Months 1-6 complete Type I, Months 6-12 observation period with continuous evidence collection, Month 12 Type II audit.

## Related Skills
- `privacy-policy` — SOC 2 Privacy criteria (P1-P8) align directly with privacy policy commitments. Ensure consistency between your published privacy policy and your SOC 2 privacy controls.
- `security-review` — Technical security controls reviewed in security-review map to SOC 2 Common Criteria (CC6, CC7, CC8). Use security-review findings to inform gap analysis.

## Examples

### Example 1: Early-stage startup needs SOC 2 to close a deal
**User:** "A big prospect wants to see our SOC 2 before signing a $200K contract. We have nothing. What do we do?"

**Good output excerpt:**
> **Recommended approach: Type I in 3 months, then begin Type II observation.**
>
> | Area | Status | Key Gaps |
> |---|---|---|
> | Access Control | Partial | MFA not enforced on AWS root, no formal access reviews, no SSO |
> | Change Management | Partial | GitHub PRs used but no documented policy, no approval requirements |
> | Incident Response | Missing | No documented plan, no on-call rotation |
> | Risk Assessment | Missing | No formal risk assessment conducted |
>
> **Immediate Actions:** (1) Sign up for compliance automation (Vanta/Drata). (2) Enforce MFA across all systems. (3) Select an auditor with startup experience.
>
> **Interim Response to Prospect:** Share a security questionnaire response, your SOC 2 Type I commitment timeline, and a signed mutual NDA with security addendum.

### Example 2: Gap analysis for a company with some controls
**User:** "We already use Okta for SSO, have a basic incident response plan, and do code reviews. Where are we relative to SOC 2?"

**Good output excerpt:**
> **Gap Analysis Summary: 55% ready**
>
> **Green:** CC6.1 Okta SSO with MFA, CC8.1 code reviews via PRs, CC7.2 basic IRP exists.
>
> **Yellow:** CC6.2 no quarterly access reviews documented, CC7.2 IRP never tested, CC6.3 no formal offboarding checklist.
>
> **Red:** CC3.1 no annual risk assessment, CC2.1 no security training, CC9.2 no vendor management, CC4.1 no control monitoring, all 10 required policies need drafting.

---

**Disclaimer:** This skill provides SOC 2 preparation guidance for planning purposes only. It does not constitute legal, audit, or professional compliance advice. SOC 2 reports can only be issued by a licensed CPA firm. Requirements may vary by auditor interpretation, and specific controls must be validated with your chosen audit firm. Engage a qualified auditor or compliance consultant to confirm your readiness before scheduling an audit.
