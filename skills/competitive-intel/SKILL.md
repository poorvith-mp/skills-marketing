---
name: competitive-intel
last_reviewed: 2026-09-06
group: Foundation
description: >-
  Turn competitor URLs into structured dossiers, then into battlecards and vs/alternative pages.
  Use when analyzing competitor positioning, feature parity, or teardowns.
---

# Competitive Intel

Competitive intelligence is differentiation engineering, not corporate espionage. Analyzing competitors requires systematically inspecting their public footprints (pricing tiers, changelogs, customer review sentiment, hiring patterns, teardowns), synthesizing findings into actionable battlecards, and building SEO-driven comparative landing pages (`/vs/` and alternative pages).

## 1. The 5-Source Intelligence Gathering Protocol
Inspect competitors across five public data streams:
1. **Product & Release Velocity**:
   - Monitor their official changelogs, GitHub releases, and documentation updates.
   - Note which feature requests languish unresolved in their public issue trackers and forums.
2. **Pricing & Packaging Changes**:
   - Track shifts in their value metrics, tier thresholds, grandfathering terms, and free plan limitations using tools like Visualping.
3. **Customer Review Mining (G2, Capterra, Trustpilot, Reddit)**:
   - Filter reviews by 2-star and 3-star ratings: this is where frustrated power users articulate exact architectural and customer service shortcomings.
4. **Hiring Postings & Job Descriptions**:
   - Engineering job postings reveal their upcoming tech stack migrations, new platform expansions, and infrastructure bottlenecks.
5. **SEO & Paid Advertising Footprint**:
   - Analyze which keywords competitors bid on via Google Ads and which high-intent organic terms drive their traffic.

## 2. Sales Battlecard Architecture
Equip your sales reps and support teams with 1-page tactical battlecards:

```markdown
# Battlecard: [Your Product] vs. [Competitor]

## Core Differentiator (The "Kill Shot" Positioning)
[Competitor] is built for legacy enterprise IT teams requiring months of professional services;
[Your Product] is developer-first, deploying in under 10 minutes with full API control.

## When We Win (Our Strengths)
- Local-first architecture (zero external data exfiltration)
- Transparent usage-based pricing with no annual contracts
- Native subagent orchestration support

## When They Win (Their Strengths / Our Gaps)
- Established legacy ERP integrations (SAP, Oracle)
- 24/7 phone support and dedicated account managers for 500+ seat deals

## Trap-Setting Questions (To Ask the Prospect)
- "How long does your current vendor take to roll back a breaking schema migration?"
- "Are you locked into annual seat minimums even when project teams scale down?"

## Common Objection Handling
- Objection: "[Competitor] has been around for 10 years."
- Pivot: "Yes, and their architecture was built before modern serverless runtimes. That's why
  their customers experience 4-week release cycles while we push updates continuously."
```

## 3. Alternative & Comparison Landing Page Architecture (`/vs/` Pages)
Build fair, high-converting comparative pages:
- **Fair Comparison Matrix**: Acknowledge where the competitor genuinely excels (e.g. legacy enterprise compliance); bias makes the entire page suspect.
- **Direct Feature-by-Feature Table**: Compare specific capabilities with verifiable proof points.
- **Migration Guide**: Outline exact steps to export data from the competitor and import it into your platform.

## Critical Rules
1. Never misrepresent competitor capabilities; false comparative claims destroy sales credibility.
2. Focus battlecards on business outcomes and developer workflows rather than superficial UI cosmetic differences.
3. Update competitive battlecards quarterly to reflect competitor feature releases and pricing adjustments.

## Verification Checklist
- [ ] Intelligence gathered from verified customer reviews and public product documentation.
- [ ] Battlecard includes specific trap-setting discovery questions.
- [ ] Legitimate competitor strengths acknowledged alongside primary differentiators.
- [ ] Comparison landing page contains factual, substantiated claims.
- [ ] Migration and data portability guide documented for switching customers.

## Anti-Patterns
- NEVER disparage competitors emotionally; let objective benchmarks and customer quotes carry the critique.
- NEVER assume competitor pricing is fixed; enterprise competitors frequently discount 30%–50% in competitive deals.
- NEVER obsess over competitor features at the expense of listening to your own active customers.
