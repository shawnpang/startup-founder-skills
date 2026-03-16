---
name: architecture-design
trigger: When the user needs to design or evaluate system architecture — service boundaries, data models, API contracts, or infrastructure topology. Also activate when they say "design the system", "how should I architect this", or are planning a new major feature.
related: [tech-stack-eval, security-review, code-review]
reads: [startup-context]
---

# Architecture Design

## When to Use

- The user is starting a new product or major feature and needs a system design
- They want to evaluate monolith vs microservices for their current stage
- They need data model design, API contract definitions, or service boundary decisions
- They want an Architecture Decision Record (ADR) for a technical choice
- They are hitting scaling pain and need to restructure their system

## Context Required

From `startup-context`: product description, tech stack, current state (prototype/beta/scaling), team size, expected scale (users, requests, data volume). If missing, ask:
- What does this system need to do? (core use cases)
- What scale are you targeting? (users, requests/sec, data size)
- What is your team size and backend experience level?
- Are there hard constraints? (compliance, latency, budget, existing infra)

## Workflow

1. **Gather requirements** — Identify functional requirements (use cases), non-functional requirements (latency, throughput, availability, consistency), and constraints (budget, team, compliance).
2. **Map domain boundaries** — Use domain-driven design to identify bounded contexts. Each context is a candidate service or module boundary.
3. **Choose architecture pattern** — Evaluate monolith-first vs microservices vs modular monolith using the decision framework below. For most early-stage startups, recommend modular monolith.
4. **Design data model** — Produce an ER diagram in Mermaid. Define ownership: which service/module owns which entities. Identify shared data and how it will be accessed (API calls vs read replicas vs events).
5. **Define API contracts** — Specify key endpoints with method, path, request/response shapes, and error codes. Use OpenAPI-style descriptions.
6. **Draw system diagram** — Produce a Mermaid C4 or flowchart diagram showing components, data stores, external services, and communication patterns.
7. **Write ADR** — Document the key decisions using the ADR format below.
8. **Identify risks** — Call out single points of failure, data consistency risks, and scaling bottlenecks. Suggest mitigations.

## Output Format

Deliver a structured architecture document with these sections:

```markdown
# Architecture: [System Name]

## Requirements Summary
- Functional: ...
- Non-functional: ...
- Constraints: ...

## System Diagram
(Mermaid diagram)

## Domain Model
(Mermaid ER diagram)

## Service / Module Boundaries
| Module | Responsibility | Owns Data | Exposes API |
|--------|---------------|-----------|-------------|

## API Contracts
### [Endpoint Group]
- `POST /resource` — description
  - Request: { ... }
  - Response: { ... }

## Architecture Decision Records
(ADR entries — see format below)

## Risks & Mitigations
| Risk | Impact | Likelihood | Mitigation |
|------|--------|------------|------------|
```

## Frameworks & Best Practices

### Monolith vs Microservices Decision Framework

Use this scoring to recommend an architecture pattern:

| Factor | Monolith Favored | Microservices Favored |
|--------|------------------|-----------------------|
| Team size | < 8 engineers | > 15 engineers |
| Domain complexity | Single domain | Multiple distinct domains |
| Scaling needs | Uniform load | Wildly different per service |
| Deployment cadence | Weekly | Multiple times daily per team |
| Stage | Pre-seed to Series A | Series B+ with proven PMF |

**Default recommendation for early startups:** Modular monolith with clear module boundaries that can be extracted later. Microservices add operational overhead that kills small teams.

### ADR Format

```markdown
## ADR-NNN: [Title]
- **Status:** Proposed | Accepted | Deprecated | Superseded
- **Context:** What situation prompted this decision
- **Decision:** What we chose and why
- **Consequences:** Trade-offs accepted, what changes, what risks remain
- **Alternatives considered:** What else was evaluated and why it lost
```

### Key Design Principles

- Every entity has a clear owner (one service/module writes, others read via API)
- Use UUIDs for primary keys if multi-service or future extraction is likely
- Version APIs from day one (`/v1/resource`); paginate all list endpoints (cursor-based preferred)
- Return consistent error shapes: `{ "error": { "code": "...", "message": "..." } }`
- Design write operations for idempotency (idempotency keys)
- Use synchronous calls (HTTP/gRPC) for queries needing immediate confirmation; use async events for notifications, analytics, and cross-service data sync
- Avoid distributed transactions — use sagas or eventual consistency

## Related Skills

- `tech-stack-eval` — chain when the user needs help choosing specific technologies for the architecture
- `security-review` — chain to review the architecture for threat vectors before implementation
- `code-review` — chain after implementation to verify code matches architectural intent

## Examples

**Example prompt:** "I'm building a SaaS project management tool. We have 3 engineers. How should I architect the backend?"

**Good output snippet:**
```
Given your team of 3 and early stage, I recommend a modular monolith using
your existing Node.js/PostgreSQL stack. Here are the domain modules:

1. **Auth Module** — user accounts, roles, sessions
2. **Projects Module** — workspaces, projects, permissions
3. **Tasks Module** — tasks, assignments, comments, activity log
4. **Notifications Module** — email digests, in-app notifications

Each module gets its own DB schema (e.g., `auth.*`, `projects.*`) and
communicates through internal function calls with typed interfaces — not
HTTP. This gives you service-like boundaries without deployment complexity.
```

**Example prompt:** "We need to add real-time collaboration to our document editor. Should we use WebSockets or SSE? Write me an ADR."

**Good output snippet:**
```
## ADR-001: Use WebSockets for Real-Time Collaboration
- **Status:** Proposed
- **Context:** Our document editor needs sub-200ms latency for cursor
  positions and concurrent edits across 2-50 users per document.
- **Decision:** WebSockets via Socket.io with Redis pub/sub for horizontal
  scaling. SSE is simpler but only supports server-to-client; we need
  bidirectional communication for operational transforms.
- **Consequences:** Adds WebSocket infrastructure (sticky sessions or Redis
  adapter), increases server memory per connection (~2KB/conn). Team needs
  to learn OT/CRDT patterns.
- **Alternatives considered:** SSE + POST (simpler but higher latency for
  edits), Firebase Realtime DB (vendor lock-in, cost at scale).
```
