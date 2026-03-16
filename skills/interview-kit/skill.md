---
name: interview-kit
trigger: When the user needs to design an interview process, create interview questions, build scorecards, or evaluate candidates for a role.
related: [job-description, sourcing-outreach]
reads: [startup-context]
---

# Interview Kit

## When to Use
Activate when the user asks to design an interview loop, create structured interview questions, build evaluation rubrics, design take-home assignments, benchmark compensation for an offer, or reduce bias in their hiring process. Also activate when a user has a JD ready and needs to turn it into a repeatable evaluation process.

## Context Required
- **From startup-context:** Company stage, team size, engineering culture, current interview process (if any), and hiring velocity.
- **From user:** Role title, level, key competencies to evaluate, number of interview rounds the team can support, and whether a take-home or live exercise is preferred.

## Workflow
1. **Define competencies** — Extract 4-6 core competencies from the job description or role discussion. Split into technical skills, domain knowledge, collaboration traits, and startup-fit signals.
2. **Design the interview loop** — Map competencies to interview stages. Each stage should evaluate distinct competencies with minimal overlap. A typical startup loop: screen call, technical assessment, team interview, founder/values interview.
3. **Write structured questions** — For each stage, write 3-5 primary questions with follow-up probes. Every question must map to a specific competency. Include "what good looks like" answer guidance.
4. **Build scorecards** — Create a 1-4 rating scale for each competency with behavioral anchors at each level. Interviewers score independently before debriefing.
5. **Design take-home or live exercise** — If applicable, create a practical assessment that mirrors real work. Include a time cap, clear instructions, and an evaluation rubric.
6. **Add anti-bias guardrails** — Include structured debrief instructions, independent scoring protocol, and a checklist of common bias traps.
7. **Benchmark compensation** — If requested, provide a framework for researching market rates using level, location, and company stage as inputs.

## Output Format
A complete interview kit document containing:
- Role summary and competency matrix
- Interview loop overview (stages, duration, interviewers)
- Per-stage question sets with scoring rubrics
- Take-home or live exercise brief (if applicable)
- Scorecard template
- Debrief protocol
- Compensation benchmarking notes (if requested)

## Frameworks & Best Practices

### Competency Categories by Role Type
**Engineering roles:** System design, code quality, debugging approach, technical communication, ownership/initiative.
**Product roles:** Customer empathy, prioritization frameworks, cross-functional communication, data-informed thinking, shipping velocity.
**Go-to-market roles:** Discovery/qualification, storytelling, objection handling, pipeline management, customer orientation.
**Design roles:** Design process, craft quality, user research fluency, systems thinking, collaboration with engineering.

### The STAR-B Question Framework
Structure behavioral questions to elicit complete answers:
- **Situation:** Set the scene
- **Task:** What was your responsibility
- **Action:** What specifically did you do
- **Result:** What happened
- **Behavior pattern:** Is this a repeatable pattern or one-off

Example: "Tell me about a time you had to ship something with significant technical debt. What was the situation, what did you decide, and how did it play out? Would you make the same call again?"

### Scorecard Design (1-4 Scale)
Avoid a 1-5 scale — it creates a "3 means fine" middle ground that erases signal.
- **1 — Does not meet bar:** Could not demonstrate the competency. Clear concerns.
- **2 — Below bar:** Showed partial ability but gaps are significant for the level.
- **3 — Meets bar:** Demonstrated the competency at the expected level. Solid hire signal.
- **4 — Exceeds bar:** Demonstrated exceptional strength. Would raise the team's overall capability.

Each score level should include 1-2 concrete behavioral anchors specific to the role.

### Take-Home Assignment Guidelines
- **Time-capped:** 2-4 hours maximum. State this explicitly and mean it.
- **Mirrors real work:** The exercise should resemble an actual task the person would do in the role.
- **Clear evaluation criteria:** Share the rubric with the candidate upfront so they know what you value.
- **Equitable:** Provide accommodations. Offer a paid alternative if the candidate cannot invest unpaid time.
- **Debrief:** Always follow up with a live walkthrough where the candidate explains their choices.

### Anti-Bias Techniques
- **Structured questions:** Every candidate for the same role gets the same core questions in the same order.
- **Independent scoring:** Interviewers submit scores before the debrief meeting. No anchoring on a senior person's opinion.
- **Blind resume review:** Where possible, strip names, photos, school names, and company names in the initial screen.
- **Diverse interview panels:** Include at least one interviewer from an underrepresented background when possible.
- **"Would I say this about a different candidate?" test:** Before writing feedback, check if the language would change if the candidate's demographics were different.
- **Avoid culture-fit framing:** Replace "culture fit" with "values alignment" and require specific evidence.

### Compensation Benchmarking Framework
Use three inputs to triangulate:
1. **Market data:** Levels.fyi, Pave, Carta Total Comp (for equity), and Glassdoor as directional inputs.
2. **Stage multiplier:** Seed-stage roles typically pay 70-85% of big-co base but with 0.5-2% equity. Series A narrows the cash gap to 80-95%.
3. **Candidate calibration:** Where does this person fall within the level band? Adjust for their specific experience, competing offers, and location.

Always present comp as a range with a target midpoint, not a single number.

## Related Skills
- `job-description` — Use the JD's competency requirements as the input for designing the interview loop.
- `sourcing-outreach` — Align outreach messaging with the interview process so candidates know what to expect.

## Examples

**Prompt:** "Design an interview process for a senior backend engineer. We're a 15-person startup."

**Good output snippet:**
```
## Interview Loop — Senior Backend Engineer

### Competencies to Evaluate
1. System design & architecture (technical depth)
2. Code quality & testing practices (craft)
3. Debugging & production thinking (operational maturity)
4. Technical communication (collaboration)
5. Ownership & initiative (startup fit)

### Stage 1: Recruiter/Founder Screen (30 min)
- Evaluate: Motivation, communication, logistics
- Questions:
  - "What's drawing you to an early-stage company right now?"
  - "Walk me through the most impactful project you led in the last year."

### Stage 2: Technical Deep-Dive (60 min)
- Evaluate: System design, code quality
- Format: Live system design discussion + code review exercise
...
```

**Prompt:** "Our interviewers keep disagreeing on candidates. How do we fix this?"

**Good output snippet:**
```
This usually means you're missing structured evaluation criteria. Here's
a three-step fix:

1. Define 4-5 competencies per role with written descriptions
2. Give each interviewer a scorecard to fill out independently BEFORE
   the debrief meeting
3. In the debrief, discuss scores that diverge by 2+ points — focus
   on evidence, not impressions

The goal isn't consensus — it's calibrated, evidence-based evaluation.
```
