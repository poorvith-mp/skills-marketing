---
name: analytics-setup
group: Measurement
description: >-
  Install and QA tracking: event plan, UTMs, GA4/GTM and conversion tracking. Use when configuring
  GA4, PostHog, event tracking, or conversion goals.
---

# Analytics Setup

Analytics is the measurement instrumentation behind capital and engineering allocation. Analytics fails when tracking is implemented haphazardly without a unified tracking schema, leading to conflicting metrics between product and marketing. A production analytics stack requires a formalized event schema, strict UTM parameter hygiene, server-side tracking resilience, and automated QA verification.

## 1. The Tracking Plan Schema
Never allow engineers or marketers to invent arbitrary event names. Enforce an Object-Action naming convention:

| Event Name | Trigger Moment | Mandatory Properties |
|---|---|---|
| `account_signup_completed` | User finishes registration | `signup_method` (email, google, github), `referral_source` |
| `onboarding_step_completed` | User finishes an onboarding milestone | `step_index`, `step_name`, `time_spent_seconds` |
| `project_created` | User creates first project/asset | `project_type`, `template_used`, `is_first_project` |
| `subscription_plan_selected` | User clicks checkout on pricing | `plan_tier`, `billing_interval` (annual/monthly), `mrr_value` |
| `payment_succeeded` | Gateway processes charge | `transaction_id`, `amount_usd`, `plan_tier`, `is_upgrade` |

## 2. UTM Parameter Hierarchy & Hygiene
Inconsistent UTM tagging breaks attribution models. Enforce lowercase, hyphenated URL parameters:
- **`utm_source`**: The platform sending the traffic (`google`, `linkedin`, `twitter`, `newsletter`).
- **`utm_medium`**: The marketing channel type (`cpc`, `organic-social`, `email`, `referral`, `affiliate`).
- **`utm_campaign`**: The specific strategic campaign (`q3-launch`, `developer-tools-retargeting`).
- **`utm_content`**: The specific ad creative or link variant (`video-demo-v1`, `hero-cta-button`).
- *Golden Rule*: Never use UTM tags on internal site links; internal UTMs overwrite original acquisition sources and destroy session attribution.

## 3. Tool Architecture: Client vs. Server-Side
- **Client-Side Analytics (PostHog / GA4 via GTM)**:
  - Best for UI interaction tracking: clicks, scroll depth, form field abandonment, and session replays.
  - Vulnerability: Blocked by 25%–40% of technical users using ad-blockers and privacy extensions.
- **Server-Side Analytics (Webhook / Backend Events)**:
  - Mandatory for source-of-truth business metrics: signups, billing events, subscription cancellations.
  - Dispatched directly from application backend code to analytics endpoints, bypassing ad-blockers entirely.

## 4. Analytics QA Verification Checklist
Before deploying tracking to production:
1. Open browser DevTools Network tab filtered by analytics endpoint (`google-analytics.com/g/collect` or `posthog.com/e/`).
2. Trigger the event in a staging environment.
3. Verify that the event name matches the tracking plan verbatim.
4. Verify that property payloads contain correct data types (integers as numbers, not strings).
5. Confirm that personal identifiable information (PII such as passwords, raw credit card numbers) is never captured.

## Critical Rules
1. Every conversion event must fire exactly once per transaction; deduplicate using unique transaction IDs.
2. Financial and revenue metrics must reconcile with Stripe/banking records within a 2% variance.
3. Never store passwords, unencrypted emails, or API tokens in analytics event properties.

## Verification Checklist
- [ ] Formal tracking plan document approved by engineering and marketing.
- [ ] Consistent lowercase UTM parameter taxonomy established and documented.
- [ ] Server-side tracking implemented for all critical revenue and account creation events.
- [ ] Event deduplication verified using transaction IDs.
- [ ] Cookie consent banner integrated with Google Tag Manager Consent Mode.

## Anti-Patterns
- NEVER use generic event names like `button_click` without identifying the specific component and context.
- NEVER track revenue on the client-side `thank-you` page alone; network dropouts and ad-blockers miss 15% of transactions.
- NEVER allow team members to create new UTM parameters without updating the central campaign tracking sheet.
