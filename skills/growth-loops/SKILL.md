---
name: growth-loops
last_reviewed: 2026-09-06
group: Operating layer
description: >-
  Set up recurring marketing workflows an agent runs on a schedule. Use when designing
  self-reinforcing acquisition, content, or product loops.
---

# Growth Loops

Growth loops are self-reinforcing compounding mechanisms where the action of an existing user naturally generates inputs that attract new users or re-engage existing ones. Unlike linear marketing funnels (where customer acquisition stops the moment ad spend pauses), growth loops reinvest user activity into viral, content, or product-led expansion.

## 1. The Anatomy of a Closed Growth Loop

Every growth loop consists of three structural phases:
1. **User Action / Output**: An existing user achieves value inside the product (e.g. creates a document, publishes an agent, generates a dashboard).
2. **Distribution / Exposure**: That output is shared or discovered by non-users (via public links, watermarked widgets, search engine indexing, or collaboration invitations).
3. **New User Activation**: The non-user encounters the output, experiences the value, signs up, and completes their own action, restarting the loop.

## 2. The 4 Fundamental Growth Loop Archetypes

### A. Viral & Collaborative Loops (Product-Led)
- **Mechanism**: Product is collaborative by nature; using it requires inviting others.
- *Examples*: Figma, Slack, Notion, Calendly.
- *Loop Metric (Viral Coefficient $K$)*:
  $$K = i \times c$$
  - $i$: Number of invites/links generated per user.
  - $c$: Conversion rate of invited recipients to active users.
  - *Rule*: If $K > 1.0$, the product exhibits true viral compounding.

### B. User-Generated Content (UGC) & Search Loops
- **Mechanism**: Users create public-facing content inside the platform that gets indexed by search engines.
- *Examples*: Stack Overflow, GitHub, Canva templates.
- *Loop*: User asks question / builds template -> Google indexes page -> New searchers find solution -> New users join to ask questions or clone templates.

### C. Paid Growth Loops (Reinvestment Velocity)
- **Mechanism**: Paid customer acquisition funded directly by the cash collected from existing cohorts.
- *Loop*: Spend $1,000 on ads -> Acquire $3,000 in upfront annual contracts -> Immediately reinvest $2,000 into ad budget.
- *Constraint*: Dependent on rapid cash payback period (<6 months).

### D. Data & Model Improvement Loops
- **Mechanism**: User interactions generate domain data that improves the underlying AI model or matching algorithm, making the product superior for all subsequent users.

## 3. Loop Friction Diagnostics
Identify the single bottleneck constricting loop velocity:
- *Invitation Friction*: Are users reluctant to share? (Incentivize with storage, feature unlocks, or bilateral referral rewards).
- *Recipient Friction*: Does the external link require an immediate password signup before viewing? (Allow recipient to view/interact with the shared asset immediately before prompting for account creation).

## Critical Rules
1. Never build an artificial referral loop on a product that users consider private or confidential.
2. The shared artifact must provide immediate value to the external recipient without forcing a mandatory signup wall.
3. Track and optimize loop cycle time: reducing the time it takes a user to invite a collaborator from 7 days to 2 days triples annual loop velocity.

## Verification Checklist
- [ ] Growth loop mechanics mapped to one of the 4 fundamental archetypes.
- [ ] Viral coefficient $K$ and invitation acceptance rates instrumented in analytics.
- [ ] Shared assets provide immediate preview value to external recipients.
- [ ] Loop cycle time measured and optimized across user onboarding.
- [ ] Incentives aligned with both sender and receiver value.

## Anti-Patterns
- NEVER force spammy contact-book uploads or automatic invitation emails without explicit user consent.
- NEVER rely on linear paid acquisition channels as your sole growth mechanism without designing an underlying retention or referral loop.
- NEVER watermark shared assets so aggressively that users are embarrassed to send them to their clients.
