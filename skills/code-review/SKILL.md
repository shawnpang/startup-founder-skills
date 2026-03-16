---
name: code-review
description: When the user asks for a code review, shares code for feedback, or says "review this", "check my code", "what's wrong with this". Also activate when reviewing a pull request or diff.
related: [security-review, architecture-design]
reads: [startup-context]
---

# Code Review

## When to Use
- The user shares code (file, snippet, or diff) and asks for feedback
- They paste a pull request or want to know if code is production-ready
- Pre-merge quality gate or bug hunting
- Reviewing architectural decisions in a PR

## Context Required
From `startup-context`: tech stack, product stage, team size. Also need from the user:
- The code or diff to review
- What the code is supposed to do (PR purpose or feature context)
- Any specific concerns (performance, security, correctness)
- Language and framework if not obvious from the code

## Workflow
Follow a structured five-step methodology. Each step must be completed before moving to the next.

1. **Context** — Understand and summarize the PR's purpose before any analysis. Recap the intent back to the user in 1-2 sentences. If unclear, ask before proceeding. Never start reviewing without understanding what the code is trying to accomplish.
2. **Structure** — Evaluate architectural decisions and design patterns:
   - Does the code belong in the right module/layer?
   - Are abstractions appropriate (not too many, not too few)?
   - Does this change align with the existing codebase patterns?
   - For non-obvious design choices, acknowledge the author's reasoning before proposing alternatives.
3. **Details** — Assess code quality across multiple dimensions:
   - **Correctness:** Logic errors, off-by-one bugs, null/undefined handling, race conditions, edge cases
   - **Security:** OWASP Top 10 baseline — injection, broken auth, data exposure, XSS, access control, misconfig, insecure deserialization, vulnerable components
   - **Performance:** N+1 queries, unnecessary re-renders, O(n^2) on large datasets, missing caching, memory leaks
   - **Naming and clarity:** Do names communicate intent? Are functions focused on a single responsibility?
4. **Tests** — Validate test coverage with equal rigor as code review:
   - Are behavioral assertions present (not just implementation testing)?
   - Are edge cases and error paths covered?
   - Are tests brittle or resilient to refactoring?
   - What test cases are missing?
5. **Feedback** — Generate a prioritized, categorized report with specific code examples and concrete improvements. Recognize strong patterns and good decisions explicitly.

## Output Format

```markdown
# Code Review: [Feature/File Name]

## Summary
One-paragraph assessment: what the PR does, whether it is ready to merge, needs minor fixes, or needs rework.

## Findings

### Critical (must fix before merge)
- **[CRT-1] Title** — file:line — description, why it matters, suggested fix with code example

### Major (should fix before merge)
- **[MAJ-1] Title** — file:line — description, why it matters, suggested fix

### Minor (fix when convenient)
- **[MIN-1] Title** — file:line — description, suggestion

### Positive (things done well)
- **[POS-1] Title** — file:line — what was done well and why it matters

## Questions
Clarifying questions about non-obvious design choices before blocking on them.

## Suggested Tests
- Test case 1
- Test case 2
```

## Frameworks & Best Practices

### Severity Definitions
| Severity | Definition | Action |
|----------|-----------|--------|
| **Critical** | Security vulnerability, data loss risk, crash in production, broken core functionality | Block merge |
| **Major** | Significant bug, performance regression, missing error handling on critical path, architectural violation | Should fix before merge |
| **Minor** | Style issue, naming improvement, minor optimization, documentation gap | Fix when convenient |
| **Positive** | Well-written code, good pattern usage, thoughtful error handling | Acknowledge and reinforce |

### Review Principles
- **Always ground feedback in specifics.** Every finding must reference a file, line, and include a concrete improvement — not just "this could be better."
- **Recognize good work explicitly.** Call out strong patterns, clean abstractions, and thoughtful error handling. Reviews that only flag problems are demoralizing and incomplete.
- **Acknowledge author reasoning.** For non-obvious choices, assume the author had a reason. Ask before overriding. Phrase as "I see you chose X — was that because of Y? If so, consider Z as an alternative."
- **Do not block on style when automated tooling handles it.** Linting and formatting are the job of CI, not reviewers. Focus on logic, architecture, and correctness.
- **Treat test review with equal weight.** Tests are not an afterthought. Missing tests for critical paths is a major finding, not a minor one.

### OWASP Top 10 Quick Checks
1. **Injection** — Are user inputs parameterized? Check SQL, NoSQL, OS command, LDAP
2. **Broken Auth** — Sessions secure? Tokens rotated? Passwords hashed (bcrypt/argon2)?
3. **Sensitive Data Exposure** — Secrets in env vars (not code)? PII encrypted at rest?
4. **XXE** — XML parsing disabled or configured to reject external entities?
5. **Broken Access Control** — Every endpoint checks authorization, not just authentication?
6. **Misconfiguration** — Debug modes off? CORS restrictive? Security headers set?
7. **XSS** — Outputs encoded? No `dangerouslySetInnerHTML` / `v-html` with user data?
8. **Insecure Deserialization** — Serialized objects from untrusted sources validated?
9. **Vulnerable Components** — Dependencies up to date? Any known CVEs?
10. **Insufficient Logging** — Auth failures, access violations, and errors logged?

### N+1 Query Detection
- Looping over a collection and making a DB call per item
- ORM lazy loading inside a loop (e.g., `user.posts` in a `for user in users` loop)
- GraphQL resolvers fetching related data per parent without DataLoader
- **Fix:** Eager loading, batch queries, or DataLoader pattern

### Language-Agnostic Red Flags
- Functions longer than 40 lines or more than 3 levels of nesting
- Boolean params that change behavior (use separate functions)
- Catch blocks that swallow exceptions silently
- Hardcoded values that should be configuration
- Missing input validation on public API boundaries

## Related Skills
- `security-review` — chain for a deep-dive security audit when critical security findings surface
- `architecture-design` — chain when code review reveals structural problems that need architectural rethinking

## Examples

**Example prompt:** "Review this Express route handler for creating users."

**Good output snippet:**
```
# Code Review: POST /api/users Handler

## Summary
The handler creates users but has a critical SQL injection vulnerability and missing
input validation. Needs fixes before merge. Clean async/await usage is a positive.

## Findings
### Critical
- **[CRT-1] SQL Injection** — routes/users.js:14 — Email interpolated
  directly into SQL string. Use parameterized queries:
  `db.query('INSERT INTO users (email) VALUES ($1)', [email])`

### Major
- **[MAJ-1] No input validation** — routes/users.js:12 — Email from
  `req.body` used with no validation. Add zod/joi schema validation.
- **[MAJ-2] Missing error handling** — routes/users.js:18 — DB errors
  propagate as 500 with stack trace. Wrap in try/catch, return generic error.

### Positive
- **[POS-1] Clean async/await** — routes/users.js:11 — Easy to follow,
  no callback nesting.

## Questions
- Is there a validation middleware already in the project that should be reused here?
```
