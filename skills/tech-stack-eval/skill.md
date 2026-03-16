---
name: tech-stack-eval
trigger: When the user needs to choose between technologies, frameworks, or tools — or says "which framework should I use", "compare X vs Y", "should we migrate from X to Y", "what database should I use".
related: [architecture-design, cicd-setup]
reads: [startup-context]
---

# Tech Stack Evaluation

## When to Use

- The user is choosing a framework, language, database, or cloud provider for a new project
- They want to compare two or more technologies head to head
- They are considering migrating from one technology to another
- They want to evaluate whether their current stack is right for their scaling needs
- They need a total cost of ownership (TCO) estimate for infrastructure decisions

## Context Required

From `startup-context`: product type, team skills, current tech stack, stage, scale expectations, budget constraints. Also ask:
- What problem are you solving with this technology? (don't let them start from a solution)
- What are your non-negotiable requirements? (performance, compliance, team familiarity)
- What is your team's experience with the options? (learning curve matters)
- What is your timeline? (tight deadlines favor familiar tools)
- What is your expected scale in 12 months? (avoid premature optimization and under-engineering)

## Workflow

1. **Clarify the decision** — What exactly is being decided and what are the real requirements? Push back if the user picks tech before defining the problem.
2. **Identify candidates** — List 2-4 realistic options. Exclude clearly wrong choices.
3. **Define evaluation criteria** — Select 6-8 weighted criteria from the master list below.
4. **Score each candidate** — Rate 1-5 on each criterion with justification.
5. **Assess ecosystem health** — Maintenance activity, community size, trajectory.
6. **Estimate TCO** — For infra decisions, project 12-month cost including engineering time.
7. **Analyze migration path** — If migrating, estimate effort, risk, and phased approach.
8. **Deliver recommendation** — Clear winner with rationale. No "it depends" without follow-up.

## Output Format

```markdown
# Tech Stack Evaluation: [Decision Title]

## Decision Context
What we're choosing and why it matters.

## Candidates
| Technology | Version | License | One-Liner |
|-----------|---------|---------|-----------|

## Evaluation Criteria
| Criterion | Weight | Why It Matters |
|-----------|--------|----------------|

## Scoring Matrix
| Criterion (weight) | Option A | Option B | Option C |
|---------------------|----------|----------|----------|
| ... | 4/5 | 3/5 | 5/5 |
| **Weighted Total** | **X.X** | **X.X** | **X.X** |

## Ecosystem Health
| Metric | Option A | Option B | Option C |
|--------|----------|----------|----------|
| GitHub Stars | | | |
| Weekly Downloads | | | |
| Last Release | | | |
| Open Issues / Ratio | | | |
| Major Companies Using | | | |

## TCO Estimate (12 months)
| Cost Category | Option A | Option B |
|---------------|----------|----------|

## Recommendation
Clear winner and why, with caveats.

## Migration Path (if applicable)
Phased approach to switch technologies.
```

## Frameworks & Best Practices

### Master Evaluation Criteria

Select 6-8 of these and assign weights (total = 100%):

- **Performance** — throughput, latency, resource efficiency
- **Developer Experience** — tooling, debugging, documentation quality
- **Learning Curve** — time for your team to become productive
- **Team Familiarity** — existing experience with this technology
- **Ecosystem & Libraries** — packages, integrations, third-party support
- **Maintenance & Longevity** — release cadence, corporate backing, bus factor
- **Hiring Pool** — availability of developers who know this technology
- **Scalability** — ability to handle 10-100x growth without rewrite
- **Cost** — licensing, hosting, operational overhead
- **Vendor Lock-in** — how hard is it to switch away later

### Ecosystem Health Scoring

Rate ecosystem health on a 3-tier scale:

- **Thriving** — regular releases (< 3 months), growing adoption, multiple corporate sponsors, active community
- **Stable** — regular releases (< 6 months), steady adoption, established community, no signs of decline
- **At Risk** — infrequent releases (> 12 months), declining adoption, key maintainers leaving, few contributors

### TCO Calculation Framework

Estimate over 12 months: compute, storage, bandwidth, licensing, engineering time (setup + ongoing maintenance hours x loaded cost), and operational overhead (monitoring, on-call). **Engineering time is usually the largest cost for startups** -- a technology saving $200/month on hosting but costing 40 extra engineering hours to operate is a net loss.

### Migration Risk Assessment

| Risk Level | Criteria |
|------------|----------|
| **Low** | Additive change, no data migration, can run in parallel, < 2 weeks |
| **Medium** | Requires data migration or API changes, 2-8 weeks, can be phased |
| **High** | Core system replacement, > 8 weeks, requires downtime or big-bang cutover |

Use the strangler fig pattern for migrations: route new traffic to the new system, migrate old incrementally. Always maintain rollback capability. Set a concrete cut-off date -- half-migrated systems are the worst outcome.

### Common Decision Anti-Patterns

- **Resume-Driven Development** — choosing tech for resumes, not fit
- **Hype Cycle Trap** — adopting at peak hype before proven stability
- **Premature Optimization** — distributed systems when a single Postgres handles the load
- **Sunk Cost Fallacy** — refusing to migrate because of prior investment
- **Ignoring Team Skills** — picking the "best" tool nobody on the team knows

## Related Skills

- `architecture-design` — chain when the tech stack decision feeds into a broader system design
- `cicd-setup` — chain to configure CI/CD for the chosen technology

## Examples

**Example prompt:** "Should we use PostgreSQL or MongoDB for our B2B SaaS app?"

**Good output snippet:**
```
## Recommendation: PostgreSQL

For a B2B SaaS application with relational data (users, organizations,
subscriptions, permissions), PostgreSQL is the clear choice.

**Key factors:**
- Your data is inherently relational — organizations have users, users
  have roles, roles have permissions. Modeling this in MongoDB requires
  denormalization that creates update anomalies.
- PostgreSQL's JSONB column gives you schema flexibility for
  user-defined fields without giving up transactions and joins.
- Ecosystem: every ORM, every hosting platform, every backup tool
  supports Postgres. The hiring pool is 3x larger.

**When MongoDB would win:** If you were building a content platform
with highly variable document shapes and no relational queries, MongoDB
would be the better fit. That's not your case.
```

**Example prompt:** "We're on Heroku and our bill is $2,400/month. Should we migrate to AWS?"

**Good output snippet:**
```
## TCO Estimate (12 months)

| Category | Heroku (Current) | AWS (Projected) |
|----------|------------------|-----------------|
| Compute | $1,200/mo | $480/mo (ECS Fargate) |
| Database | $800/mo | $350/mo (RDS) |
| Add-ons | $400/mo | $120/mo (equivalent) |
| Bandwidth | included | $50/mo |
| Engineering (setup) | $0 | $12,000 one-time |
| Engineering (ongoing) | 2 hrs/mo | 8 hrs/mo |
| **Annual Total** | **$28,800** | **$18,000** |

The migration saves ~$10,800/year but costs ~$12,000 in upfront
engineering time plus 6 hrs/mo additional operational overhead.
**Break-even is at month 14.** At your stage (Series A, team of 6),
I'd wait until the Heroku bill hits $4,000/mo before migrating — the
engineering hours are better spent on product right now.
```
