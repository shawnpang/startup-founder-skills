---
name: security-review
trigger: When the user needs a security assessment — threat modeling, vulnerability review, auth flow audit, dependency scanning, or says "is this secure", "review for vulnerabilities", "threat model", "security audit", "pen test prep".
related: [code-review, architecture-design, soc2-prep]
reads: [startup-context]
---

# Security Review

## When to Use

- The user wants a security audit of their application, architecture, or specific feature
- They are implementing authentication or authorization and want it reviewed
- They need a threat model before launching a feature that handles sensitive data
- They want to prepare for a penetration test or security compliance audit
- They have a dependency vulnerability alert and need guidance on remediation
- They are handling PII, payment data, or health data and need to verify they are doing it safely

## Context Required

From `startup-context`: product type, tech stack, deployment environment, compliance requirements (SOC 2, HIPAA, PCI-DSS), data types handled (PII, payment, health). Also ask:
- What is the scope of this review? (full app, specific feature, auth system, single PR)
- What type of data do you handle? (PII, payment cards, health records, credentials)
- What is your deployment environment? (cloud provider, containerized, serverless)
- Do you have any compliance requirements? (SOC 2, HIPAA, PCI-DSS, GDPR)
- Have you had a security incident before? (context on known weaknesses)

## Workflow

1. **Define scope** — Clarify what is being reviewed: architecture, code, auth flows, dependencies, infrastructure, or all of the above.
2. **STRIDE threat model** — Walk through each STRIDE category against the system or feature to identify threats systematically.
3. **OWASP Top 10 audit** — Check the application against each OWASP Top 10 category with specific tests for the tech stack.
4. **Auth flow review** — Trace the authentication and authorization flow end to end. Check token handling, session management, password policies, and privilege escalation vectors.
5. **Dependency scan** — Identify vulnerable dependencies using appropriate tooling for the stack. Score by CVSS and assess exploitability.
6. **Infrastructure review** — Check for misconfigurations in cloud resources, exposed ports, overly permissive IAM, and missing encryption.
7. **Score and prioritize** — Assign CVSS scores to findings and categorize by severity and exploitability.
8. **Deliver report** — Produce structured findings with remediation steps and a prioritized action plan.

## Output Format

```markdown
# Security Review: [Scope Description]

## Executive Summary
Overall risk posture (Critical / High / Medium / Low) and top findings.

## Threat Model (STRIDE)
| Threat | Category | Asset | Impact | Likelihood | Risk |
|--------|----------|-------|--------|------------|------|

## Findings

### Critical (CVSS 9.0-10.0)
- **[SEC-1] Title** — CVSS X.X — description, impact, remediation

### High (CVSS 7.0-8.9)
- **[SEC-2] Title** — CVSS X.X — description, impact, remediation

### Medium (CVSS 4.0-6.9)
- **[SEC-3] Title** — CVSS X.X — description, impact, remediation

### Low (CVSS 0.1-3.9)
- **[SEC-4] Title** — CVSS X.X — description, impact, remediation

## Auth Flow Assessment
Diagram and analysis of authentication/authorization.

## Dependency Vulnerabilities
| Package | Current | Vuln | CVSS | Fix Version | Exploitable? |
|---------|---------|------|------|-------------|-------------|

## Remediation Roadmap
Prioritized action plan: what to fix first, second, third.
```

## Frameworks & Best Practices

### STRIDE Threat Modeling

Apply each category to every component and data flow:

| Category | Threat | Example Questions |
|----------|--------|-------------------|
| **Spoofing** | Impersonating a user or system | Can an attacker forge auth tokens? Are API keys rotatable? |
| **Tampering** | Modifying data or code | Can request bodies be modified in transit? Are webhook payloads signed? |
| **Repudiation** | Denying an action occurred | Are critical actions logged with timestamps? Are logs tamper-evident? |
| **Information Disclosure** | Exposing confidential data | Are error messages leaking stack traces? Is PII encrypted at rest? |
| **Denial of Service** | Making the system unavailable | Are rate limits enforced? Can a single user exhaust resources? |
| **Elevation of Privilege** | Gaining unauthorized access | Can a regular user access admin endpoints? Are roles checked server-side? |

### OWASP Top 10 Deep Checks

