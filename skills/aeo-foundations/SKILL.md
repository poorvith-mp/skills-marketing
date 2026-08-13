---
name: aeo-foundations
description: >-
  Establishes answer engine optimisation basics: structuring content so AI assistants can quote
  it, with entity clarity and citable claims. Use when starting AEO work. Not for auditing
  existing visibility - use ai-citation-strategist.
---
# AEO Foundations

Structure content so AI assistants can find, trust and quote it.

## Process
1. **Answer the question in the first paragraph.** Assistants extract direct answers; content that builds to a conclusion over 800 words does not get quoted.
2. **Make claims self-contained.** A sentence that requires the previous three to make sense cannot be lifted as a citation.
3. **Attach evidence to claims** — a number, a date, a source. Unsupported assertions are paraphrased away; specific ones get cited.
4. **Be explicit about entities.** Name the product, company and category rather than relying on pronouns and context the extractor will not carry.
5. **Use structure that survives extraction**: real headings phrased as questions, short paragraphs, lists where the content is genuinely a list.
6. **Keep facts current and dated.** Assistants weight recency, and a stale figure is worse than none.
7. **Make the page machine-reachable** — crawlable, not JavaScript-gated, with schema markup where it applies.

For auditing existing visibility across assistants, use `ai-citation-strategist`.

## Deliverables
- Question-led structure with self-contained answers
- Claims paired with evidence and dates
- Entity naming audit
- Technical accessibility check

## Verification & Quality Checklist

- [ ] Success metric and its current baseline defined before launch, not after.
- [ ] Target segment named specifically enough to exclude someone.
- [ ] Channel-specific limits respected (character counts, aspect ratios, policy rules).
- [ ] Compliance checked for the channel (CAN-SPAM, GDPR, platform ad policy).

## Anti-Patterns & Constraints

- NEVER launch without a stated kill criterion and review date.
- NEVER claim a result without naming the attribution window and method.
- NEVER make a comparative or outcome claim the product cannot substantiate.
