---
name: lifecycle-messaging
last_reviewed: 2026-09-06
group: Lifecycle
description: >-
  Design automated email, SMS and push flows: welcome, nurture, cart, win-back and broadcast. Use
  when writing onboarding drip emails, feature updates, or re-engagement.
---

# Lifecycle Messaging

Lifecycle messaging is automated behavioral communication across Email, SMS, and In-App Push notifications. High-retention messaging engages users at explicit lifecycle inflection points (welcome onboarding, activation nudges, milestone celebrations, re-engagement, churn prevention) triggered by product behavioral data rather than arbitrary calendar dates.

## 1. The 5 Core Lifecycle Communication Sequences

### A. The Onboarding / Welcome Sequence (Days 1–7)
- **Email 1 (Immediate upon signup)**: Personal founder welcome. Reinforce the primary benefit; provide a single direct link to complete the first project.
- **Email 2 (Day 2 - Behavioral Trigger)**:
  - *If activated*: Congratulate and show the next advanced capability.
  - *If not activated*: Address common setup friction; offer 2-minute video walkthrough.
- **Email 3 (Day 4)**: Case study highlighting how a peer customer achieved a specific quantifiable outcome.
- **Email 4 (Day 7)**: Offer direct live support or invite to developer community.

### B. Behavioral Activation Nudges
Triggered exclusively by inactivity at key funnel stages:
- *Inactivity Trigger*: User signed up 3 days ago but has not added an API key or deployed a service.
- *Message Copy*: Short, helpful, plain-text email from a real team member: "Noticed you started setup on [Project] — did you hit any friction with our CLI? Happy to help unblock."

### C. Milestone & Progress Celebrations
Reinforce product habituation and the endowment effect:
- "You just processed your 10,000th background event! Here is your 30-day performance summary."
- Provide shareable assets to turn milestone accomplishments into organic social advocacy.

### D. Cart Abandonment & Upgrade Nudges
- Triggered when a user views the pricing page or clicks "Upgrade to Pro" without completing checkout.
- Send a contextual reminder 4 hours later addressing common billing questions, refund policies, and team seat options.

### E. Inactivity Win-Back Cadence (Days 30, 60, 90)
- **Day 30**: Highlight major new features and performance improvements shipped since their last login.
- **Day 60**: Offer an account credit or temporary free tier extension to re-test the platform.
- **Day 90**: Sunset notification: clean up inactive data and politely close the communication loop.

## 2. Technical Infrastructure & Event-Driven Architecture
- Connect your product database to your lifecycle engine (Customer.io, Resend, Braze) via real-time webhooks.
- Discard static email list blasts; segment users dynamically based on real-time event attributes (`has_deployed_production == false`, `days_since_last_login > 14`).

## 3. Channel Selection Hierarchy
- **In-App Notification**: Best for immediate, in-context product alerts and task completions.
- **Email**: Best for asynchronous updates, milestone digests, and deep technical explainers.
- **SMS / Push**: Reserve strictly for urgent, mission-critical events (system downtime, security alerts, payment failure). Never use SMS for promotional marketing spam.

## Critical Rules
1. Never send an onboarding setup email to a user who has already completed that step in the product.
2. Use plain-text or clean, minimalist HTML email templates; heavy marketing graphics trigger Gmail Promotions tab placement.
3. Every automated email must contain a 1-click unsubscribe link that takes effect immediately.

## Verification Checklist
- [ ] Lifecycle messaging mapped to explicit user behavioral events, not calendar schedules.
- [ ] Onboarding sequence branches dynamically based on user activation status.
- [ ] Plain-text sender formatting verified for inbox deliverability.
- [ ] Event webhooks tested between production database and email automation platform.
- [ ] Unsubscribe mechanisms compliant with CAN-SPAM and GDPR requirements.

## Anti-Patterns
- NEVER blast daily promotional emails to unactivated users; aggressive volume accelerates unsubscribes.
- NEVER send automated lifecycle emails from a `noreply@domain.com` address; allow users to reply directly.
- NEVER ignore email deliverability metrics; keep spam complaint rates strictly below 0.1%.
