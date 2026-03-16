---
name: employer-brand
description: When the user needs to create or improve content that shapes how candidates and the public perceive the company as a place to work.
related: [job-description, content-strategy]
reads: [startup-context]
---

# Employer Brand

## When to Use
Activate when the user asks to write careers page copy, create a culture document, draft an engineering blog post, build "day in the life" content, document company values, or generally improve how the company presents itself to prospective hires. Also activate when the user is struggling to differentiate their startup from competitors in the talent market.

## Context Required
- **From startup-context:** Company name, mission, stage, team size, founding story, values (stated or practiced), remote/hybrid/onsite policy, notable perks, and any existing brand voice guidelines.
- **From user:** The specific content type needed, target audience (engineers, designers, go-to-market, general), existing content to build on (if any), and what makes the company genuinely distinctive as a workplace.

## Workflow
1. **Identify the authentic story** — Ask the user what is genuinely true and distinctive about working at this company. Employer brand must be rooted in reality or it backfires at onboarding. Probe for specific stories, rituals, and decisions that reveal culture.
2. **Choose the content format** — Select from: careers page, values document, engineering blog post, "day in the life" feature, team spotlight, hiring process transparency post, or culture deck.
3. **Draft the content** — Write using the Voice-Evidence-Proof framework (see below). Lead with what candidates care about (impact, growth, people, flexibility), not what the company cares about (mission statements in a vacuum).
4. **Ground every claim in evidence** — For each cultural claim, attach a specific example, policy, or anecdote. "We value work-life balance" becomes "We have no meetings on Wednesdays and our average team member works 42 hours/week."
5. **Calibrate the tone** — Match the company's actual communication style. A developer tools startup sounds different from a healthcare company. Avoid generic startup voice.
6. **Review for authenticity** — Flag any claims that feel aspirational rather than current. Mark those explicitly or remove them. Candidates trust specificity and distrust superlatives.

## Output Format
The deliverable depends on the content type:
- **Careers page:** Full page copy in markdown, section by section, ready for a designer to lay out.
- **Values document:** 4-6 values with definitions, behavioral examples, and counter-examples.
- **Blog post:** A complete draft with headline, intro, body sections, and closing CTA.
- **Day in the life:** A narrative feature with time stamps, quotes, and concrete details.
- **Culture deck:** Slide-by-slide content outline with speaker notes.

## Frameworks & Best Practices

### The Voice-Evidence-Proof (VEP) Framework
Every employer brand claim needs three layers:
- **Voice:** The claim stated in the company's natural tone. ("We ship fast and learn faster.")
- **Evidence:** A concrete policy, practice, or structure that supports the claim. ("Our deploy pipeline runs 40+ times per day. Every engineer ships to production in their first week.")
- **Proof:** A real story or data point that makes it undeniable. ("Last quarter, a new hire identified a UX issue on day 3 and had the fix live by day 5 — no approval chain needed.")

### Careers Page Structure
A high-converting careers page follows this arc:
1. **Hero section:** A bold statement about what working here means. Not the company mission — the employee promise. (e.g., "Build the future of [X] with people who actually care about the craft.")
2. **Why here:** 3-4 tiles or sections covering the top reasons candidates join. Use the candidate's language: impact, ownership, growth, people, flexibility.
3. **How we work:** Concrete details about rituals, tools, and cadences. Remote practices, meeting culture, shipping rhythm.
4. **Team spotlight:** Photos, quotes, and short bios of real team members. Diverse representation matters.
5. **What we offer:** Comp philosophy, benefits, equity, and learning budget — in specific terms, not vague promises.
6. **Open roles:** Live job listings with clear titles and locations.
7. **Application process:** What candidates can expect step-by-step with timeline estimates.

