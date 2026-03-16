---
name: cicd-setup
description: When the user needs to set up or improve CI/CD pipelines — GitHub Actions, GitLab CI, deployment automation, or says "set up CI", "automate deployment", "add tests to pipeline", "fix my build".
related: [code-review, security-review]
reads: [startup-context]
---

# CI/CD Setup

## When to Use

- Setting up CI for a new project from scratch
- Replacing unreliable copied pipeline configurations that do not match the actual stack
- Transitioning between GitHub Actions and GitLab CI platforms
- Reviewing whether pipeline stages align with actual project tooling
- Optimizing slow builds (caching, parallelism, conditional steps)
- Establishing a stable CI foundation before adding specialized hardening

## Context Required

From `startup-context`: tech stack, deployment target, team size. Also detect or ask:
- Language and framework (auto-detect from repo files before asking)
- Deployment target (Vercel, AWS, GCP, Fly.io, etc.)
- CI/CD platform (default: GitHub Actions; also supports GitLab CI)
- Environments (dev, staging, production) and existing test coverage
- Secrets and credentials needed for build or deploy

## Workflow

1. **Detect stack from repo signals** — Scan for lockfiles (package-lock.json, yarn.lock, poetry.lock, go.sum, Cargo.lock), language manifests (package.json, pyproject.toml, go.mod), and script definitions (test, lint, build commands). Lockfiles indicate package manager choice. Absent scripts trigger conservative defaults. Never assume Node for a Python project.
2. **Choose pipeline stages** — Start with a dependable baseline: checkout, runtime setup, dependency install with caching, then sequential lint, test, build. Only add complexity after the baseline works.
3. **Generate pipeline config** — Write CI config for the detected platform. Output machine-readable YAML with correct caching strategy for the detected package manager. Verify all referenced commands actually exist in the project.
4. **Configure secrets** — List required secrets and how to add them. Use platform-managed secret stores. Recommend OIDC for cloud auth over long-lived keys. Never hardcode credentials in YAML.
5. **Add deployment stages safely** — Begin CI-only (lint/test/build). Add staging deployment with explicit environment info. Add production deployment with manual approval. Maintain transparency in rollout and rollback procedures.
6. **Validate before merge** — Confirm generated YAML is syntactically valid, all commands exist in the project, caching aligns with the package manager, and branch protections match organizational requirements.
7. **Deliver config and instructions** — Full config file plus setup steps.

## Output Format

```markdown
# CI/CD Pipeline: [Project Name]
## Stack Detection Results — detected language, runtime, tools, and build commands
## Pipeline Overview — Mermaid flowchart showing stages
## Pipeline Configuration — Full YAML config file
## Secrets Required — table: name, where to get, how to add
## Setup Instructions — step-by-step to activate
## Validation Checklist — commands verified, caching confirmed, branch rules set
## Optimization Notes — caching strategy, estimated build time
```

## Frameworks & Best Practices

### Detection-First Pipeline Generation

Always detect before generating. The detector relies on concrete file signals:
- Lockfiles indicate package manager choice (npm, yarn, pip, cargo, go modules)
- Language manifests identify runtime families
- Script definitions in package.json/pyproject.toml inform lint/test/build commands
- Absent scripts trigger conservative default commands rather than assumptions

### Caching Strategies by Ecosystem

| Ecosystem | Cache Path | Cache Key |
|-----------|-----------|-----------|
| Node.js | `~/.npm` or `node_modules` | `hashFiles('**/package-lock.json')` |
| Python | `~/.cache/pip` | `hashFiles('**/requirements*.txt')` |
| Go | `~/go/pkg/mod` | `hashFiles('**/go.sum')` |
| Rust | `~/.cargo/registry`, `target/` | `hashFiles('**/Cargo.lock')` |
| Ruby | `vendor/bundle` | `hashFiles('**/Gemfile.lock')` |

### Pipeline Architecture Principles

- **Lint first** — fail early before expensive test runs
- **Sequential baseline** — checkout, install, lint, test, build, then artifact publish
- **Cache aggressively** — cuts 30-60% off build times
- **Pin action versions** — use SHA hashes, not tags, for supply chain security
- **Set timeouts** (`timeout-minutes: 15`) and **concurrency** to cancel redundant runs
- **One enhancement at a time** — do not add matrix builds, security scanning, and deployment in one PR

### Environment Strategy

| Environment | Trigger | Approval | Purpose |
|-------------|---------|----------|---------|
| **CI** | Every push/PR | None | Run lint + tests |
| **Staging** | Merge to `main` | None (auto) | Integration testing, QA |
| **Production** | Git tag or manual | Required | Live users |

### Common Pitfalls

1. Applying Node-specific pipelines to Python or Go repos (detect first)
2. Enabling deployment before establishing reliable test coverage
3. Overlooking dependency caching configuration
4. Running full matrix builds on minor branch updates (use path filters)
5. Omitting branch protections on production deployments
6. Embedding credentials directly in pipeline YAML

### Scaling & Platform Notes

- Split long-running jobs when execution exceeds 10 minutes
- Implement test matrices only when genuine compatibility concerns exist
- GitHub Actions for GitHub ecosystem; GitLab CI for self-hosted SCM+CI
- Maintain a single canonical pipeline source per repository

## Related Skills

- `code-review` — chain to review the CI config itself before committing
- `security-review` — chain to add or audit security scanning stages (trivy, semgrep, npm audit)

## Examples

**Example prompt:** "Set up CI/CD for my Next.js app deployed on Vercel."

**Good output snippet:**
```yaml
name: CI
on:
  push: { branches: [main] }
  pull_request: { branches: [main] }
concurrency:
  group: ${{ github.workflow }}-${{ github.ref }}
  cancel-in-progress: true
jobs:
  lint:
    runs-on: ubuntu-latest
    timeout-minutes: 10
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with: { node-version: 20, cache: 'npm' }
      - run: npm ci
      - run: npm run lint && npx tsc --noEmit
  test:
    runs-on: ubuntu-latest
    timeout-minutes: 15
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with: { node-version: 20, cache: 'npm' }
      - run: npm ci && npm test -- --coverage
```

**Example prompt:** "My Python CI takes 8 minutes, how do I speed it up?"

**Good output snippet:**
```
Stack detection shows: Python 3.11, pytest, pip. Three fixes to cut to ~3 minutes:
(1) Add pip caching keyed on hashFiles('requirements*.txt'),
(2) split unit/integration tests into parallel jobs,
(3) add path filters to skip CI on docs-only changes.
```
