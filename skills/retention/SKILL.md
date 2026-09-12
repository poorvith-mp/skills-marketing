---
name: retention
last_reviewed: 2026-09-06
group: Lifecycle
description: >-
  Cut churn with cancel flows, save offers, dunning, exit surveys and account health signals. Use
  when diagnosing churn, building retention loops, or cohort analysis.
---

# retention

## Core Philosophy
Customer acquisition without retention is a treadmill to company failure. If you lose 5% of your customer base each month, you must replace 46% of your revenue every year just to stay flat. True retention is not achieved through aggressive cancellation barriers; it is driven by deep workflow habituation, early proactive health monitoring, dynamic save offers, and automated involuntary churn recovery.

---

## 4-Step Retention Engineering Framework

### Step 1: Churn Taxonomy & Telemetry Instrumentation
1. **Classify Churn Sources**:
   - *Involuntary Churn (Payment Failures)*: Typically 20–40% of total SaaS churn (expired cards, bank declines, fraud flags).
   - *Voluntary Churn (Cancellations)*: Customers actively requesting account closure or subscription termination.
2. **Cohort Retention Curves**:
   - Plot user and revenue retention by signup cohort across Months 1, 3, 6, 12.
   - Benchmark against target: Healthy B2B SaaS requires $> 85\%$ annual logo retention and $> 105\%$ Net Revenue Retention (NRR).
3. **Health Score Signals**:
   - Calculate composite account health scores (0–100):
     - Frequency of key action execution (e.g. 5 team logins/week).
     - Integration connectivity status (e.g. webhook still active).
     - Support ticket volume and sentiment.
     - Drop in daily active usage $> 40\%$ over 14 days flags account as "At Risk".

### Step 2: Automated Involuntary Churn Recovery (Dunning)
1. **Pre-Dunning Notifications**:
   - Detect cards expiring within 14 days and prompt update via in-app banner.
2. **Smart Retries & Cadence**:
   - Use smart retry logic (Stripe Smart Retries or exponential retry on days 1, 3, 5, 8).
   - Retry during standard banking business hours (9:00 AM local time).
3. **Communication Sequence**:
   - *Day 1*: Subtle in-app notification: "Update payment method to maintain uninterrupted service."
   - *Day 3*: Email 1 (Transactional & polite): "Payment issue with your account."
   - *Day 7*: Email 2 (Urgent): "Service interruption scheduled in 48 hours."
   - *Day 14*: Account moves to grace period (read-only mode, data preserved for 30 days).

### Step 3: Cancellation Flow & Dynamic Save Strategy
1. **Friction-Free Cancellation with Data Gathering**:
   - Never force users to call or email support to cancel; self-serve cancellation is mandatory.
   - Multi-step structured exit survey:
     - 1. Reason for leaving (Pricing, Missing Feature, Project Finished, Bugs, Switching to Competitor).
     - 2. Specific qualitative feedback input.
2. **Dynamic Save Offers (Reason-Matched)**:
   - *Finished Project / Seasonal*: Offer 1-click subscription pause for 1–3 months (freezing billing, saving data).
   - *Too Expensive*: Offer a temporary 50% discount for 3 months or automated downgrade to a lower tier.
   - *Missing Feature*: Connect instantly with a technical founder or route to roadmap voter.
3. **Graceful Exit**:
   - Confirm cancellation immediately, email receipt, and outline export/data-retention timelines (e.g., "Your data is safe for 60 days").

### Step 4: Executive Re-Engagement & Win-Back Loops
1. **Champion Turnover Protocol**:
   - Monitor key account executive bounce backs (e.g., primary contact left the company).
   - Automatically trigger an executive check-in to secondary admins.
2. **Win-Back Cadence**:
   - Re-contact canceled accounts 60–90 days post-churn only when a major feature they explicitly requested is deployed to production.

---

## Deliverable Format: Retention Playbook & Dunning Matrix (`RETENTION-PLAYBOOK.md`)

```markdown
# Retention & Churn Reduction Playbook: [Product Name]

## 1. Baseline Metrics & Churn Diagnostics
- **Monthly Gross Logo Churn**: [Current %] (Target: < 1.5%)
- **Net Revenue Retention (NRR)**: [Current %] (Target: > 110%)
- **Involuntary vs Voluntary Ratio**: [Split, e.g. 35% involuntary / 65% voluntary]

## 2. Involuntary Churn Dunning Sequence
| Day | Trigger Event | Channel | Action / Copy Message |
|---|---|---|---|
| Day 0 | Initial Charge Decline | Webhook | Retry in 24h; silent |
| Day 1 | Second Decline | In-App Banner | "Please update billing info" |
| Day 4 | Third Decline | Email 1 | "Payment failed - update card" |
| Day 8 | Fourth Decline | Email 2 + In-App Modal | "Account locking in 48 hours" |
| Day 14 | Final Failure | System | Soft downgrade to Read-Only |

## 3. Self-Serve Cancellation Flow & Save Logic
- **Exit Survey Options**: [List of 5 core reasons]
- **Dynamic Save Offers**:
  - If *Pricing*: Offer [Pause for 60 days / 50% off 2 months]
  - If *Technical Bug*: Prompt [Instant priority ticket to engineering]
- **Data Retention Period**: [e.g. 60 days post-cancellation]

## 4. Account Health Scoring Rubric
- **Green (Score 80-100)**: [Specific usage thresholds]
- **Yellow (Score 50-79)**: [Action drop triggers]
- **Red (Score < 50)**: [Trigger automated CSM check-in]
```

---

## Worked Example: SaaS Churn Intervention

- **Diagnosis**: 40% of churn cited "temporary reduction in project volume".
- **Intervention**: Added a 1-click "Pause Account for 60 Days" option in the cancellation flow.
- **Result**: 31% of users who clicked cancel selected the Pause option instead; 64% of paused accounts resumed billing after 60 days, cutting gross monthly churn from 4.8% to 3.2%.

---

## Verification Checklist

- [ ] Self-serve cancellation is available in-app with zero mandatory sales calls.
- [ ] Dunning sequence includes automated smart card retries and multi-touch email notifications.
- [ ] Canceled users are offered a 1-click Pause option rather than binary account deletion.
- [ ] Telemetry tracks at least 3 early health degradation signals (e.g. login drop, webhook failures).
- [ ] Data retention and export guidelines are explicitly stated upon cancellation confirmation.

---

## Anti-Patterns

- **Roach Motel Cancellation**: Hiding the cancellation button or requiring phone calls during business hours.
- **Immediate Data Destruction**: Purging user data the second a subscription is canceled, destroying win-back potential.
- **Ignoring Involuntary Churn**: Blaming product-market fit when 30% of cancellations are simply expired credit cards.