### Values Documentation Framework
Strong values have four properties:
- **Specific:** "Default to transparency" is better than "Integrity."
- **Opinionated:** A real value implies a trade-off. If no reasonable company would disagree, it's not a value — it's a platitude.
- **Behavioral:** Each value should connect to observable actions. Define "what this looks like" and "what this does NOT look like."
- **Prioritized:** When two values conflict, which one wins? Documenting this makes values real.

Example:
```
## Ship and Iterate
We choose progress over perfection. We'd rather learn from a live
feature than debate a hypothetical one.

What this looks like:
- Shipping an MVP to 10 customers before building the "full" version
- Writing a quick RFC instead of scheduling a meeting
- Celebrating a launched experiment that failed, because we learned

What this does NOT look like:
- Shipping broken code that erodes customer trust
- Skipping testing because "we move fast"
- Ignoring feedback because "we already shipped it"
```

### Engineering Blog Post Framework
Engineering blog posts serve dual duty as employer brand and thought leadership.
1. **Start with the problem** — Technical readers want to know the challenge before the solution.
2. **Show the constraints** — What made this problem hard at your scale, stage, or domain?
3. **Walk through the decision** — Show the trade-offs and alternatives you considered, not just the final choice.
4. **Be honest about what didn't work** — Vulnerability builds trust. "Our first approach failed because..." is more compelling than a clean narrative.
5. **End with what's next** — Open loops invite follow-up conversations and signal that interesting work continues.

### "Day in the Life" Content Structure
- **Format:** First-person narrative or interviewer-led Q&A, structured around a real or representative day.
- **Include:** Specific tools, meetings (or lack thereof), lunch habits, collaboration moments, and a real challenge they worked through.
- **Avoid:** Sanitized, marketing-approved-sounding quotes. Let personality come through.
- **Diversity:** Feature team members across roles, levels, and backgrounds.

### Anti-Patterns to Avoid
- **The aspiration trap:** Writing about the culture you want instead of the culture you have. Candidates who join based on aspiration churn fast.
- **Superlative overload:** "World-class team, cutting-edge technology, incredible culture." These words mean nothing without evidence.
- **Perks over substance:** Leading with the ping-pong table, free lunch, or unlimited PTO instead of meaningful work, good management, and career growth.
- **Copying big tech:** Your startup is not Google. Don't mimic their tone, perks list, or values format. Lean into what makes you different.
- **Stock photo culture:** Use real photos of real team members or none at all. Staged stock photos actively hurt trust.

## Related Skills
- `job-description` — Every JD is an employer brand touchpoint. Ensure JD voice matches the careers page.
- `content-strategy` — Employer brand content (blog posts, social) should integrate into the broader content calendar and distribution plan.

## Examples

**Prompt:** "Write careers page copy for our developer tools startup. We're 20 people, Series A, remote-first."

**Good output snippet:**
```
# Build tools that developers actually love

We're a team of 20 building [product] — and we're looking for people
who care about developer experience as much as we do.

## Why engineers join us

**You'll ship to thousands of developers weekly.** Our CLI has 50K+
monthly active users. The feature you build on Monday gets feedback
in Slack by Thursday.

**You'll own entire systems.** We don't have ticket jockeys. Each
engineer owns a domain — from design through production monitoring.
Your last PR won't need four approvals to merge.

**You'll work with people who write well.** We're remote-first and
async-heavy. That means clear writing, thoughtful RFCs, and Loom
videos instead of status meetings.
```

**Prompt:** "Help us write our company values. We keep saying we have them but haven't documented anything."

**Good output snippet:**
```
Let's start by identifying what's actually true about how you operate
today — not what sounds good on a poster. I'll ask a few questions:

1. When your team disagrees on a decision, how does it get resolved?
2. What behavior have you praised in the last month?
3. What's something your team does that an outsider might find unusual?
4. When has the team made a hard trade-off, and which side did you land on?

Your answers will reveal the real values. Then we'll name them, define
them with behavioral examples, and pressure-test them with counter-
examples to make sure they're genuinely opinionated.
```
