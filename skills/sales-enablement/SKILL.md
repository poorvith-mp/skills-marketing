---
name: sales-enablement
last_reviewed: 2026-09-06
group: Sales handoff
description: >-
  Build the collateral that closes: decks, one-pagers, demo scripts and objection handling. Use
  when creating sales one-pagers, demo decks, or battlecards.
---

# sales-enablement

## Core Philosophy
Sales enablement collateral should not be 40-page generic corporate marketing slide decks that sales reps never open. Reps need high-velocity, modular assets that directly remove friction in the sales conversation: 1-page executive battlecards, technical objection cheat sheets, interactive ROI calculators, and crisp proof decks that answer the buyer’s security, integration, and migration concerns immediately.

---

## 4-Step Sales Enablement Framework

### Step 1: Rep Needs Audit & Objection Taxonomy
1. **Audit Deal-Killing Friction**:
   - Shadow 10 live sales and discovery calls across top and bottom-performing reps.
   - Categorize the top 5 recurring objections that stall deals:
     - *Security & Compliance*: "Where is data stored? Are you SOC 2 Type II compliant?"
     - *Migration Friction*: "How painful is switching from our incumbent legacy vendor?"
     - *Economic ROI*: "Why pay for this when we can build it internally or use open-source?"
     - *Feature Parity*: "Does your tool have feature X that competitor Y has?"

### Step 2: Competitor Battlecard Architecture
1. **The 1-Page Battlecard Structure**:
   - *Competitor Positioning*: How they pitch themselves in market.
   - *Where We Win*: Our top 3 undeniable architectural or commercial advantages.
   - *Where They Win*: Honest assessment of their strengths (and how to pivot away).
   - *Landmines to Lay*: Strategic technical questions for the buyer to ask the competitor.
   - *Quick Dismissal Talk Tracks*: 2-sentence responses to their most aggressive claims.

### Step 3: High-Impact Core Collateral Library
1. **The Executive One-Pager (PDF/Web)**:
   - Clear problem-solution breakdown, architecture diagram, 3 customer proof stats, and security badges.
2. **The 12-Slide Pitch Deck**:
   - Slide 1: Title & Positioning statement.
   - Slide 2: The Macro Industry Shift (why the old way is breaking).
   - Slide 3: The Core Pain & Quantified Business Cost.
   - Slide 4: The New Paradigm / Solution Architecture.
   - Slides 5–7: Product Demonstration / Key Differentiators.
   - Slide 8: Customer Case Study with hard metrics (e.g., "Saved $140k in cloud costs").
   - Slide 9: Security, Compliance & Enterprise Readiness.
   - Slide 10: Implementation & Time-to-Value Timeline.
   - Slide 11: Pricing Model & Commercial Packaging.
   - Slide 12: Next Steps / Mutual Action Plan (MAP).
3. **The ROI Calculator**:
   - Simple spreadsheet or web calculator translating customer inputs (team size, hourly dev rate, downtime frequency) into quantified annual savings.

### Step 4: Distribution, Governance & Feedback Loops
1. **Single Source of Truth**:
   - Host all collateral in a centralized, indexed repository (Notion, Seismic, or Highspot).
   - Tag assets by Deal Stage (Discovery, Evaluation, Security Review, Negotiation) and Buyer Persona (Developer, Engineering VP, CFO).
2. **Quarterly Asset Deprecation**:
   - Retire outdated screenshots, obsolete competitor pricing, and unverified stats every 90 days.

---

## Deliverable Format: Sales Battlecard Template (`BATTLECARD-[COMPETITOR].md`)

```markdown
# Competitor Battlecard: [Competitor Name]

## 1. Quick Overview & Snapshot
- **Incumbent Positioning**: [How they position themselves]
- **Target Profile**: [Their primary customer size/segment]
- **Pricing Model**: [Seat-based / Usage-based / Enterprise opaque]

## 2. Head-to-Head Comparison
| Dimension | Our Product | [Competitor Name] | Advantage |
|---|---|---|---|
| Deployment | Self-hosted / VPC / Cloud | Multi-tenant Cloud only | We win (Data Sovereignty) |
| Latency | < 5ms local processing | 120ms cloud roundtrip | We win (24x faster) |
| Enterprise Governance | Role-based RBAC, audit logs | Basic team seats | We win (SOC 2 ready) |

## 3. Landmines to Lay (Questions for Buyer to Ask Competitor)
1. *"How does your platform handle local offline execution when AWS us-east-1 drops?"*
2. *"Are your pricing tiers tied to database volume or seats, and what happens when we scale to 50 engineers?"*

## 4. Objection Talk Tracks
- **If Buyer says**: *"Competitor X is the established industry standard."*
- **Rep Response**: *"They built great tech 10 years ago for monolithic architectures. But modern microservice teams switch to us because our Rust runtime cuts infrastructure overhead by 65%."*
```

---

## Worked Example: Developer Tool Battlecard

- **Competitor**: Legacy Enterprise APM Vendor (Datadog/New Relic).
- **Core Objection**: "Datadog already monitors everything in our stack."
- **Talk Track**: "Datadog is fantastic for broad infrastructure metrics, but their custom metric ingestion pricing punishes high-cardinality data. We store your raw traces in your own ClickHouse instance, eliminating 70% of your monitoring bill."
- **Landmine**: "Ask Datadog what your invoice will look like when your trace retention expands from 7 to 30 days."

---

## Verification Checklist

- [ ] Collateral directly addresses verified deal-killing objections surfaced by sales reps.
- [ ] Competitor battlecards include specific technical landmines and defensive talk tracks.
- [ ] Pitch deck is strictly 12 slides or fewer and focuses on customer outcomes over features.
- [ ] All assets are organized by sales stage (Discovery, Evaluation, Closing) and persona.
- [ ] Quarterly review date is scheduled to audit and deprecate obsolete collateral.

---

## Anti-Patterns

- **Marketing Decks for Sales**: Giving reps 40-slide decks filled with high-level corporate branding and zero pricing or security details.
- **Unverified Competitor Bashing**: Making false or outdated claims about competitors that ruin credibility with technical buyers.
- **Neglecting Security Collateral**: Leaving security and compliance documentation to be hastily compiled during closing week.
