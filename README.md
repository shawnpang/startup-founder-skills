# Startup Founder Skills for AI Agents

A collection of AI agent skills for tech startup founders. Covers the full founder stack — fundraising, sales, product, recruiting, engineering, legal, finance, and growth. Works with Claude Code, OpenAI Codex, Cursor, Windsurf, and any agent that supports the [Agent Skills spec](https://agentskills.io).

Built by [Shawn Pang](https://github.com/shawnpang). Inspired by [Marketing Skills](https://github.com/coreyhaines31/marketingskills) by Corey Haines.

**Contributions welcome!** Found a way to improve a skill or have a new one to add? [Open a PR](#contributing).

## What are Skills?

Skills are markdown files that give AI agents specialized knowledge and workflows for specific tasks. When you add these to your project, your agent can recognize what you're working on and apply the right frameworks, templates, and best practices — so you get founder-grade output, not generic AI slop.

## How Well Does This Actually Work?

Not all founder tasks are equally automatable. We tier every skill by confidence level so you know what to trust and what to double-check.

| Tier | Meaning | What to expect |
|------|---------|----------------|
| **High** | Agent output is directly usable | Ship it after a quick skim. These are writing, research, and code tasks where AI consistently produces good results. |
| **Medium** | Good drafts, needs founder review | Saves 60-80% of the work, but you need to edit, validate, or add judgment before using. |

We intentionally excluded tasks where AI is unreliable — financial modeling, unit economics, pricing decisions, and OKR-setting. These require human judgment and verified numbers, not AI scaffolding. See [What Can and Can't Be Automated](#what-can-and-cant-be-automated) for details.

## How Skills Work Together

Every skill reads from `startup-context` first — your company's stage, product, market, team, and metrics. This shared context means skills produce output tailored to your specific startup, not generic advice.

```
                              ┌──────────────────────────────────────┐
                              │          startup-context             │
                              │    (read by all other skills first)  │
                              └──────────────────┬───────────────────┘
                                                 │
  ┌──────────────┬──────────────┬────────────────┼────────────────┬──────────────┬──────────────┐
  ▼              ▼              ▼                ▼                ▼              ▼              ▼
┌───────────┐ ┌───────────┐ ┌───────────┐ ┌────────────┐ ┌───────────┐ ┌────────────┐ ┌───────────┐
│Fundraising│ │ Sales &BD │ │ Product & │ │ Recruiting │ │Engineering│ │  Legal &   │ │ Marketing │
│           │ │           │ │ Strategy  │ │   & Team   │ │           │ │ Operations │ │ & Growth  │
├───────────┤ ├───────────┤ ├───────────┤ ├────────────┤ ├───────────┤ ├────────────┤ ├───────────┤
│pitch-deck │ │cold-      │ │prd-writng │ │job-desc    │ │arch-desgn │ │privacy-pol │ │landing-pg │
│inv-rsrch  │ │ outreach  │ │user-rsrch │ │interview   │ │code-revew │ │terms-of-sv │ │content    │
│data-room  │ │sales-scrpt│ │roadmap    │ │sourcing    │ │cicd-setup │ │contract-rv │ │seo        │
│fund-email │ │proposal   │ │mvp-scope  │ │employer-   │ │tech-stack │ │soc2-prep   │ │email-mktg │
│           │ │lead-score │ │comp-anlys │ │ brand      │ │security   │ │process-doc │ │social     │
│           │ │partner-   │ │mkt-rsrch  │ │            │ │           │ │board-update│ │launch     │
│           │ │ outreach  │ │           │ │            │ │           │ │            │ │           │
└─────┬─────┘ └─────┬─────┘ └─────┬─────┘ └──────┬─────┘ └─────┬─────┘ └──────┬─────┘ └─────┬─────┘
      │             │             │               │             │              │             │
      └─────────────┴──────┬──────┴───────────────┴─────────────┴──────────────┴─────────────┘
                           │
            Skills cross-reference each other:
              pitch-deck ↔ investor-research ↔ data-room
              cold-outreach ↔ lead-scoring ↔ sales-script
              prd-writing ↔ mvp-scoping ↔ roadmap-planning
              job-description ↔ interview-kit ↔ sourcing-outreach
```

See each skill's **Related Skills** section for the full dependency map.

## Available Skills

<!-- SKILLS:START -->
| Skill | Confidence | Description |
|-------|------------|-------------|
| [startup-context](skills/startup-context/) | — | Foundation skill read by all others. Captures your company stage, product, market, team, metrics, and goals so every skill produces tailored output. |
| | | |
| **Fundraising** | | |
| [pitch-deck](skills/pitch-deck/) | Medium | Create or refine pitch deck content — slide-by-slide narrative, not just bullet points. Narrative and story still need your voice. |
| [investor-research](skills/investor-research/) | High | Identify, qualify, and prioritize potential investors by stage, sector, check size, and portfolio fit. |
| [data-room](skills/data-room/) | High | Prepare due diligence materials — checklists, document organization, and drafts for missing items. |
| [fundraising-email](skills/fundraising-email/) | High | Write investor outreach — cold intros, warm follow-ups, update emails, and thank-you notes. |
| | | |
| **Sales & BD** | | |
| [cold-outreach](skills/cold-outreach/) | High | Write cold emails, LinkedIn messages, and follow-up sequences for B2B prospecting. Proven to increase volume 5x with better personalization. |
| [sales-script](skills/sales-script/) | Medium | Demo scripts, discovery call frameworks, objection handling docs, and closing playbooks. Good prep material, but live calls need human adaptation. |
| [proposal-generation](skills/proposal-generation/) | Medium | Create sales proposals, SOWs, and pricing quotes. Structure is solid, deal-specific nuance needs your input. |
| [lead-scoring](skills/lead-scoring/) | Medium | Define ICP criteria, lead qualification frameworks, and scoring models. Also covers pipeline stage design. |
| [partnership-outreach](skills/partnership-outreach/) | High | Write partnership proposals, integration pitches, and co-marketing outreach. |
| | | |
| **Product & Strategy** | | |
| [prd-writing](skills/prd-writing/) | Medium | Write product requirements documents, feature specs, and user story sets. Great first drafts, needs your product judgment. |
| [user-research-synthesis](skills/user-research-synthesis/) | Medium | Synthesize customer interviews, survey data, and support tickets into insights and personas. |
| [roadmap-planning](skills/roadmap-planning/) | Medium | Build or update a product roadmap with timeline views, dependencies, and milestones. |
| [mvp-scoping](skills/mvp-scoping/) | Medium | Define MVP scope — what to build, what to cut, and what to defer. |
| [competitive-analysis](skills/competitive-analysis/) | High | Research competitors — feature comparison, positioning analysis, pricing benchmarks, and market mapping. |
| [market-research](skills/market-research/) | Medium | Size a market (TAM/SAM/SOM), identify trends, and validate market hypotheses. Useful framework, verify data points. |
| | | |
| **Recruiting & Team** | | |
| [job-description](skills/job-description/) | High | Write compelling job descriptions that attract top candidates without corporate jargon. |
| [interview-kit](skills/interview-kit/) | High | Design interview processes — questions, scorecards, take-home assignments, evaluation rubrics, and comp benchmarking. |
| [sourcing-outreach](skills/sourcing-outreach/) | High | Write recruiting outreach — LinkedIn inmails, cold emails to candidates, and referral requests. |
| [employer-brand](skills/employer-brand/) | Medium | Build employer branding — careers page copy, team culture docs, and engineering blog posts. |
| | | |
| **Engineering** | | |
| [architecture-design](skills/architecture-design/) | Medium | Design system architecture — service boundaries, data models, API design, and infrastructure planning. |
| [code-review](skills/code-review/) | High | Thorough code review focused on correctness, security, performance, and maintainability. |
| [cicd-setup](skills/cicd-setup/) | High | Set up or improve CI/CD pipelines — GitHub Actions, testing, deployment, and release automation. |
| [tech-stack-eval](skills/tech-stack-eval/) | Medium | Evaluate and select technologies — frameworks, databases, hosting, and third-party services. |
| [security-review](skills/security-review/) | High | Audit security — OWASP top 10, auth flows, data handling, and dependency vulnerabilities. |
| | | |
| **Legal & Compliance** | | |
| [privacy-policy](skills/privacy-policy/) | High | Generate or update a privacy policy, cookie policy, or data processing documentation. **Not a substitute for legal counsel.** |
| [terms-of-service](skills/terms-of-service/) | High | Draft or update terms of service, acceptable use policies, or SaaS agreements. **Not a substitute for legal counsel.** |
| [contract-review](skills/contract-review/) | Medium | Review contracts and flag risks — vendor agreements, partnership deals, or customer contracts. Good for spotting issues, lawyer signs off. |
| [soc2-prep](skills/soc2-prep/) | Medium | Prepare for SOC 2 compliance — policy templates, control mapping, and evidence collection checklists. |
| | | |
| **Operations** | | |
| [process-docs](skills/process-docs/) | High | Document processes, create SOPs, and build internal playbooks and runbooks. |
| [board-update](skills/board-update/) | Medium | Write investor updates, board decks, and monthly/quarterly reports. Template and structure are great, substance must be real. |
| | | |
| **Customer Success** | | |
| [onboarding-flow](skills/onboarding-flow/) | Medium | Design or optimize user onboarding — activation flows, welcome sequences, and time-to-value optimization. |
| [support-docs](skills/support-docs/) | High | Create help center articles, FAQs, troubleshooting guides, and API documentation. |
| [feedback-synthesis](skills/feedback-synthesis/) | Medium | Analyze customer feedback — categorize themes, identify patterns, and prioritize action items. |
| [churn-analysis](skills/churn-analysis/) | Medium | Analyze churn — identify drivers, design retention experiments, and create win-back campaigns. |
| | | |
| **Marketing & Growth** | | |
| [landing-page](skills/landing-page/) | High | Build or optimize a landing page — copy, layout, CTAs, and conversion optimization. |
| [content-strategy](skills/content-strategy/) | High | Plan content — blog strategy, SEO content calendars, thought leadership, and documentation. |
| [seo-technical](skills/seo-technical/) | High | Audit or improve technical SEO — site structure, meta tags, schema markup, and Core Web Vitals. |
| [email-marketing](skills/email-marketing/) | High | Create email campaigns — newsletters, drip sequences, lifecycle emails, and re-engagement flows. |
| [social-content](skills/social-content/) | High | Create social media content — LinkedIn posts, Twitter/X threads, and content repurposing. |
| [launch-strategy](skills/launch-strategy/) | Medium | Plan a product launch — Product Hunt, Hacker News, press outreach, and community seeding. |
<!-- SKILLS:END -->

## Installation

### Option 1: CLI Install (Recommended)

```bash
# Install all skills
npx skills add shawnpang/startup-founder-skills

# Install specific skills
npx skills add shawnpang/startup-founder-skills --skill pitch-deck cold-outreach

# Install a category
npx skills add shawnpang/startup-founder-skills --skill fundraising

# List available skills
npx skills add shawnpang/startup-founder-skills --list
```

### Option 2: Clone and Copy

```bash
git clone https://github.com/shawnpang/startup-founder-skills.git
cp -r startup-founder-skills/skills/* .agents/skills/
```

### Option 3: Git Submodule

```bash
git submodule add https://github.com/shawnpang/startup-founder-skills.git .agents/startup-founder-skills
```

### Option 4: Fork and Customize

1. Fork this repository
2. Customize skills for your startup's specific needs
3. Clone your fork into your projects

## Usage

Once installed, just ask your agent to help with founder tasks:

```
"Help me write a pitch deck for our Series A"
→ Uses pitch-deck + investor-research skills

"Write a cold email to reach enterprise prospects"
→ Uses cold-outreach + lead-scoring skills

"Create a PRD for our new billing feature"
→ Uses prd-writing skill

"Help me write a job description for a senior engineer"
→ Uses job-description + employer-brand skills

"Review this contract from our vendor"
→ Uses contract-review skill

"Draft an investor update for this month"
→ Uses board-update skill
```

You can also invoke skills directly:

```
/pitch-deck
/cold-outreach
/prd-writing
/code-review
```

## Skill Categories

### Fundraising
- `pitch-deck` - Slide-by-slide deck content and narrative
- `investor-research` - Investor targeting and qualification
- `data-room` - Due diligence preparation
- `fundraising-email` - Investor outreach and updates

### Sales & BD
- `cold-outreach` - Prospecting emails and sequences
- `sales-script` - Demo and call frameworks
- `proposal-generation` - Proposals, SOWs, and quotes
- `lead-scoring` - ICP definition, qualification, and pipeline design
- `partnership-outreach` - BD and integration pitches

### Product & Strategy
- `prd-writing` - Product requirement documents
- `user-research-synthesis` - Interview and feedback analysis
- `roadmap-planning` - Timeline and milestone planning
- `mvp-scoping` - MVP definition and scope cutting
- `competitive-analysis` - Competitor research and positioning
- `market-research` - TAM/SAM/SOM and trend analysis

### Recruiting & Team
- `job-description` - Compelling job posts
- `interview-kit` - Questions, scorecards, rubrics, and comp benchmarking
- `sourcing-outreach` - Candidate outreach messages
- `employer-brand` - Careers page and culture content

### Engineering
- `architecture-design` - System and API design
- `code-review` - Security, performance, correctness review
- `cicd-setup` - Pipeline and deployment automation
- `tech-stack-eval` - Technology selection and tradeoffs
- `security-review` - OWASP, auth, and vulnerability audits

### Legal & Compliance
- `privacy-policy` - Privacy and data handling policies
- `terms-of-service` - ToS and SaaS agreements
- `contract-review` - Risk flagging in contracts
- `soc2-prep` - SOC 2 readiness and policy templates

### Operations
- `process-docs` - SOPs, playbooks, and runbooks
- `board-update` - Investor updates and board decks

### Customer Success
- `onboarding-flow` - Activation and time-to-value
- `support-docs` - Help center and API docs
- `feedback-synthesis` - Theme extraction from feedback
- `churn-analysis` - Retention analysis and win-back

### Marketing & Growth
- `landing-page` - Copy, layout, and conversion
- `content-strategy` - Blog, SEO, and thought leadership
- `seo-technical` - Technical SEO and site structure
- `email-marketing` - Campaigns and lifecycle emails
- `social-content` - LinkedIn, Twitter/X content
- `launch-strategy` - Product Hunt, HN, and press launches

## What Can and Can't Be Automated

### What AI agents do well

- **Writing at volume** — emails, docs, copy, posts, job descriptions, outreach sequences. This is the #1 proven use case. 82% of founders cite content generation as their top AI workflow.
- **Research and analysis** — competitor intel, market sizing, investor targeting, feedback synthesis. Cuts research time by 50-60%.
- **Code tasks** — review, CI/CD, architecture, security audits, technical SEO. The strongest overall category for coding agents.
- **Legal document drafts** — policies, terms, contracts. YC-backed startups are using AI for 8x faster contract review. Still need a lawyer for anything binding.

### What we intentionally left out

- **Financial modeling** — LLMs hallucinate historical data and can't reliably handle formula logic. An unauditable number is a useless number.
- **Unit economics / burn rate** — Same problem. Use a spreadsheet, not an AI agent.
- **Pricing decisions** — AI can research competitors' pricing, but setting your own price is a high-stakes strategic call.
- **OKR / goal-setting** — Structure is easy to template, but goals require your strategic vision. A framework without conviction is just busywork.
- **Feature prioritization** — RICE scores are only as good as the inputs. The founder who talks to customers daily will out-prioritize any scoring model.

### What requires a human, period

- **Investor meetings** — skills prep you, but you run the room
- **Hiring decisions** — skills write JDs and scorecards, but you pick the people
- **Legal sign-off** — skills draft policies and flag risks, but get a lawyer for anything binding
- **Live sales calls** — skills write your playbook, but objection handling is real-time judgment
- **Strategy** — skills give you research, but you make the bets

### The right mental model

Think of these skills as a **chief of staff that works at AI speed** — they draft, research, structure, and prepare. You review, decide, and ship. The founder who uses AI to write 10 cold emails in 5 minutes and personally reviews each one will outperform both the founder who writes 2 emails manually and the one who auto-sends 100 unreviewed AI emails.

## Contributing

Found a way to improve a skill? Have a new skill to suggest? PRs and issues welcome!

### Adding a New Skill

1. Create a new directory under `skills/` with a kebab-case name
2. Add a `skill.md` file following the template in [CONTRIBUTING.md](CONTRIBUTING.md)
3. Include: trigger conditions, workflow steps, output format, and related skills
4. Update the skills table in this README
5. Open a PR

## License

[MIT](LICENSE) — Use these however you want.

## Acknowledgments

Inspired by [Marketing Skills for AI Agents](https://github.com/coreyhaines31/marketingskills) by Corey Haines.
