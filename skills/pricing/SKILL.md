---
name: pricing
last_reviewed: 2026-09-06
group: Offer and money
description: >-
  Set tiers, value metric, trial versus freemium and price changes, and audit the pricing page.
  Use when determining price levels, packaging tiers, or freemium models.
---

# Pricing

Pricing is a function of positioning and value capture, not cost-plus accounting. The most consequential lever in software economics is the value metric: charging in alignment with how the customer derives value creates an automatic expansion loop as they grow.

## 1. Value Metric Decision Tree

Choose a value metric that scales with customer usage without punishing adoption:
- **Per-Seat / Per-User**: Best when collaboration is the primary product value (e.g. Slack, Figma). Anti-pattern when single users share credentials; avoid if account sharing throttles adoption.
- **Usage / Consumption-Based**: Best when value correlates directly with discrete units (API requests, compute minutes, GB stored, emails sent). Ensure customers can set spend caps and alerts to prevent bill shock.
- **Outcome / Value-Shared**: Best when attribution is clean and deterministic (percentage of payments processed, percentage of ad spend managed).
- **Feature-Gated Tiered**: Best when customer segments have distinct feature requirements (individuals vs teams vs enterprise security/compliance).

## 2. Trial vs. Freemium Framework

Decide your customer acquisition model based on product economics:
- **Free Trial (Time-limited, 14-30 days)**:
  - Best when: Product has high perceived value, setup requires effort, or marginal server/API costs per active user are non-trivial.
  - Requires: Tight onboarding sprint to deliver the "aha" moment within the first 48 hours.
  - Variant: Reverse trial (start all users on full Pro features for 14 days, downgrade to free tier on day 15).
- **Freemium (Feature-limited or usage-capped forever)**:
  - Best when: Marginal cost per free user is near zero, product has strong built-in virality/network effects, and the free product serves as the primary top-of-funnel acquisition channel.
  - Failure mode: Generous free tier that satisfies 95% of users with no incentive to upgrade.

## 3. Tier Architecture & Packaging (Good / Better / Best)

Structure 3 distinct tiers to guide segmentation:

| Element | Tier 1: Starter | Tier 2: Pro (Target Tier) | Tier 3: Enterprise |
|---|---|---|---|
| **Target Persona** | Solopreneurs, early adopters | Growing teams, power users | Companies with procurement & security |
| **Positioning** | Fast time-to-value, low friction | Complete workflow, collaboration | Compliance, SSO, dedicated SLA |
| **Pricing Anchor** | Accessible entry point ($19–$49/mo) | The highlighted default ($79–$199/mo) | Custom contract ($10k+/yr, sales-assisted) |
| **Feature Fences** | Core features, single user | Team workspaces, integrations, exports | SAML/SSO, audit logs, custom terms |

### Pricing Psychology & Framing
- **Visual Anchoring**: Highlight the Pro tier visually (badge: "Most Popular", subtle elevation or distinct primary button color).
- **Annual Billing Incentive**: Offer 2 months free or a 15–20% discount on annual commitment to pull forward cash flow and reduce churn.
- **Charm Pricing**: Use charm pricing ($49/mo, $99/mo) for self-serve credit card purchases; use rounded round numbers ($5,000/yr, $20,000/yr) for enterprise and sales-led contracts.

## 4. Price Increases & Migration Playbook

When increasing prices or changing packaging:
1. **Grandfather Existing Customers**: Reward early adopters by locking their existing rate for 12 months (or indefinitely on their current tier), charging higher rates only to new signups.
2. **Advance Notice**: Provide a 30 to 60-day notice explaining the product improvements and investments made since the last price point.
3. **Upgrade Window**: Offer existing users an option to lock in the old rate for an additional annual term before the price increases take effect.
4. **Monitor Churn Risk**: Model expected churn against revenue expansion: a 20% price hike with a 5% churn increase is a net +14% revenue gain.

## 5. Pricing Page Audit Rubric

Audit an existing pricing page against these conversion criteria:
- [ ] **Value Metric Clarity**: Can a prospect determine their tier in under 15 seconds?
- [ ] **Feature Fence Transparency**: Are differences between tiers explicit (not hidden in expandable accordions)?
- [ ] **Toggle Ergonomics**: Does the monthly/annual toggle clearly display savings (e.g. "Save 20%")?
- [ ] **FAQ for Purchase Hesitations**: Does the FAQ address cancellation terms, refunds, seat additions, and security compliance?
- [ ] **Secondary CTAs**: Does enterprise have a "Contact Sales" or "Book Demo" path while self-serve tiers have direct checkout?
- [ ] **Risk Reversals**: Is there a money-back guarantee or "no credit card required" note immediately beneath the primary CTA?

## Critical Rules
1. Never price based solely on hosting or development cost; anchor to the financial value delivered to the buyer.
2. Ensure every tier has a clear, non-negotiable upgrade trigger (a threshold where staying on the lower tier becomes inconvenient).
3. Do not hide pricing behind a sales call for products under $5,000 ARR unless procurement or security customization requires high-touch closing.

## Verification Checklist
- [ ] Value metric aligns with customer usage and expands revenue organically.
- [ ] Feature fences separate customer segments by willingness to pay, not by artificial crippleware.
- [ ] Annual billing discount provides meaningful cash acceleration without destroying unit margins.
- [ ] Pricing page copy and comparison table eliminate ambiguity about what is included.
- [ ] Price change strategy incorporates grandfathering and clear advance communication.

## Anti-Patterns
- NEVER gate table-stakes security features (like 2FA or basic exports) behind the Enterprise tier; reserve Enterprise for SAML SSO, SCIM, and SOC 2 reports.
- NEVER make the free tier so capable that target paying users never experience a constraint.
- NEVER introduce complex multi-variable pricing equations that require a spreadsheet for the buyer to predict their monthly invoice.
