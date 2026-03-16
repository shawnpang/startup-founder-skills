---
name: code-review
trigger: When the user asks for a code review, shares code for feedback, or says "review this", "check my code", "what's wrong with this". Also activate when reviewing a pull request or diff.
related: [security-review, architecture-design]
reads: [startup-context]
---

# Code Review

## When to Use

- The user shares code (file, snippet, or diff) and asks for feedback
- They paste a pull request or ask to review changes
- They want to know if their code is production-ready
- They suspect a bug and want a second pair of eyes
- Pre-merge quality gate before deploying to production

## Context Required

From `startup-context`: tech stack, product stage, team size. Also need from the user:
- The code or diff to review
- What the code is supposed to do (feature context)
- Any specific concerns (performance, security, correctness)
- Language and framework if not obvious from the code

## Workflow

1. **Understand intent** — Read the code and any description to understand what it is supposed to accomplish. If unclear, ask the user before reviewing.
2. **Correctness pass** — Check for logic errors, off-by-one bugs, null/undefined handling, race conditions, and edge cases.
3. **Security pass** — Scan for OWASP Top 10 vulnerabilities: injection, broken auth, sensitive data exposure, XXE, broken access control, misconfig, XSS, insecure deserialization, known vulnerable components, insufficient logging.
4. **Performance pass** — Look for N+1 queries, missing indexes (if DB code), unnecessary re-renders (if frontend), O(n^2) algorithms on large datasets, missing caching opportunities, memory leaks.
5. **Maintainability pass** — Evaluate naming, function length, single responsibility, DRY violations, dead code, missing error handling, type safety.
6. **Test coverage assessment** — Note untested paths, missing edge case tests, brittle test patterns (testing implementation vs behavior).
7. **Categorize and report** — Group findings by severity and deliver structured output.

## Output Format

```markdown
# Code Review: [Feature/File Name]

## Summary
One-paragraph assessment: is this ready to merge, needs minor fixes, or needs rework?

## Findings

### Critical (must fix before merge)
- **[CRT-1] Title** — file:line — description, why it matters, suggested fix

### Major (should fix before merge)
- **[MAJ-1] Title** — file:line — description, why it matters, suggested fix

### Minor (fix when convenient)
- **[MIN-1] Title** — file:line — description, suggestion

### Positive (things done well)
- **[POS-1] Title** — file:line — what was done well and why it matters

## Security Checklist
- [ ] No SQL/NoSQL injection vectors
- [ ] No XSS vulnerabilities
- [ ] Auth/authz properly enforced
- [ ] Sensitive data not logged or exposed
- [ ] Input validated and sanitized

## Performance Notes
Brief assessment of performance implications.

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
Critical SQL injection and missing input validation. Needs fixes before merge.

## Findings
### Critical
- **[CRT-1] SQL Injection** — routes/users.js:14 — Email interpolated
  directly into SQL. Use parameterized queries instead.

### Major
- **[MAJ-1] No input validation** — routes/users.js:12 — Email used
  from `req.body` with no validation. Add zod/joi schema.
- **[MAJ-2] Missing error handling** — routes/users.js:18 — DB errors
  propagate as 500 with stack trace. Add try/catch.

### Positive
- **[POS-1] Clean async/await** — routes/users.js:11 — Easy to follow.
```

**Example prompt:** "Is this React component okay for production?"

**Good output snippet:**
```
### Major
- **[MAJ-1] N+1 API calls** — Dashboard.tsx:23 — `useEffect` calls
  `fetchMetrics(project.id)` per project. Batch into single request.
- **[MAJ-2] Missing dependency array** — Dashboard.tsx:22 — `useEffect`
  runs on every render. Add `[projects]` as dependency.
```
