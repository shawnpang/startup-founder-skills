---
name: architecture-design
description: When the user needs to design or evaluate system architecture — service boundaries, data models, API contracts, infrastructure topology, database selection, or dependency analysis. Also activate for "design the system", "how should I architect this", "monolith vs microservices", or architecture decision records.
related: [tech-stack-eval, security-review, code-review]
reads: [startup-context]
---

# Architecture Design

## When to Use
- Starting a new product or major feature that needs system design
- Choosing between monolith, modular monolith, microservices, or event-driven patterns
- Selecting a database (SQL vs NoSQL vs specialized) for a new project
- Analyzing dependencies for circular references, coupling issues, or outdated packages
- Creating architecture diagrams (Mermaid, PlantUML, ASCII) for documentation or review
- Writing Architecture Decision Records (ADRs) for technical choices
- Evaluating scalability bottlenecks or planning capacity

## Context Required
From `startup-context`: product description, tech stack, current state (prototype/beta/scaling), team size, expected scale (users, requests/sec, data volume). If missing, ask:
- What does this system need to do? (core use cases)
- What scale are you targeting? (users, requests/sec, data size)
- What is your team size and backend experience level?
- Are there hard constraints? (compliance, latency, budget, existing infra)

## Workflow
1. **Gather requirements** — Identify functional requirements (use cases), non-functional requirements (latency, throughput, availability, consistency), and constraints (budget, team size, compliance).
2. **Run architecture assessment** — Analyze the existing project structure to detect current patterns (MVC, layered, hexagonal, microservices indicators), code organization issues (god classes, mixed concerns), and layer violations.
3. **Analyze dependencies** — Examine the dependency tree for circular dependencies, coupling scores, and outdated packages across npm, Python, Go, or Rust projects.
4. **Select architecture pattern** — Use the decision workflows below to match team size, deployment needs, and data boundaries to the right pattern. For most early-stage startups, recommend modular monolith.
5. **Select database** — Match data characteristics, scale requirements, and consistency needs to the appropriate database technology using the selection workflow below.
6. **Design data model** — Produce an ER diagram in Mermaid. Define entity ownership: which module/service writes, others read via API.
7. **Define API contracts** — Specify key endpoints with method, path, request/response shapes, and error codes. Version from day one.
8. **Generate architecture diagram** — Produce a Mermaid C4 or flowchart diagram showing components, data stores, external services, and communication patterns.
9. **Write ADRs** — Document key decisions using the ADR format below.
10. **Identify risks** — Call out single points of failure, data consistency risks, and scaling bottlenecks with mitigations.

## Output Format
Deliver a structured architecture document with these sections:
- **Requirements Summary** — Functional, non-functional, and constraints
- **Architecture Assessment** — Detected pattern with confidence, issues, recommendations
- **System Diagram** — Mermaid C4 or flowchart (component, layer, or deployment view)
- **Domain Model** — Mermaid ER diagram with entity ownership
- **Module Boundaries** — Table: Module, Responsibility, Owns Data, Exposes API
- **API Contracts** — Key endpoints with method, path, request/response shapes
- **ADRs** — Architecture Decision Records for key choices
- **Dependency Analysis** — Total deps, coupling score, circular deps, outdated packages
- **Risks & Mitigations** — Table: Risk, Impact, Likelihood, Mitigation

## Frameworks & Best Practices

### Architecture Pattern Selection

| Team Size | Recommended Starting Point |
|-----------|---------------------------|
| 1-3 developers | Modular monolith |
| 4-10 developers | Modular monolith or service-oriented |
| 10+ developers | Consider microservices |

| Requirement | Recommended Pattern |
|-------------|-------------------|
| Rapid MVP development | Modular Monolith |
| Independent team deployment | Microservices |
| Complex domain logic | Domain-Driven Design |
| High read/write ratio difference | CQRS |
| Audit trail required | Event Sourcing |
| Third-party integrations | Hexagonal / Ports & Adapters |

**Default for early startups:** Modular monolith with clear module boundaries that can be extracted later. Microservices add operational overhead that kills small teams.

### Monolith vs Microservices Checklist

**Choose Monolith when:** team is small (<10), domain boundaries are unclear, rapid iteration is the priority, shared database is acceptable.

**Choose Microservices when:** teams can own services end-to-end, independent deployment is critical, different scaling requirements per component, domain boundaries are well understood.

**Hybrid approach:** Start monolith. Extract a service only when a module has significantly different scaling needs, a team needs independent deployment, or technology constraints require separation.

### Database Selection
Structured data with relationships or ACID needs points to SQL. Flexible/evolving schema or document-oriented data points to NoSQL. Quick reference: PostgreSQL (default for most apps), MongoDB (document store), Redis (caching/sessions), DynamoDB (serverless auto-scaling), TimescaleDB (time-series), CockroachDB/Spanner (global distribution).

### ADR Format
Use five fields: **Status** (Proposed/Accepted/Deprecated/Superseded), **Context** (what prompted the decision), **Decision** (what was chosen and why), **Consequences** (trade-offs and remaining risks), **Alternatives considered** (what else was evaluated and why it lost).

### Key Design Principles
- Every entity has a clear owner (one module writes, others read via API)
- Use UUIDs for primary keys if multi-service or future extraction is likely
- Version APIs from day one (`/v1/resource`); paginate all list endpoints (cursor-based preferred)
- Consistent error shapes: `{ "error": { "code": "...", "message": "..." } }`
- Design write operations for idempotency (idempotency keys)
- Synchronous calls (HTTP/gRPC) for queries needing immediate confirmation; async events for notifications, analytics, and cross-service data sync
- Avoid distributed transactions — use sagas or eventual consistency

## Related Skills
- `tech-stack-eval` — Chain when choosing specific technologies for the architecture
- `security-review` — Chain to review the architecture for threat vectors before implementation
- `code-review` — Chain after implementation to verify code matches architectural intent

## Examples

**Prompt:** "I'm building a SaaS project management tool. 3 engineers. How should I architect it?"

**Good output snippet:**
```
Given your team of 3 and early stage, I recommend a modular monolith.
Domain modules:

1. Auth Module — user accounts, roles, sessions
2. Projects Module — workspaces, projects, permissions
3. Tasks Module — tasks, assignments, comments, activity log
4. Notifications Module — email digests, in-app notifications

Each module gets its own DB schema (auth.*, projects.*) and communicates
through internal function calls with typed interfaces — not HTTP. This
gives you service-like boundaries without deployment complexity.

Architecture Assessment:
  Detected pattern: Layered Architecture (confidence: 85%)
  ✓ controllers/  - Presentation layer
  ✓ services/     - Business logic layer
  ✓ repositories/ - Data access layer
```

**Prompt:** "Should we use WebSockets or SSE for real-time collaboration?"

**Good output snippet:**
```
## ADR-001: Use WebSockets for Real-Time Collaboration
- Status: Proposed
- Context: Document editor needs sub-200ms latency for cursor positions
  and concurrent edits across 2-50 users per document.
- Decision: WebSockets via Socket.io with Redis pub/sub for horizontal
  scaling. SSE only supports server-to-client; we need bidirectional
  communication for operational transforms.
- Consequences: Adds WebSocket infrastructure (sticky sessions or Redis
  adapter), ~2KB memory per connection. Team needs OT/CRDT knowledge.
- Alternatives: SSE + POST (simpler but higher edit latency),
  Firebase Realtime DB (vendor lock-in, cost at scale).
```
