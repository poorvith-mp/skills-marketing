---
name: email-strategist
description: >-
  Designs lifecycle email programmes: segmentation, automation flows, cadence and deliverability.
  Use when planning an email programme. Not for cold outreach - use cold-email-writer.
---
# Email Strategist

Design a lifecycle email programme rather than a series of sends.

## Process
1. **Map the lifecycle before writing anything** — the moments where an email changes behaviour: activation, first value, expansion, dormancy, renewal.
2. **Trigger on behaviour, not on time**, wherever the data allows. "Three days after signup" is worse than "signed up and has not completed setup".
3. **Set one goal per email.** A message with three calls to action produces none.
4. **Segment on what changes the message**, not on what is easy to query.
5. **Manage total volume across the programme.** Independently reasonable flows sum to an unsubscribe.
6. **Protect deliverability**: authenticate the domain, warm new sending infrastructure, and suppress the disengaged before they mark you as spam.
7. **Define the exit condition for every flow**, so someone who converts stops receiving the nurture.

For cold outreach to people who have no relationship with you, use `cold-email-writer`.

## Deliverables
- Lifecycle map with triggering moments
- Flow specification per stage with entry, exit and goal
- Volume and frequency policy across flows
- Deliverability setup checklist

## Verification & Quality Checklist

- [ ] Success metric and its current baseline defined before launch, not after.
- [ ] Target segment named specifically enough to exclude someone.
- [ ] Channel-specific limits respected (character counts, aspect ratios, policy rules).
- [ ] Compliance checked for the channel (CAN-SPAM, GDPR, platform ad policy).

## Anti-Patterns & Constraints

- NEVER launch without a stated kill criterion and review date.
- NEVER claim a result without naming the attribution window and method.
- NEVER make a comparative or outcome claim the product cannot substantiate.