1. **Injection** — Parameterize all SQL/NoSQL; check OS commands, SSTI, LDAP
2. **Broken Auth** — argon2id/bcrypt (cost >= 10), session timeout, rate limiting, no credentials in URLs
3. **Sensitive Data Exposure** — TLS 1.2+, PII encrypted at rest, secrets in vault, HSTS header
4. **XXE** — Disable DTD processing, prefer JSON over XML
5. **Broken Access Control** — Server-side authz on every endpoint, no IDOR, CORS whitelist
6. **Misconfiguration** — Debug off, default creds removed, security headers (CSP, X-Frame-Options)
7. **XSS** — Context-aware output encoding, CSP header, HTTP-only secure cookies
8. **Insecure Deserialization** — Validate schema before processing, prefer JSON
9. **Vulnerable Components** — Run `npm audit`, `pip-audit`, `govulncheck`, or `trivy`
10. **Insufficient Logging** — Log auth events, admin actions, aggregate and alert

### CVSS v3.1 Scoring Guide

| Score | Severity | Criteria |
|-------|----------|----------|
| 9.0-10.0 | **Critical** | RCE, auth bypass, full data breach without authentication |
| 7.0-8.9 | **High** | Privilege escalation, significant data exposure, SSRF |
| 4.0-6.9 | **Medium** | Stored XSS, CSRF on state-changing actions, limited IDOR |
| 0.1-3.9 | **Low** | Info disclosure (version numbers), missing headers |

### Auth Flow Checklist

- [ ] Passwords hashed with argon2id or bcrypt (cost >= 10)
- [ ] JWT access tokens expire in 15 min, refresh tokens in 7 days, rotated on use
- [ ] Rate limiting on login (5 attempts / 15 min)
- [ ] Sessions invalidated on password change
- [ ] OAuth state parameter prevents CSRF; API keys scoped to minimum permissions
- [ ] MFA available for admin accounts; password reset tokens single-use, 1-hour expiry

### Security Scanning Tools

| Stack | SAST | Dependency Scan |
|-------|------|-----------------|
| **Node.js** | `semgrep`, `eslint-plugin-security` | `npm audit`, `snyk` |
| **Python** | `bandit`, `semgrep` | `pip-audit`, `safety` |
| **Go** | `gosec`, `semgrep` | `govulncheck` |
| **All** | `semgrep --config=auto` | `trivy fs .` / `trivy image` |

### Remediation Priority

1. Actively exploitable + critical data at risk — fix immediately
2. Auth/authz bypass — fix within 24 hours
3. Injection vulnerabilities — fix within 48 hours
4. Sensitive data exposure / critical dependency CVEs — fix within 1 week
5. Configuration hardening — fix within 2 weeks
6. Defense-in-depth — schedule in next sprint

## Related Skills

- `code-review` — chain when security findings require code-level fixes that should be reviewed
- `architecture-design` — chain when security findings reveal architectural flaws (e.g., missing auth layer, no network segmentation)
- `soc2-prep` — chain when the security review is part of compliance preparation

## Examples

**Example prompt:** "Review the security of our user authentication system. We use JWT with Express."

**Good output snippet:**
```
# Security Review: JWT Authentication System

## Executive Summary
Risk posture: **High**. Two critical findings: JWT secret is hardcoded
in source and tokens never expire. Three medium findings around missing
rate limiting and overly permissive CORS.

## Findings

### Critical (CVSS 9.8)
- **[SEC-1] Hardcoded JWT secret** — auth/config.js:3 — The JWT signing
  secret is hardcoded as `"supersecret123"`. Any attacker who reads your
  source (or decompiles your bundle) can forge arbitrary tokens for any
  user, including admins.
  **Remediation:** Move to environment variable `JWT_SECRET`. Generate
  with `openssl rand -base64 64`. Rotate every 90 days using a secret
  manager. Consider RS256 with key pair for token verification without
  sharing the signing key.

### Critical (CVSS 9.1)
- **[SEC-2] Tokens never expire** — auth/jwt.js:12 — `expiresIn` is not
  set in `jwt.sign()`. Once issued, a token is valid forever. A leaked
  token (from logs, browser storage, or network capture) grants permanent
  access.
  **Remediation:** Set `expiresIn: '15m'` for access tokens. Implement
  refresh tokens (7-day expiry, stored server-side, rotated on use).
```

**Example prompt:** "We got a Snyk alert about a critical CVE in lodash. What should we do?"

**Good output snippet:**
```
## Dependency Vulnerability: lodash (CVE-2021-23337, CVSS 7.2)

Command injection via `_.template`. Fix version: 4.17.21.

1. **Check exploitability** — search codebase for `_.template` with
   user-controlled input. If unused, risk is theoretical.
2. **Upgrade** — `npm install lodash@4.17.21` (patch, no breaking changes)
3. **Verify** — `npm audit` to confirm. Add `npm audit --audit-level=high`
   to CI to catch these going forward.
```
