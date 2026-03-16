---
name: cicd-setup
trigger: When the user needs to set up or improve CI/CD pipelines — GitHub Actions, GitLab CI, deployment automation, or says "set up CI", "automate deployment", "add tests to pipeline", "fix my build".
related: [code-review, security-review]
reads: [startup-context]
---

# CI/CD Setup

## When to Use

- The user is starting a new project and needs CI/CD from scratch
- They want to add testing, linting, or security scanning to an existing pipeline
- They need environment-specific deployment stages (staging, production)
- They are migrating between CI/CD platforms
- Their builds are slow and need optimization (caching, parallelism)
- They need secrets management for deployment credentials

## Context Required

From `startup-context`: tech stack, deployment target (cloud provider, platform), team size. Also detect or ask:
- What is the project language and framework? (auto-detect from repo)
- Where is it deployed? (Vercel, AWS, GCP, Fly.io, bare metal, etc.)
- What CI/CD platform? (GitHub Actions, GitLab CI, CircleCI — default to GitHub Actions)
- What environments exist? (dev, staging, production)
- What tests exist? (unit, integration, e2e, none yet)
- Are there secrets needed for build or deploy? (API keys, cloud credentials)

## Workflow

1. **Detect tech stack** — Scan repo for package.json, requirements.txt, go.mod, Cargo.toml, etc. Note the test runner, linter, and build tool.
2. **Choose pipeline stages** — Lint, Test (with coverage), Build, Security scan, Deploy.
3. **Generate pipeline config** — Write CI config (default: `.github/workflows/ci.yml`) with caching, test matrix if needed, and environment-specific deploy jobs.
4. **Configure secrets** — List required secrets and how to add them. Never hardcode.
5. **Add deployment stages** — Staging (auto on `main` merge) and production (manual approval or tag-based).
6. **Optimize** — Dependency caching, parallel jobs, conditional steps, path filters.
7. **Deliver config and instructions** — Full config file and setup steps.

## Output Format

```markdown
# CI/CD Pipeline: [Project Name]

## Pipeline Overview
(Mermaid flowchart showing stages)

## Pipeline Configuration
(Full YAML config file)

## Secrets Required
| Secret Name | Where to Get It | How to Add |
|-------------|----------------|------------|

## Setup Instructions
1. Step-by-step to activate the pipeline

## Optimization Notes
- Caching strategy explanation
- Estimated build time
```

## Frameworks & Best Practices

### GitHub Actions Config Patterns

**Caching strategies by ecosystem:**

| Ecosystem | Cache Path | Cache Key |
|-----------|-----------|-----------|
| Node.js | `~/.npm` or `node_modules` | `hashFiles('**/package-lock.json')` |
| Python | `~/.cache/pip` | `hashFiles('**/requirements*.txt')` |
| Go | `~/go/pkg/mod` | `hashFiles('**/go.sum')` |
| Rust | `~/.cargo/registry`, `target/` | `hashFiles('**/Cargo.lock')` |
| Ruby | `vendor/bundle` | `hashFiles('**/Gemfile.lock')` |

### Pipeline Best Practices

- **Lint first** — fast feedback, fail early before expensive test runs
- **Run tests in parallel** — split unit and integration tests into separate jobs
- **Cache aggressively** — dependency caching cuts 30-60% off build times
- **Pin action versions** — use SHA hashes not tags for supply chain security
- **Set timeouts** — prevent hung jobs: `timeout-minutes: 15`
- **Use matrix builds** — only when you support multiple runtimes
- **Use `concurrency` settings** — prevent overlapping deploys

### Environment Strategy

| Environment | Trigger | Approval | Purpose |
|-------------|---------|----------|---------|
| **CI** | Every push/PR | None | Run lint + tests |
| **Staging** | Merge to `main` | None (auto) | Integration testing, QA |
| **Production** | Git tag or manual | Required | Live users |

### Secrets Management

- Never commit secrets to the repository; use environment-level secrets
- Use OIDC for cloud auth instead of long-lived keys when possible
- Rotate secrets every 90 days minimum

### Security Scanning in CI

- **All projects:** `trivy` for container/dependency scanning, `semgrep` for SAST
- **Node.js:** `npm audit`; **Python:** `pip-audit`, `bandit`; **Go:** `govulncheck`

## Related Skills

- `code-review` — chain to review the CI config itself before committing
- `security-review` — chain to add or audit security scanning stages in the pipeline

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
  security:
    runs-on: ubuntu-latest
    timeout-minutes: 10
    steps:
      - uses: actions/checkout@v4
      - run: npm audit --audit-level=high
```

**Example prompt:** "My Python CI build takes 8 minutes, how do I speed it up?"

**Good output snippet:**
```
Three fixes to cut build time to ~3 minutes:
1. **Add pip caching** — cache `~/.cache/pip` keyed on
   `hashFiles('requirements*.txt')`. Saves ~90s.
2. **Split test jobs** — Run unit and integration tests in parallel.
3. **Add path filters** — Skip CI on docs-only changes with
   `paths-ignore: ['docs/**', '*.md']`.
```
