---
name: data-room
trigger: When the user wants to prepare a due diligence data room for fundraising, or when an investor has requested additional materials after a pitch. Also activates for "data room", "due diligence", "DD checklist", or "what documents do investors need?".
related: [pitch-deck, investor-research]
reads: [startup-context]
---

# Data Room

## When to Use

- The founder is mid-fundraise and investors are requesting due diligence materials.
- The founder wants to proactively prepare a data room before starting outreach.
- The founder received a term sheet and needs to prepare for confirmatory due diligence.

## Context Required

From `startup-context`: stage, legal entity type, founding date, team composition, fundraising history, cap table basics, revenue/metrics, and any existing legal or financial documents.

From the user: current round stage (pre-term sheet vs. post-term sheet), which investor is requesting materials, and any specific document requests received.

## Workflow

1. **Read startup context** — Pull company details from `.agents/startup-context.md` to understand stage, entity type, and what documents should already exist.
2. **Assess the DD stage** — Determine if this is proactive prep (pre-pitch), initial DD (post-first meeting), or confirmatory DD (post-term sheet). The scope differs significantly.
3. **Generate the checklist** — Produce a stage-appropriate checklist using the master framework below. Mark each item as: Exists, Needs Update, Needs Creation, or Not Applicable.
4. **Audit existing materials** — Review documents for completeness, staleness (financials older than 1 month), and red flags (missing signatures, inconsistent cap table).
5. **Draft missing items** — Provide templates or drafts for documents the founder needs to create (financial summary, KPI dashboard, org chart).
6. **Organize the room** — Recommend a folder structure and set access controls for what to share pre- vs. post-term sheet.

## Output Format

A structured checklist in markdown, organized by category:

```
## Data Room Checklist — [Company Name] — [Round]

### Section 1: Corporate Documents
- [x] Certificate of Incorporation — exists, current
- [ ] Board consent for fundraise — needs creation
- [ ] 409A valuation — needs update (last done 14 months ago)
```

Followed by a recommended folder structure and access-level guidance.

## Frameworks & Best Practices

### Master Due Diligence Checklist

**1. Corporate Documents**: Certificate of Incorporation (and amendments), bylaws, board minutes (last 12 months), board consent for fundraise, stockholder agreements, QSBS eligibility docs, state registrations, any pending litigation.

**2. Cap Table & Equity**: Fully diluted cap table (Carta/Pulley export, not a manual spreadsheet), option plan and grant ledger, SAFEs/convertible notes with terms, pro forma post-round cap table, current 409A valuation (<12 months old), secondary sale history.

**3. Financials**: P&L, balance sheet, cash flow — actual, last 12 months (monthly). Bank balance and burn rate. 18-36 month projections with stated assumptions. Revenue breakdown by customer/cohort. Unit economics (CAC, LTV, gross margin, payback). AR/AP aging. Outstanding debt.

**4. Metrics & KPIs**: Monthly KPI dashboard (MRR/ARR, growth, churn, NRR, DAU/MAU). Cohort retention. Sales pipeline (B2B) or funnel conversion (B2C/PLG).

**5. Product & Technology**: Product roadmap (6-12 months), architecture overview, IP ownership confirmation, patent filings, open source license audit, SOC 2 or security summary.

**6. Contracts & Customers**: Top 10 customer contracts, customer concentration analysis (<20% per customer is ideal), key vendor/partner agreements, exclusivity or non-compete clauses, churn log.

**7. Team & HR**: Org chart, founder/key employee bios, employment agreements (confirm IP assignment), contractor agreements, option grant summary, HR disputes, benefits summary.

**8. Legal & Compliance**: Privacy policy and GDPR/CCPA status, regulatory licenses, trademarks, terms of service, insurance (D&O, E&O, cyber).

### Stage-Specific Scoping

- **Pre-seed / Seed**: Focus on sections 1, 2, 3 (lighter — 3-6 months of financials), and 7 (team). Product and legal can be thinner. No 409A yet is fine.
- **Series A**: All sections expected. Monthly financials for 12+ months. Solid metrics dashboard. Airtight IP assignment. Current 409A required.
- **Post-term sheet DD**: Everything above, plus items the lead investor's counsel specifically requests. Corporate governance gets scrutinized here.

### Folder Structure

```
/01-Corporate           /05-Product-and-Technology
/02-Cap-Table-Equity    /06-Contracts-Customers
/03-Financials          /07-Team-HR
/04-Metrics-KPIs        /08-Legal-Compliance
                        /09-Pitch-Materials
```

### Access Control

- **Pre-term sheet**: Share pitch materials, metrics dashboard, financial summary, team bios. Hold back contracts, full cap table, legal docs.
- **Post-term sheet**: Open the full room. Require an NDA before sharing customer contracts or detailed financials.
- Watermark PDFs with the investor's name. Use link-level analytics (DocSend) to track what gets opened.

### Red Flags That Kill Deals

- Cap table inconsistencies between the table and signed documents.
- Missing IP assignment agreements for contractors who built core product.
- Stale or missing 409A when options have been granted.
- Financial statements that don't reconcile with bank statements.
- Non-standard founder vesting without board approval documentation.

## Related Skills

- `pitch-deck` — the deck is the top-of-funnel; the data room is the supporting evidence
- `investor-research` — knowing which investors are in the pipeline helps prioritize what to prepare first

## Examples

**Example prompt**: "We just got a term sheet for our Series A. What do I need in my data room?"

**Good output approach**: Generate the full 8-section checklist scoped for confirmatory DD. Cross-reference against startup context to pre-fill what likely exists. Flag highest-risk items (cap table accuracy, IP assignments, 409A currency). Recommend a folder structure and 2-4 week timeline.

**Example prompt**: "I'm about to start fundraising for our seed round. Should I set up a data room now?"

**Good output snippet**:

> Yes — a proactive data room signals operational maturity. For seed, focus on:
> - Clean cap table export (Carta or Pulley, not a spreadsheet)
> - Certificate of Incorporation and amendments
> - 6-month financial summary (revenue, burn, bank balance)
> - IP assignment agreements for all founders and contractors
> - Monthly KPI dashboard (MRR, user count, growth rate)
