---
name: sales-script
trigger: When a founder needs demo scripts, discovery call frameworks, objection handling documents, or closing playbooks. Activate when the user mentions sales calls, demo prep, objection handling, talk tracks, or closing deals.
related: [cold-outreach, proposal-generation]
reads: [startup-context]
---

# Sales Script

## When to Use
Activate when a founder needs to prepare for sales conversations: discovery calls, product demos, objection handling, or closing meetings. Also use when the user says "I have a demo tomorrow," "how do I handle this objection," "write me a talk track," or "help me close this deal."

## Context Required
From `startup-context` or the user:
- **Product/service** — What you sell and who it is for
- **Target persona** — Role, seniority, typical pain points
- **Sales motion** — Founder-led, inside sales, or product-led
- **Deal context** — Stage, deal size, stakeholders involved, known objections
- **Differentiators** — What makes you different from the next best alternative
- **Proof points** — Metrics, case studies, customer quotes

## Workflow
1. **Gather context** — Read startup-context if available. Ask for the deal situation and what type of script is needed.
2. **Identify the script type** — Discovery call, first demo, technical deep-dive, executive overview, or closing call.
3. **Map pain to value** — Connect the prospect's specific pain points to your product's capabilities with proof.
4. **Draft the script** — Write the full script with timing, talk tracks, questions, and transition cues.
5. **Build objection responses** — Anticipate likely objections and write response frameworks.
6. **Add closing moves** — Include specific closing techniques appropriate to the deal stage.

## Output Format
Deliver the appropriate format based on the request:
- **Discovery call script** — Questions organized by topic, qualifying criteria, and next-step framing
- **Demo script** — Scene-by-scene with timing, talk track, interaction points, and transition cues
- **Objection handling doc** — Table format with objection, underlying concern, response, proof point, and follow-up question
- **Closing playbook** — Decision criteria checklist, closing techniques, and timeline management

## Frameworks & Best Practices

### Discovery Call Framework (30 min)

| Phase | Duration | What to Do |
|-------|----------|------------|
| **Rapport & agenda** | 3 min | Set the agenda, confirm time, build quick rapport |
| **Situation questions** | 7 min | Understand their current state and workflow |
| **Problem questions** | 8 min | Dig into pain points, frequency, and impact |
| **Implication questions** | 5 min | Explore the cost of not solving the problem |
| **Need-payoff questions** | 4 min | Let them articulate the value of a solution |
| **Next steps** | 3 min | Summarize, confirm fit, schedule the demo |

**Key discovery questions for founders to ask:**
1. "Walk me through how you handle [process] today."
2. "What happens when [problem] occurs? Who feels it most?"
3. "How much time/money does that cost you per month?"
4. "If you could fix one thing about this process, what would it be?"
5. "What has your team tried so far? What worked and what did not?"
6. "Who else would need to be involved in evaluating a solution?"
7. "What does your timeline look like for solving this?"

### Demo Script Structure (30-45 min)

1. **Opening** (2 min) — Context setting, agenda, confirm their priorities from discovery
2. **Discovery recap** (3 min) — "Last time you mentioned X, Y, Z — is that still accurate? Anything changed?"
3. **Workflow 1** (8 min) — Map to their primary pain point. Show, do not tell.
4. **Check-in** (2 min) — "How does this compare to how you handle it today?"
5. **Workflow 2** (8 min) — Map to their secondary pain point.
6. **Check-in** (2 min) — "Is this what you had in mind?"
7. **Workflow 3** (5 min) — Differentiator or delight feature they did not expect.
8. **Q&A** (5 min) — Handle live questions and objections.
9. **Close** (5 min) — Summarize value, propose next steps with specific dates.

**Demo principles:**
- Demo after discovery, never before. If you do not know their pain, you are guessing.
- Use their terminology and data when possible.
- Leave time for questions. A demo where the prospect does not talk is a demo that does not close.
- As a founder, share why you built the feature — the "origin story" resonates more than a feature walkthrough.

### Objection Handling Framework

For every objection, use the **LAER model**:
1. **Listen** — Let them finish. Do not interrupt or get defensive.
2. **Acknowledge** — "That makes sense" or "I hear that a lot."
3. **Explore** — Ask a follow-up to understand the real concern: "Help me understand — is the concern about X or Y?"
4. **Respond** — Address the real concern with proof, then confirm: "Does that address your concern?"

**Common objection categories and responses:**

| Category | Example Objection | Response Strategy |
|----------|------------------|-------------------|
| **Price** | "Too expensive" | Reframe as ROI. "What is the cost of not solving this?" |
| **Timing** | "Not the right time" | Uncover the real blocker. "What would need to change?" |
| **Competition** | "We already use X" | Acknowledge, then differentiate. "How is that working for [specific pain]?" |
| **Authority** | "I need to check with my boss" | Enable the champion. "What would they need to see to say yes?" |
| **Status quo** | "What we have works fine" | Quantify the hidden cost. Share a peer story. |
| **Trust** | "You are too small/new" | Lead with proof: customers, metrics, investors, team background |

### Closing Techniques for Founders

- **The summary close** — "So we have agreed that [pain] costs you [amount], our solution addresses [needs], and the team liked what they saw. What would it take to move forward this week?"
- **The timeline close** — "You mentioned wanting this solved by Q3. Working backward, we would need to start onboarding by [date]. Does that timeline work?"
- **The next-step close** — "What is the next step on your end? Who else needs to see this, and can we schedule that now?"
- **The pilot close** — "Would it help to start with a focused pilot? We could prove the value on [specific use case] and expand from there."
- **The founder close** — "I will personally make sure your onboarding goes smoothly. You would be working directly with me for the first 30 days."

### Founder-Led Sales Advantages
- You can make decisions on pricing and terms in real time — use this to accelerate deals
- You have the deepest product knowledge — use it to handle technical objections directly
- You can offer personal commitment to customer success that a sales rep cannot
- You understand the "why" behind every feature — share the vision, not just the functionality
- Early customers often buy the founder as much as the product — lean into that relationship

### What to Avoid
- Talking more than 40% of the time on discovery calls
- Demoing features the prospect did not ask about or does not need
- Getting defensive when handling objections
- Offering discounts before being asked — it signals low confidence
- Skipping discovery and going straight to demo
- Using technical jargon the prospect has not used first

## Related Skills
- `cold-outreach` — use to generate the meetings that lead to these sales conversations
- `proposal-generation` — use after a successful demo to create the formal proposal or SOW

## Examples

**Example prompt:** "I have a demo tomorrow with the Head of Engineering at a fintech startup. They care about reducing deployment failures. We cut deployment rollbacks by 60% for another customer."

**Good demo opening output:**
> "Thanks for making time, [Name]. Last week you mentioned your team is spending about 8 hours per sprint dealing with failed deployments and rollbacks. You said the biggest pain is that it slows down your release velocity and frustrates the team. Is that still the top priority, or has anything changed?
>
> Great. Here is what I want to show you today: three specific workflows that address deployment reliability. I will keep it focused — about 25 minutes — and leave time for your questions. Sound good?
>
> Let me start with how [Similar Fintech Customer] was handling this before they switched to us..."
