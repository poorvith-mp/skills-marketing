---
name: referrals
group: Earned and partnerships
description: >-
  Design referral, affiliate and ambassador programmes with incentives and payout mechanics. Use
  when designing customer referral loops, affiliate programs, or invites.
---

# referrals

## Core Philosophy
A referral or affiliate program cannot fix an unretentive product. Referral programs work exclusively as an amplification loop for products that already demonstrate high customer satisfaction (NPS > 50) and clear organic word-of-mouth. To prevent fraud, low-quality leads, and margin erosion, incentives must be double-sided, economically bounded, and triggered precisely at the customer's peak emotional moment of value.

---

## 4-Stage Referral Loop Architecture

### Stage 1: Economic Modeling & Incentive Engineering
1. **Unit Economics Guardrails**:
   - Set Maximum Referral Reward $\le 0.30  imes text{Customer Acquisition Cost (CAC)}$.
   - Example: If Blended CAC is $300, total referral payout must not exceed $90 across both parties.
2. **Double-Sided Incentive Structures**:
   - *Cash/Credit*: Give $50 account credit to referrer; Give $50 onboarding credit to referee.
   - *Feature/Quota Unlocks*: Give 5,000 free API calls or 1 month of premium features to both sides.
   - *Status/Access*: Invite-only early beta access or VIP community tier for 3 successful invites.
3. **Affiliate vs Customer Referral**:
   - *Customer Referrals*: Account credits and feature upgrades (keeps incentives aligned with product usage).
   - *Affiliate Program*: Cash commissions (15–25% recurring for 12 months) for content creators, agencies, and consultants.

### Stage 2: Trigger Timing & Journey Placement
1. **The "Peak Joy" Trigger Moment**:
   - Never ask for a referral during onboarding or setup.
   - Trigger referral prompts immediately after value realization:
     - After completing their first successful build or export.
     - After resolving a customer support ticket with a 5-star rating.
     - Immediately after reaching a quantifiable milestone (e.g., "You saved 10 hours this week").
2. **In-Product Real Estate**:
   - Dedicated navigation item: "Share & Earn $50".
   - Non-intrusive modal or banner at milestone achievements.
   - Transactional email footer: "Give your team $25 off".

### Stage 3: Attribution, Tracking & Fraud Mitigation
1. **Tracking Infrastructure**:
   - Generate unique, deterministic referral slugs per user (`app.domain.com/r/{user_slug}`).
   - Store referral cookie with a 30-to-60 day attribution window.
   - Implement server-side attribution logging on signup and conversion events.
2. **Fraud Prevention Gates**:
   - Disallow referral payouts for accounts sharing IP addresses, credit cards, or device fingerprints.
   - Implement delayed reward maturation: Hold payouts for 30 days until the referee passes the refund/chargeback window.
   - Require referee to complete a paid transaction or minimum active threshold before rewarding referrer.

### Stage 4: Program Optimization & Viral Loops
1. **Viral Coefficient ($K$-Factor) Calculation**:
   $$K = i  imes c$$
   - Where $i$ = Number of invites sent per active user, and $c$ = Conversion rate of each invite.
   - If $K > 1$, the product achieves viral organic growth.
2. **Friction Reduction in Sharing**:
   - Provide 1-click native copy to clipboard with pre-written social and email share copy.
   - Generate automated Open Graph preview cards showing the referee's personalized discount.

---

## Deliverable Format: Referral Program Specification (`REFERRAL-PROGRAM-SPEC.md`)

```markdown
# Customer Referral Program Specification: [Program Name]

## 1. Incentive Economics & Rules
- **Referrer Reward**: [e.g. $50 account credit / 1 free month]
- **Referee Reward**: [e.g. 20% off first 3 months]
- **Maximum Payout / User**: [Cap, e.g. $500/year]
- **Economic Limit**: [Referral cost as % of CAC]

## 2. Trigger Moments & UI Placements
- **Primary Trigger**: [Exact in-product milestone, e.g. 10th workflow run]
- **UI Placements**: [Sidebar widget, settings tab, invoice email footer]
- **In-App Modal Copy**: [Headline, body, primary CTA button text]

## 3. Fraud & Payout Policies
- **Maturation Window**: [e.g. 30 days post-conversion]
- **Self-Referral Check**: [IP, fingerprint, credit card hash match]
- **Minimum Spend**: [Referee must spend minimum $X to trigger credit]

## 4. Viral Sharing Assets
- **Default Share URL**: `https://[domain].com/r/{referral_code}`
- **Pre-Written Email Copy**: [Subject and body]
- **Social Share Text**: [Default tweet/LinkedIn post copy]
```

---

## Worked Example: B2B Developer Tool Referral Program

- **Incentive**: Give $100 cloud compute credits to both referrer and referee.
- **Trigger**: Displayed in-app immediately after user executes 100 successful cloud builds.
- **Fraud Rule**: Payout releases only when referee spends $50 of real cash or runs 50 builds across 14 distinct days.
- **Resulting Metric**: 18% of referred users convert to paid vs 6% baseline organic rate; $K$-factor increased from 0.12 to 0.41.

---

## Verification Checklist

- [ ] Total referral incentive cost does not exceed 30% of target blended CAC.
- [ ] Referral prompt is triggered strictly after value realization, not during onboarding.
- [ ] Tracking uses durable cookies (30–60 days) and server-side conversion webhooks.
- [ ] Fraud safeguards block self-referrals and shared billing profiles.
- [ ] 1-click sharing copy is pre-written and includes dynamic discount preview.

---

## Anti-Patterns

- **Early Begging**: Showing referral popups before the user has completed a single core workflow.
- **Asymmetric One-Sided Rewards**: Rewarding the referrer with cash while offering zero incentive to the person being invited.
- **Uncapped Vulnerabilities**: Allowing bad actors to farm thousands in credits using throwaway email domains.
