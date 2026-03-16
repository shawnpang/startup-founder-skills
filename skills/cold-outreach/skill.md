---
name: cold-outreach
trigger: When a founder needs to write cold emails or LinkedIn messages to prospects, partners, or investors. Activate when the user mentions cold email, outbound, prospecting, LinkedIn outreach, or needs help getting replies from people who don't know them.
related: [lead-scoring, sales-script]
reads: [startup-context]
---

# Cold Outreach

## When to Use
Activate when a founder needs to write cold emails or cold LinkedIn messages to prospects, potential customers, investors, or strategic contacts. Also use when the user says "nobody replies to my emails," "how do I reach out to X," "write me a cold email," or "help with outbound."

## Context Required
From `startup-context` or the user:
- **Target recipient** — Role, company, why them specifically
- **Desired outcome** — Meeting, reply, intro, demo, investment conversation
- **Value proposition** — The specific problem you solve for people like them
- **Proof points** — Results, traction, case studies, credibility signals
- **Research signals** — Funding rounds, hiring posts, LinkedIn activity, product launches, tech stack changes

Work with whatever the user provides. A strong signal and clear value prop is enough to write. Note what would strengthen the message but do not block on missing inputs.

## Workflow
1. **Gather context** — Read startup-context if available. Ask for missing info on target, value prop, and proof points.
2. **Research the recipient** — Identify a personalization hook: something they said, did, or published that connects to the problem you solve.
3. **Select channel and framework** — Choose email, LinkedIn, or both. Pick a structure that fits the situation (see Frameworks below).
4. **Draft the message** — Write the outreach following the principles below. Keep emails under 125 words. Keep LinkedIn messages under 300 characters for connection requests, under 500 characters for InMails.
5. **Write follow-up sequence** — Draft 3-4 follow-ups for email, each adding a new angle. For LinkedIn, draft 2-3 follow-ups.
6. **Quality check** — Read aloud. Verify it sounds human, has one clear ask, and the personalization connects to the problem.

## Output Format
Deliver all of the following:
- **Subject line** (email) or **connection note** (LinkedIn) — short, lowercase, no gimmicks
- **Primary message** — the full outreach text
- **Follow-up sequence** — 3-4 follow-ups with suggested timing and a new angle per touch
- **Personalization notes** — what to customize per recipient if sending to multiple people

## Frameworks & Best Practices

### Core Writing Principles
- **Write like a peer, not a vendor.** The message should read like it came from someone who understands their world. Use contractions. If it sounds like marketing copy, rewrite it.
- **Every sentence must earn its place.** If a sentence does not move the reader toward replying, cut it.
- **Personalization must connect to the problem.** If you remove the personalized opening and the email still makes sense, the personalization is not working.
- **Lead with their world, not yours.** "You/your" should dominate over "I/we." Do not open with who you are or what your company does.
- **One ask, low friction.** Interest-based CTAs ("Worth exploring?" / "Would this be useful?") beat meeting requests. One CTA per message.

### Email Frameworks
- **Observation-Problem-Proof-Ask** — You noticed X, which usually means Y challenge. We helped Z with that. Interested?
- **Question-Value-Ask** — Struggling with X? We do Y. Company Z saw [result]. Worth a look?
- **Trigger-Insight-Ask** — Congrats on X. That usually creates Y challenge. We have helped similar companies. Curious?
- **Story-Bridge-Ask** — [Similar company] had [problem]. They [solved it this way]. Relevant to you?

### LinkedIn-Specific Rules
- **Connection requests** — Keep under 300 characters. Reference something specific (mutual connection, shared experience, their content). Do not pitch in the connection request.
- **First message after connecting** — Wait 1-2 days. Reference why you connected. Offer value before asking for anything.
- **InMail** — Treat like a cold email but shorter. LinkedIn InMails with under 400 characters get 22% higher response rates.
- **Engage before reaching out** — Comment thoughtfully on 2-3 of their posts before sending a connection request. This warms the outreach significantly.

### Subject Lines (Email)
- 2-4 words, lowercase, no punctuation tricks
- Should look like an internal email ("quick question," "re: [their company]," "idea for [problem area]")
- No product pitches, no urgency, no emojis, no first-name personalization

### Follow-Up Cadence
| Touch | Email Timing | LinkedIn Timing | Angle |
|-------|-------------|-----------------|-------|
| 1 | Day 0 | Day 0 | Primary value prop |
| 2 | Day 3 | Day 4 | New proof point or case study |
| 3 | Day 7 | Day 8 | Different angle on the problem |
| 4 | Day 14 | Day 14 | Breakup — "closing the loop" |

Each follow-up must add something new. "Just checking in" gives the reader no reason to respond.

### Founder-Specific Advantages
As a founder, you have unique outreach advantages over SDRs and sales reps:
- **Founder-to-founder** or **founder-to-exec** emails get 2-3x higher reply rates than rep emails
- Lead with your story and why you built the company — authenticity is your edge
- You can offer things reps cannot: personal onboarding, product roadmap input, advisory relationships
- Use "I built this because..." framing — it is more compelling than "our company offers..."

### What to Avoid
- Opening with "I hope this finds you well" or "My name is X and I work at Y"
- Jargon: "synergy," "leverage," "best-in-class," "leading provider"
- Feature dumps — one proof point beats ten features
- HTML formatting, images, or multiple links in cold emails
- Fake "Re:" or "Fwd:" subject lines
- Asking for 30-minute calls in first touch
- Sending identical templates with only the name swapped
- Pitching in a LinkedIn connection request

## Related Skills
- `lead-scoring` — use to prioritize which prospects to reach out to first
- `sales-script` — use when the outreach lands a meeting and you need a discovery call or demo script

## Examples

**Example prompt:** "I need to reach out to VP Engineering at mid-market SaaS companies about our API monitoring tool. We reduced downtime by 73% for Acme Corp."

**Good email output:**
> Subject: api alerts
>
> Hi [Name],
>
> Saw your team just shipped the new payments integration — nice work. Launches like that usually surface a wave of edge-case API failures that are tough to catch with standard monitoring.
>
> We built a tool that catches those failures before customers notice. Acme Corp cut their API downtime by 73% in the first month.
>
> Worth a quick look?

**Good LinkedIn connection request:**
> Hi [Name] — saw the payments launch. We help engineering teams catch API failures before customers do. Would love to connect.
