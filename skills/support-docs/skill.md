---
name: support-docs
trigger: When the user needs to create help center articles, FAQs, troubleshooting guides, API documentation, or getting-started guides for customers.
related: [process-docs, onboarding-flow]
reads: [startup-context]
---

# Support Documentation

## When to Use
Activate when a founder or team member needs to create customer-facing documentation that helps users solve problems independently. This includes prompts like "write a help center article," "create an FAQ," "document our API," "write a troubleshooting guide," "build a getting-started guide," or "our support tickets keep asking the same questions."

## Context Required
- **From startup-context:** product type, target user technical level, existing documentation (if any), top support ticket categories, and tools used for docs hosting (e.g., Notion, GitBook, Zendesk, ReadMe).
- **From the user:** the specific topic to document, the target audience (end users, admins, developers), the user's technical sophistication, common failure modes or confusion points, and whether this is a new article or an update to existing content.

## Workflow
1. **Identify document type** — Determine which template fits: help center article, FAQ, troubleshooting guide, API reference, or getting-started guide. Each serves a different user intent.
2. **Define the user's entry point** — How will someone find this document? Search query, error message, support agent link, in-app help button? This determines the title and opening line.
3. **Write in problem-solution format** — Lead with the user's problem (in their words), then provide the solution. Never start with product architecture explanations.
4. **Apply progressive disclosure** — Put the most common answer first. Nest edge cases, advanced options, and technical details in expandable sections or later in the article.
5. **Add searchability elements** — Include the exact error messages, feature names, and colloquial terms users search for. Repeat key terms naturally.
6. **Test with the "3 AM rule"** — Read the article as if you are a frustrated user at 3 AM with a broken workflow. Does it get you to a solution in under 2 minutes? If not, restructure.
7. **Link related articles** — Add "Related" or "Next steps" links at the bottom to keep users in the self-serve flow.

## Output Format
A markdown document following one of the five templates below. Every support doc should be scannable in under 30 seconds and solvable in under 2 minutes.

### Template 1: Help Center Article
```
# [Action-oriented title: "How to X" or "Setting up Y"]

[One sentence describing what this article helps you do.]

## Before You Start
- Prerequisites or permissions needed

## Steps
1. Action step with specific UI path (Settings > Integrations > Slack)
2. Next action step
   > **Note:** Important callout for common mistakes

## Frequently Asked Questions
**Q: Common question about this feature?**
A: Direct answer.

## Still Need Help?
Contact support at [link] or chat with us in-app.
```

### Template 2: Troubleshooting Guide
```
# Troubleshooting: [Problem in user's words]

## Symptoms
What the user sees when this problem occurs (exact error messages in code blocks).

## Quick Fix
The solution that works 80% of the time. Put this first.

## If That Didn't Work
### Cause 1: [Most common cause]
How to diagnose → How to fix

### Cause 2: [Second most common]
How to diagnose → How to fix

## Collect Information for Support
If none of the above worked, gather these details before contacting support:
- [Specific data point 1]
- [Specific data point 2]
```

### Template 3: FAQ Page
Group questions by category (Getting Started, Common Issues, Billing). Each answer is 1-3 sentences with a link to the full article if the answer requires more detail.

### Template 4: API Documentation
Structure: endpoint + method, authentication, request parameters (table with name/type/required/description), example request (working curl), response examples (success + every error code), and rate limits. Every code snippet must be copy-pasteable and functional.

### Template 5: Getting-Started Guide
Structure: welcome sentence with outcome and time commitment, 3-5 sequential steps (each with the action and why it matters), a verification moment ("you should now see X"), and "What's Next" links to deeper features.

## Frameworks & Best Practices

### The Problem-Solution-Verification Pattern
Every support document should follow this arc:
1. **Problem:** State what the user is trying to do or what went wrong (using their language, not internal jargon).
2. **Solution:** Provide the fix or steps, in order, with exact UI paths and expected outcomes at each step.
3. **Verification:** Tell the user how to confirm it worked. "You should now see X on the Y page."

### Searchability Principles
- **Title matches the search query.** "How to export data to CSV" not "Data Export Functionality Overview."
- **Include error messages verbatim.** If users see `Error 403: Insufficient permissions`, that exact string must appear in your troubleshooting guide.
- **Use both technical and colloquial terms.** Write "single sign-on (SSO)" so both "SSO" and "single sign-on" searches find the article.
- **Front-load the answer.** Put the solution in the first 100 words. Many users never scroll.

### Progressive Disclosure Rules
- **Level 1 (visible):** The answer that works for 80% of users.
- **Level 2 (expandable):** Edge cases, advanced configuration, platform-specific variations.
- **Level 3 (linked):** Deep technical details, architecture explanations, full API reference.
- Never force a basic user through advanced content to get a simple answer.

### Writing Style and Maintenance
- **Second person, present tense.** "Click Save" not "You will click Save." "You can" not "Users can."
- **Specific UI paths.** "Go to Settings > Team > Permissions" not "Navigate to your team settings."
- **Show, then explain.** Lead with the action, then add context. Users want to solve first, understand second.
- **Consistent terminology.** If the UI says "Workspace," never call it "Organization" in docs.
- **Tag and date every article.** Outdated docs are worse than no docs. Review on every product release.
- **Track deflection rate.** If a help article does not reduce support tickets for that topic, rewrite it.
- **Include a feedback widget.** "Was this helpful? Yes / No" — route "No" responses to the docs owner.

## Related Skills
- `process-docs` — Chain when the support topic requires an internal SOP to handle edge cases or escalations that the customer-facing doc cannot resolve alone.
- `onboarding-flow` — Chain when creating getting-started guides that serve as part of the new-user onboarding experience.

## Examples

### Example 1: Troubleshooting guide
**User:** "Users keep emailing us saying they can't connect their Slack integration. Write a troubleshooting guide."

**Good output excerpt:**
> # Troubleshooting: Slack Integration Not Connecting
>
> ## Symptoms
> When you click "Connect to Slack," you see one of these errors:
> - `Authorization failed. Please try again.`
> - The page redirects back to Settings with no confirmation message.
> - Slack opens but shows "This app is not approved by your workspace admin."
>
> ## Quick Fix
> 1. **Try a different browser.** Browser extensions (especially ad blockers) can interfere with the OAuth redirect. Open an incognito/private window and retry.
> 2. **Check your Slack permissions.** You must be a Slack Workspace Admin or Owner. Ask your Slack admin to grant you permission, or have them complete the connection.
>
> ## If That Didn't Work
> ### Cause: Slack workspace restrictions
> Your Slack workspace may require admin approval for new apps.
> - **Diagnose:** If you see "This app is not approved by your workspace admin," this is the cause.
> - **Fix:** Ask your Slack admin to approve our app at Slack Admin > Apps > Manage > search for "[Product Name]" > Approve.

### Example 2: API documentation
**User:** "Document our webhook endpoint. It accepts POST requests with event data and returns 200 on success."

**Good output approach:** Follow the API template precisely. Include authentication details, every parameter with type and required/optional, a working curl example, all response codes with descriptions, rate limits, and a retry policy. Developers will copy-paste from this doc, so every code snippet must actually work.
