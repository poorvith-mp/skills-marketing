---
name: unit-economics
last_reviewed: 2026-09-06
group: Offer and money
description: >-
  Model CAC, LTV, payback and channel break-even so spend decisions have a floor. Use when
  calculating CAC, LTV, payback periods, or contribution margin.
---

# Unit Economics

Growth without positive unit economics is accelerated insolvency. Marketing and growth investments must be governed by fully-loaded Customer Acquisition Cost (CAC), gross-margin-adjusted Lifetime Value (LTV), cash payback velocity, and channel-level contribution margins.

## 1. Core Mathematical Formulations

### A. Customer Acquisition Cost (CAC)
Distinguish between blended and paid acquisition costs:
- **Paid CAC**:
  $$\text{Paid CAC} = \frac{\text{Direct Paid Ad Spend}}{\text{Customers Acquired via Paid Channels}}$$
- **Fully-Loaded CAC** (the true economic floor):
  $$\text{Fully-Loaded CAC} = \frac{\text{Ad Spend} + \text{Agency/Creative Fees} + \text{Salaries (Sales + Mktg)} + \text{Software Stack}}{\text{Total New Customers Acquired}}$$
  *Rule*: Always use Fully-Loaded CAC when setting budget ceilings.

### B. Customer Lifetime Value (LTV)
Never calculate LTV using top-line revenue alone; LTV must be adjusted for cost of goods sold (COGS):
$$\text{LTV} = \frac{\text{ARPU} \times \text{Gross Margin \%}}{\text{Customer Churn Rate (Monthly)}}$$
- **ARPU**: Average Revenue Per User/Account per month.
- **Gross Margin \%**: `(Revenue - Hosting/Payment/Support COGS) / Revenue`. For B2B SaaS, benchmark is 75%–85%; for e-commerce, 40%–60%.
- **Expansion-Adjusted LTV** (when Net Revenue Retention > 100%):
  $$\text{LTV} = \frac{\text{Initial ARPU} \times \text{Gross Margin \%}}{\text{Churn Rate} - \text{Expansion Rate}}$$

### C. CAC Payback Period (Cash Velocity)
Payback measures how many months of gross profit are required to recover the cash spent to acquire a customer:
$$\text{CAC Payback (Months)} = \frac{\text{Fully-Loaded CAC}}{\text{Monthly ARPU} \times \text{Gross Margin \%}}$$

### D. Channel Contribution Margin & Break-Even ROAS
Determine whether an individual acquisition channel is accretive:
$$\text{Contribution Margin} = \text{Attributed Net Revenue} - \text{COGS} - \text{Channel Ad Spend} - \text{Payment Gateway Fees}$$
$$\text{Break-Even ROAS} = \frac{1}{\text{Gross Margin \%}}$$
*Example*: At 70% Gross Margin, break-even ROAS is `1 / 0.70 = 1.43x`. Any campaign below 1.43x ROAS destroys cash on the first transaction.

## 2. Benchmark Health Scorecard

| Metric | Danger Zone (< Floor) | Target (Healthy) | Exceptional (> Ceiling) |
|---|---|---|---|
| **LTV : CAC Ratio** | `< 2.5x` (Burning capital) | `3.0x – 5.0x` (Sustainable scale) | `> 5.0x` (Under-investing in acquisition) |
| **B2B SaaS Payback** | `> 18 months` | `9 – 12 months` | `< 6 months` (Hyper-efficient) |
| **B2C / Self-Serve Payback** | `> 12 months` | `4 – 6 months` | `< 3 months` (Near-instant cash recycle) |
| **Gross Margin** | `< 65%` (SaaS) | `75% – 85%` | `> 88%` |
| **Net Revenue Retention (NRR)** | `< 90%` | `105% – 115%` | `> 125%` (Enterprise expansion) |

## 3. Worked Example: B2B SaaS Tier

Given:
- Monthly subscription: $200/month
- Gross Margin: 80% (Hosting + payment processing = $40/month)
- Monthly customer logo churn: 2.5% (Average lifetime = `1 / 0.025 = 40 months`)
- Total sales & marketing monthly spend: $40,000
- New customers closed per month: 25

Calculations:
1. **Fully-Loaded CAC**: `$40,000 / 25 = $1,600`
2. **Gross Margin ARPU**: `$200 * 0.80 = $160/month`
3. **LTV**: `$160 / 0.025 = $6,400`
4. **LTV : CAC**: `$6,400 / $1,600 = 4.0x` (Healthy scaling zone)
5. **CAC Payback**: `$1,600 / $160 = 10 months` (Meets the <12 month B2B benchmark)

## Critical Rules
1. Never report Blended CAC as an excuse for an unprofitable paid ad channel; paid campaigns must stand on their own Paid CAC.
2. Always deduct variable delivery and payment processing costs from revenue before computing LTV.
3. If churn exceeds 5% monthly, fix customer retention and onboarding before increasing acquisition spend.

## Verification Checklist
- [ ] CAC calculation includes fully-loaded personnel, agency, and tooling costs.
- [ ] LTV uses gross margin dollars rather than gross revenue.
- [ ] Payback period calculated against gross profit contribution per month.
- [ ] Break-even ROAS and contribution margin calculated for each paid channel.
- [ ] Baseline metrics compared against industry cohort benchmarks.

## Anti-Patterns
- NEVER use a single company-wide LTV across disparate customer segments (e.g. self-serve vs enterprise).
- NEVER assume lifetime is infinite when churn is low; cap lifetime at 36 or 60 months in financial models.
- NEVER scale marketing budgets based on top-line revenue when net contribution margin is negative.
