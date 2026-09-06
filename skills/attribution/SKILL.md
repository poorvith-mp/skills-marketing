---
name: attribution
group: Measurement
description: >-
  Work out which channels actually drive revenue and reconcile conflicting platform numbers. Use
  when tracking UTM campaigns, referral sources, or conversion loops.
---

# Attribution

Attribution is the science of determining which marketing touchpoints drive business revenue. Platform-reported metrics (Meta Ads Manager, Google Ads) routinely double-count conversions due to overlapping 7-day click and 1-day view attribution windows. A reliable attribution framework combines first-party tracking, blended marketing efficiency ratios (MER), and lightweight multi-touch models.

## 1. The Platform Overlap Problem & Multi-Counting
When a prospect clicks a Google Search ad, views a LinkedIn ad, and later converts via an email link:
- Google Ads claims 100% credit for the sale.
- LinkedIn Ads claims 100% credit for the sale.
- Meta claims 100% credit if they saw an Instagram ad in the last 24 hours.
*Result*: Platform dashboards report 3 conversions for a single customer transaction.

## 2. Core Attribution Methodologies

### A. First-Touch Attribution
- **Credit**: 100% of revenue attributed to the first recorded marketing touchpoint.
- **Best Used For**: Measuring top-of-funnel discovery channels (content, PR, organic search, early brand ads).
- **Weakness**: Completely ignores mid-funnel nurture and closing channels.

### B. Last-Touch (Last Non-Direct Click) Attribution
- **Credit**: 100% of revenue attributed to the final campaign prior to conversion (excluding direct visits).
- **Best Used For**: Evaluating conversion-focused channels (retargeting, promotional emails, brand search).
- **Weakness**: Starves top-of-funnel awareness channels of budget.

### C. Blended Marketing Efficiency Ratio (MER) — The Source of Truth
Avoid getting lost in conflicting click attribution models by tracking aggregate financial return:
$$\text{MER} = \frac{\text{Total Gross Revenue}}{\text{Total Marketing Spend (All Channels)}}$$
$$\text{Blended CAC} = \frac{\text{Total Marketing \& Sales Spend}}{\text{Total New Customers Acquired}}$$
*Rule*: If total ad spend increases by $20,000 and total top-line revenue only increases by $5,000, your incremental ROAS is negative, regardless of what platform dashboards report.

## 3. First-Party Tracking Infrastructure
Capture UTM parameters and click IDs on initial site visit and persist them in user session cookies:
1. Store `utm_source`, `utm_medium`, `utm_campaign`, `gclid`, and `fbclid` in `localStorage` or first-party cookie for 30 days.
2. Upon user registration or checkout, send these persisted attribution parameters into your backend database alongside the user profile.
3. Send server-to-server conversion events (Meta Conversions API - CAPI, Google Enhanced Conversions) matching on hashed email and transaction IDs.

## Critical Rules
1. Never judge marketing channel profitability on in-platform ROAS alone without cross-referencing first-party CRM data.
2. Store the original first-touch attribution parameters permanently on the user record in your production database.
3. Exclude branded search clicks from paid acquisition ROAS calculations to avoid taking credit for organic demand.

## Verification Checklist
- [ ] First-party attribution script captures and persists UTM parameters across multi-page sessions.
- [ ] Backend database records first-touch and last-touch parameters on the user profile.
- [ ] Server-side conversion tracking (Meta CAPI / Google Enhanced Conversions) configured.
- [ ] Marketing Efficiency Ratio (MER) calculated weekly against aggregate spend.
- [ ] Deduplication verified across ad platform conversion tags.

## Anti-Patterns
- NEVER rely on 1-day view-through attribution to justify scaling paid social budgets.
- NEVER allow paid branded search to claim credit for users who already intended to visit the site.
- NEVER change attribution models retroactively without recalculating historical channel baselines.
