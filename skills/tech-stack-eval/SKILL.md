---
name: tech-stack-eval
description: When the user needs to choose between technologies, frameworks, or tools — or says "which framework should I use", "compare X vs Y", "should we migrate from X to Y", "what database should I use", "calculate TCO".
related: [architecture-design, cicd-setup]
reads: [startup-context]
---

# Tech Stack Evaluation

## When to Use

- Comparing frontend/backend frameworks or libraries for new projects
- Evaluating cloud providers (AWS vs Azure vs GCP) for specific workloads
- Planning technology migrations with risk and effort assessment
- Calculating TCO including hidden costs; making build vs. buy decisions
- Assessing open-source library viability and ecosystem health

Do NOT use when: the decision is trivial (use team preference), the technology is already mandated, or this is an emergency production issue.

## Context Required

From `startup-context`: product type, team skills, tech stack, stage, scale, budget. Also ask:
- What problem are you solving? (push back on solution-first thinking)
- Non-negotiable requirements (performance, compliance, team familiarity)
- Team experience with each option and timeline pressure (tight deadlines favor familiar tools)
- Growth expectations that affect scalability requirements

## Workflow

1. **Clarify the decision** — What exactly is being decided and what are the real requirements? Push back if the user picks tech before defining the problem.
2. **Identify candidates** — List 2-4 realistic options. Exclude clearly wrong choices early.
3. **Define weighted evaluation criteria** — Select 6-8 criteria from the master list below. Assign weights based on the user's priorities (total = 100%).
4. **Score each candidate** — Rate 1-5 on each criterion with one-line justification per score.
5. **Assess ecosystem health** — Evaluate GitHub activity, npm/PyPI adoption, community strength, corporate backing, and trajectory (growing, stable, declining).
6. **Calculate TCO** — Project 5-year total cost including compute, storage, bandwidth, licensing, engineering time (setup + ongoing), and operational overhead. Engineering time is usually the largest cost for startups.
7. **Analyze migration path** — If migrating, estimate effort, risks, timeline, and recommend phased approach (strangler fig pattern).
8. **Deliver recommendation** — Clear winner with rationale and confidence level. No "it depends" without a follow-up question to resolve the ambiguity.

## Output Format

```markdown
# Tech Stack Evaluation: [Decision Title]

## Decision Context — what we are choosing and why it matters
## Candidates — table: technology, version, license, one-liner
## Evaluation Criteria — table: criterion, weight, why it matters
## Scoring Matrix — table: criterion (weight), scores per option, weighted total
## Ecosystem Health — table: GitHub stars, weekly downloads, last release, open issues, major users
## TCO Estimate — table: cost category by option over 12 months or 5 years
## Security & Compliance — vulnerability history, compliance readiness (SOC 2, GDPR)
## Recommendation — clear winner, rationale, confidence level, caveats
## Migration Path (if applicable) — phased plan with timeline and rollback strategy
```

## Frameworks & Best Practices

### Master Evaluation Criteria

Select 6-8 and assign weights (total = 100%):

- **Performance** — throughput, latency, resource efficiency for the specific workload
- **Developer Experience** — tooling, debugging, documentation quality, error messages
- **Learning Curve / Team Familiarity** — time to productivity for the current team
- **Ecosystem & Libraries** — packages, integrations, third-party support
- **Maintenance & Longevity** — release cadence, corporate backing, bus factor
- **Hiring Pool** — developer availability in your market and salary band
- **Scalability** — handle 10-100x growth without a rewrite
- **Cost / Vendor Lock-in** — TCO and switching cost if you need to move later
- **Security & Compliance** — vulnerability track record, compliance tooling readiness

### Ecosystem Health Scoring

| Level | Criteria |
|-------|----------|
| **Thriving** | Regular releases (< 3 months), growing adoption, multiple corporate sponsors, active community |
| **Stable** | Regular releases (< 6 months), steady adoption, established community, no decline signs |
| **At Risk** | Infrequent releases (> 12 months), declining downloads, key maintainers leaving, few contributors |

### TCO Calculation Framework

Project over 12 months minimum (5 years for infrastructure decisions): compute, storage, bandwidth, licensing, engineering time (setup + ongoing maintenance x loaded cost), operational overhead (monitoring, on-call), and hidden costs (training, migration tooling, dual-running).

**Engineering time is usually the largest cost for startups.** A technology saving $200/month on hosting but costing 40 extra engineering hours to operate is a net loss.

### Migration Risk Assessment

| Risk Level | Criteria |
|------------|----------|
| **Low** | Additive change, no data migration, can run in parallel, < 2 weeks |
| **Medium** | Requires data migration or API changes, 2-8 weeks, can be phased |
| **High** | Core system replacement, > 8 weeks, requires downtime or big-bang cutover |

Use the strangler fig pattern: route new traffic to the new system, migrate old incrementally. Always maintain rollback capability. Set a concrete cut-off date -- half-migrated systems are the worst outcome.

### Confidence Levels

| Level | Score | Interpretation |
|-------|-------|----------------|
| **High** | 80-100% | Clear winner, strong data, wide margin |
| **Medium** | 50-79% | Trade-offs present, recommendation holds but with caveats |
| **Low** | < 50% | Close call, limited data, suggest a proof-of-concept before committing |

### Common Decision Anti-Patterns

- **Resume-Driven Development** — choosing tech for resumes, not fit
- **Hype Cycle Trap** — adopting at peak hype before stability is proven
- **Premature Optimization** — distributed systems when a single Postgres handles the load
- **Sunk Cost Fallacy** — refusing to migrate because of prior investment
- **Ignoring Team Skills / Solution-First Thinking** — picking tech nobody knows, or selecting technology before defining the problem

## Related Skills

- `architecture-design` — chain when the tech stack decision feeds into a broader system design
- `cicd-setup` — chain to configure CI/CD for the chosen technology

## Examples

**Example prompt:** "Compare React vs Vue for a SaaS dashboard. Priorities: developer productivity (40%), ecosystem (30%), performance (30%)."

**Good output snippet:**
```
## Scoring Matrix
| Criterion (weight)       | React | Vue  |
|--------------------------|-------|------|
| Developer Productivity (40%) | 4/5   | 4/5  |
| Ecosystem (30%)          | 5/5   | 4/5  |
| Performance (30%)        | 4/5   | 5/5  |
| **Weighted Total**       | **4.3** | **4.3** |

Confidence: Medium (55%). Scores are nearly identical. Recommendation: React,
but only because your team has 2 years of React experience (not captured in
the matrix). If the team were greenfield, Vue's developer experience gives it
a slight edge. This is close enough to warrant team preference as the tiebreaker.
```

**Example prompt:** "We're on Heroku at $2,400/mo. Should we migrate to AWS?"

**Good output snippet:**
```
## TCO Estimate (12 months)
| Category             | Heroku    | AWS               |
|----------------------|-----------|-------------------|
| Compute              | $1,200/mo | $480/mo (ECS)     |
| Database             | $800/mo   | $350/mo (RDS)     |
| Add-ons              | $400/mo   | $120/mo           |
| Engineering (setup)  | $0        | $12,000 one-time  |
| Engineering (ongoing)| 2 hrs/mo  | 8 hrs/mo          |
| **Annual Total**     | **$28,800** | **$18,000**     |

Break-even at month 14. At Series A with a team of 6, wait until Heroku hits
$4,000/mo — engineering hours are better spent on product right now.
```
