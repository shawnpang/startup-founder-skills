# Startup Founder Skills for AI Agents

A collection of AI agent skills for tech startup founders. Inspired by [Marketing Skills](https://github.com/coreyhaines31/marketingskills) by Corey Haines — extended from marketing to the full founder stack: fundraising, sales, product, recruiting, engineering, legal, finance, and growth. Works with Claude Code, OpenAI Codex, Cursor, Windsurf, and any agent that supports the [Agent Skills spec](https://agentskills.io).

**Contributions welcome!** Found a way to improve a skill or have a new one to add? [Open a PR](#contributing).

## Who Is This For?

- **Solo technical founders** building an MVP who also need to fundraise, sell, hire, and market — without a team to delegate to
- **First-time founders** who know how to code but haven't written a pitch deck, cold email, or job description before
- **Small founding teams (2-3 people)** wearing multiple hats and needing to move fast across every function
- **Technical co-founders** who handle product and engineering but now need to step into sales, recruiting, or investor conversations

If you're at a company with a VP of Sales, a Head of Marketing, and in-house counsel — you probably don't need this. These skills are for founders who *are* the sales team, the marketing team, and the legal team, all at once.

## What are Skills?

Skills are markdown files that give AI agents specialized knowledge and workflows for specific tasks. When you add these to your project, your agent can recognize what you're working on and apply the right frameworks, templates, and best practices — so you get founder-grade output, not generic AI slop.

## How These Skills Were Built

Each skill is based on the best open-source skill we could find for that task — from authors like [Pawel Huryn](https://github.com/phuryn/pm-skills), [Alireza Rezvani](https://github.com/alirezarezvani/claude-skills), [Corey Haines](https://github.com/coreyhaines31/marketingskills), [Jeff Allan](https://github.com/Jeffallan/claude-skills), and others. We read the original SKILL.md, extracted the core frameworks and workflows, and adapted them into a consistent format tailored for startup founders.

In some cases, multiple skills from a source were merged into one. For example, our `soc2-prep` draws from a broader CISO advisor skill, our `lead-scoring` combines ICP definition with pipeline qualification, and our `sales-script` merges demo scripting with RFP analysis and competitive positioning. The goal is one skill per founder task, not one skill per original repo.

Every attributed skill was [verified against its source](/README.md#acknowledgments) — the Author column in the table below links directly to the original skill each one is based on.

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
| Skill | Confidence | Author | Description |
|-------|------------|--------|-------------|
| [startup-context](skills/startup-context/) | — | Shawn Pang | Foundation skill read by all others. Captures your company stage, product, market, team, metrics, and goals so every skill produces tailored output. |
| | | | |
| **Fundraising** | | | |
| [pitch-deck](skills/pitch-deck/) | Medium | Shawn Pang | Create or refine pitch deck content — slide-by-slide narrative, not just bullet points. Narrative and story still need your voice. |
| [investor-research](skills/investor-research/) | High | Shawn Pang | Identify, qualify, and prioritize potential investors by stage, sector, check size, and portfolio fit. |
| [data-room](skills/data-room/) | High | Shawn Pang | Prepare due diligence materials — checklists, document organization, and drafts for missing items. |
| [fundraising-email](skills/fundraising-email/) | High | Shawn Pang | Write investor outreach — cold intros, warm follow-ups, update emails, and thank-you notes. |
| [accelerator-application](skills/accelerator-application/) | High | Shawn Pang | Apply to YC, Techstars, and other accelerators — includes directory of top US programs, application drafts, and interview prep. |
| | | | |
| **Sales & BD** | | | |
| [cold-outreach](skills/cold-outreach/) | High | [Brian Wagner](https://github.com/BrianRWagner/ai-marketing-claude-code-skills/tree/main/cold-outreach-sequence) | Write cold emails, LinkedIn messages, and follow-up sequences for B2B prospecting. Adapted from cold-outreach-sequence skill. |
| [sales-script](skills/sales-script/) | Medium | [Alireza Rezvani](https://github.com/alirezarezvani/claude-skills/tree/main/business-growth/sales-engineer) | Demo scripts, discovery call frameworks, objection handling docs, and closing playbooks. Adapted from sales-engineer skill. |
| [proposal-generation](skills/proposal-generation/) | Medium | [Alireza Rezvani](https://github.com/alirezarezvani/claude-skills/tree/main/business-growth/contract-and-proposal-writer) | Create sales proposals, SOWs, and pricing quotes. Adapted from contract-and-proposal-writer skill. |
| [lead-scoring](skills/lead-scoring/) | Medium | [Athina AI](https://github.com/athina-ai/goose-skills/tree/main/skills/composites/inbound-lead-qualification) | Define ICP criteria, lead qualification frameworks, and scoring models. Adapted from inbound-lead-qualification skill. |
| [partnership-outreach](skills/partnership-outreach/) | High | Shawn Pang | Write partnership proposals, integration pitches, and co-marketing outreach. |
| | | | |
| **Product & Strategy** | | | |
| [prd-writing](skills/prd-writing/) | Medium | [Pawel Huryn](https://github.com/phuryn/pm-skills/tree/main/pm-execution/skills/create-prd) | Write product requirements documents, feature specs, and user story sets. Adapted from create-prd skill. |
| [user-research-synthesis](skills/user-research-synthesis/) | Medium | [Pawel Huryn](https://github.com/phuryn/pm-skills/tree/main/pm-product-discovery/skills/summarize-interview) | Synthesize customer interviews, survey data, and support tickets into insights and personas. Adapted from summarize-interview skill. |
| [roadmap-planning](skills/roadmap-planning/) | Medium | [Pawel Huryn](https://github.com/phuryn/pm-skills/tree/main/pm-execution/skills/outcome-roadmap) | Build or update a product roadmap with timeline views, dependencies, and milestones. Adapted from outcome-roadmap skill. |
| [mvp-scoping](skills/mvp-scoping/) | Medium | Shawn Pang | Define MVP scope — what to build, what to cut, and what to defer. |
| [competitive-analysis](skills/competitive-analysis/) | High | [Pawel Huryn](https://github.com/phuryn/pm-skills/tree/main/pm-market-research/skills/competitor-analysis) | Research competitors — feature comparison, positioning analysis, pricing benchmarks, and market mapping. Adapted from competitor-analysis skill. |
| [market-research](skills/market-research/) | Medium | [Pawel Huryn](https://github.com/phuryn/pm-skills/tree/main/pm-market-research/skills/market-sizing) | Size a market (TAM/SAM/SOM), identify trends, and validate market hypotheses. Adapted from market-sizing skill. |
| [review-mining](skills/review-mining/) | High | Shawn Pang | Mine Trustpilot, G2, Capterra, and app store reviews to extract user pain points, switching triggers, and voice-of-customer language. |
| [daily-product-digest](skills/daily-product-digest/) | High | Shawn Pang | Summarize what's trending on Product Hunt, Hacker News, and Indie Hackers — filtered for relevance to your market. |
| [competitor-monitoring](skills/competitor-monitoring/) | High | Shawn Pang | Ongoing tracking of competitor pricing, features, hiring, and positioning changes — weekly intel briefs with threat levels. |
| | | | |
| **Recruiting & Team** | | | |
| [job-description](skills/job-description/) | High | Shawn Pang | Write compelling job descriptions that attract top candidates without corporate jargon. |
| [interview-kit](skills/interview-kit/) | High | [Alireza Rezvani](https://github.com/alirezarezvani/claude-skills/tree/main/engineering/interview-system-designer) | Design interview processes — questions, scorecards, take-home assignments, evaluation rubrics, and comp benchmarking. Adapted from interview-system-designer skill. |
| [sourcing-outreach](skills/sourcing-outreach/) | High | Shawn Pang | Write recruiting outreach — LinkedIn inmails, cold emails to candidates, and referral requests. |
| [employer-brand](skills/employer-brand/) | Medium | Shawn Pang | Build employer branding — careers page copy, team culture docs, and engineering blog posts. |
| | | | |
| **Engineering** | | | |
| [architecture-design](skills/architecture-design/) | Medium | [Alireza Rezvani](https://github.com/alirezarezvani/claude-skills/tree/main/engineering-team/senior-architect) | Design system architecture — service boundaries, data models, API design, and infrastructure planning. Adapted from senior-architect skill. |
| [code-review](skills/code-review/) | High | [Jeff Allan](https://github.com/Jeffallan/claude-skills/tree/main/skills/code-reviewer) | Thorough code review focused on correctness, security, performance, and maintainability. Adapted from code-reviewer skill. |
| [cicd-setup](skills/cicd-setup/) | High | [Alireza Rezvani](https://github.com/alirezarezvani/claude-skills/tree/main/engineering/ci-cd-pipeline-builder) | Set up or improve CI/CD pipelines — GitHub Actions, testing, deployment, and release automation. Adapted from ci-cd-pipeline-builder skill. |
| [tech-stack-eval](skills/tech-stack-eval/) | Medium | [Alireza Rezvani](https://github.com/alirezarezvani/claude-skills/tree/main/engineering-team/tech-stack-evaluator) | Evaluate and select technologies — frameworks, databases, hosting, and third-party services. Adapted from tech-stack-evaluator skill. |
| [security-review](skills/security-review/) | High | [Jeff Allan](https://github.com/Jeffallan/claude-skills/tree/main/skills/security-reviewer) | Audit security — OWASP top 10, auth flows, data handling, and dependency vulnerabilities. Adapted from security-reviewer skill. |
| | | | |
| **Legal & Compliance** | | | |
| [privacy-policy](skills/privacy-policy/) | High | [Pawel Huryn](https://github.com/phuryn/pm-skills/tree/main/pm-toolkit/skills/privacy-policy) | Generate or update a privacy policy, cookie policy, or data processing documentation. Adapted from privacy-policy skill. **Not a substitute for legal counsel.** |
| [terms-of-service](skills/terms-of-service/) | High | Shawn Pang | Draft or update terms of service, acceptable use policies, or SaaS agreements. **Not a substitute for legal counsel.** |
| [contract-review](skills/contract-review/) | Medium | Shawn Pang | Review contracts and flag risks — vendor agreements, partnership deals, or customer contracts. Good for spotting issues, lawyer signs off. |
| [soc2-prep](skills/soc2-prep/) | Medium | [Alireza Rezvani](https://github.com/alirezarezvani/claude-skills/tree/main/c-level-advisor/ciso-advisor) | Prepare for SOC 2 compliance — policy templates, control mapping, and evidence collection checklists. Adapted from ciso-advisor skill. |
| | | | |
| **Operations** | | | |
| [process-docs](skills/process-docs/) | High | Shawn Pang | Document processes, create SOPs, and build internal playbooks and runbooks. |
| [board-update](skills/board-update/) | Medium | [Alireza Rezvani](https://github.com/alirezarezvani/claude-skills/tree/main/c-level-advisor/board-deck-builder) | Write investor updates, board decks, and monthly/quarterly reports. Adapted from board-deck-builder skill. |
| | | | |
| **Customer Success** | | | |
| [onboarding-flow](skills/onboarding-flow/) | Medium | [Manoj Bajaj](https://github.com/manojbajaj95/claude-gtm-plugin/tree/main/plugins/growth/skills/user-onboarding) | Design or optimize user onboarding — activation flows, welcome sequences, and time-to-value optimization. Adapted from user-onboarding skill. |
| [support-docs](skills/support-docs/) | High | Shawn Pang | Create help center articles, FAQs, troubleshooting guides, and API documentation. |
| [feedback-synthesis](skills/feedback-synthesis/) | Medium | [Pawel Huryn](https://github.com/phuryn/pm-skills/tree/main/pm-product-discovery/skills/analyze-feature-requests) | Analyze customer feedback — categorize themes, identify patterns, and prioritize action items. Adapted from analyze-feature-requests skill. |
| [churn-analysis](skills/churn-analysis/) | Medium | [Athina AI](https://github.com/athina-ai/goose-skills/tree/main/skills/composites/churn-risk-detector) | Analyze churn — identify drivers, design retention experiments, and create win-back campaigns. Adapted from churn-risk-detector skill. |
| [sentiment-monitoring](skills/sentiment-monitoring/) | High | Shawn Pang | Monitor your own product's reviews and mentions across Product Hunt, G2, Trustpilot, Google Maps, and app stores — with response drafts and pattern detection. |
| | | | |
| **Marketing & Growth** | | | |
| [landing-page](skills/landing-page/) | High | [Corey Haines](https://github.com/coreyhaines31/marketingskills/tree/main/skills/page-cro) | Build or optimize a landing page — copy, layout, CTAs, and conversion optimization. Adapted from page-cro skill. |
| [content-strategy](skills/content-strategy/) | High | [Corey Haines](https://github.com/coreyhaines31/marketingskills/tree/main/skills/content-strategy) | Plan content — blog strategy, SEO content calendars, thought leadership, and documentation. Adapted from content-strategy skill. |
| [seo-technical](skills/seo-technical/) | High | [Daniel Agrici](https://github.com/AgriciDaniel/claude-seo/tree/main/skills/seo-technical) | Audit or improve technical SEO — site structure, meta tags, schema markup, and Core Web Vitals. Adapted from seo-technical skill. |
| [email-marketing](skills/email-marketing/) | High | [Corey Haines](https://github.com/coreyhaines31/marketingskills/tree/main/skills/email-sequence) | Create email campaigns — newsletters, drip sequences, lifecycle emails, and re-engagement flows. Adapted from email-sequence skill. |
| [social-content](skills/social-content/) | High | [Brian Wagner](https://github.com/BrianRWagner/ai-marketing-claude-code-skills/tree/main/linkedin-authority-builder) | Create social media content — LinkedIn posts, Twitter/X threads, and content repurposing. Adapted from linkedin-authority-builder skill. |
| [launch-strategy](skills/launch-strategy/) | Medium | [Daniel Mendes](https://github.com/dmend3z/tribo-skills/tree/main/plugins/product-launch-marketing) | Plan a product launch — Product Hunt, Hacker News, press outreach, and community seeding. Adapted from product-launch-marketing skill. |
| [founder-thought-leadership](skills/founder-thought-leadership/) | High | Shawn Pang | Build founder IP and personal brand on X and LinkedIn — original frameworks, contrarian takes, and building in public. |
| [community-discovery](skills/community-discovery/) | High | Shawn Pang | Find relevant Slack, Discord, Reddit, and forum communities where your target customers hang out — with engagement strategies. |
| [event-hosting](skills/event-hosting/) | High | Shawn Pang | Plan and promote tech events, meetups, and workshops on Luma — event page copy, run of show, promotion plan, and follow-up. |
| [earned-media-outreach](skills/earned-media-outreach/) | High | Shawn Pang | Find podcasts, journalists, and newsletter writers to get earned media exposure — pitches, target lists, and appearance prep. |
<!-- SKILLS:END -->

## Installation

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
- `accelerator-application` - Apply to YC, Techstars, and top US accelerators

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
- `review-mining` - Extract pain points from Trustpilot, G2, and app store reviews
- `daily-product-digest` - Summarize trending launches on Product Hunt and Hacker News
- `competitor-monitoring` - Ongoing tracking of competitor changes and strategic signals

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
- `sentiment-monitoring` - Monitor your product's reviews and public mentions

### Marketing & Growth
- `landing-page` - Copy, layout, and conversion
- `content-strategy` - Blog, SEO, and thought leadership
- `seo-technical` - Technical SEO and site structure
- `email-marketing` - Campaigns and lifecycle emails
- `social-content` - LinkedIn, Twitter/X content
- `launch-strategy` - Product Hunt, HN, and press launches
- `founder-thought-leadership` - Build founder IP and personal brand on X and LinkedIn
- `community-discovery` - Find and engage Slack, Discord, Reddit communities for distribution
- `event-hosting` - Plan and promote tech events and meetups on Luma
- `earned-media-outreach` - Get on podcasts and earn press coverage

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

This project builds on the work of many open-source skill authors:

- [Corey Haines](https://github.com/coreyhaines31/marketingskills) — Marketing Skills for AI Agents, the project that inspired this repo
- [Alireza Rezvani](https://github.com/alirezarezvani/claude-skills) — Engineering, architecture, CI/CD, sales, and compliance skills
- [Pawel Huryn](https://github.com/phuryn/pm-skills) — Product management skills (PRDs, roadmaps, research, privacy)
- [Jeff Allan](https://github.com/Jeffallan/claude-skills) — Code review and security review skills
- [Brian Wagner](https://github.com/BrianRWagner/ai-marketing-claude-code-skills) — Cold outreach and social content skills
- [Athina AI](https://github.com/athina-ai/goose-skills) — Lead scoring and churn analysis skills
- [Daniel Agrici](https://github.com/AgriciDaniel/claude-seo) — Technical SEO skills
- [Daniel Mendes](https://github.com/dmend3z/tribo-skills) — Launch strategy and marketing skills
- [Manoj Bajaj](https://github.com/manojbajaj95/claude-gtm-plugin) — Onboarding and GTM skills
