---
name: partnerships
group: Earned and partnerships
description: Find and structure creator, sponsor and co-marketing deals: vetting, briefs, and ROI. For reseller channels, see alliances. Use when structuring co-marketing or ecosystem integrations.
---

# partnerships

## Core Philosophy
Partnerships are not vanity press releases or hollow co-marketing badges. A technical or strategic partnership only creates enterprise value if it establishes a recurring, bidirectional distribution loop or removes a critical adoption blocker. Every partnership must be anchored in joint workflow utility: mutual customer overlap, seamless API-level integration, and clear economic alignment between partner sales teams.

---

## 4-Stage Partnership Execution Framework

### Stage 1: Ecosystem Mapping & Opportunity Sizing
1. **Overlap Analysis**:
   - Query existing customer CRM accounts against partner ecosystems.
   - Benchmark mutual accounts: Target a minimum of 20 shared enterprise customers or 100 mutual SMB accounts before committing engineering resources.
2. **Partnership Type Classification**:
   - *Technology/Integration*: Mutual API hooks, data synchronization, certified marketplace app (e.g. Slack, GitHub, Linear app).
   - *Channel/Reseller*: Agency or MSP partners embedding your software into their service contracts for 15–25% recurring margin.
   - *Co-Marketing/Alliance*: Joint webinars, co-authored industry benchmarks, and bundle offerings.
3. **Partner Prioritization Matrix**:
   - Score prospective partners on: API Completeness (1–5), Audience Alignment (1–5), Partner Marketplace Traffic (1–5), and Developer Portal Friction (1–5).

### Stage 2: Technical Integration Architecture & Scoping
1. **Auth & Security**:
   - Implement OAuth 2.0 with minimal required permission scopes.
   - Establish webhook signature verification (HMAC-SHA256) and mutual TLS for enterprise endpoints.
2. **Bidirectional Data Flow**:
   - Define exact sync cadences: real-time webhooks for event streaming, batch polling for historical backfills.
   - Design idempotent event handlers with exponential backoff retry logic.
3. **App Directory Listing Specifications**:
   - Standardize listing assets: 128x128px icon, 1200x630px showcase banner, 3-minute Loom walkthrough, and end-to-end setup guide.

### Stage 3: Joint Go-to-Market (GTM) Playbook
1. **Tier 1 Launch Deliverables**:
   - Partner marketplace publication with deep-link installation flow.
   - Joint press release or co-authored technical blog post with working code snippets.
   - Dedicated landing page (`/integrations/{partner-name}`) optimized for joint search intent.
2. **Sales Enablement & Field Alignment**:
   - Create a 1-page "Better Together" cheat sheet for both sales teams:
     - 3-sentence positioning: Why customer needs both tools together.
     - Common buyer objections and answers.
     - Customer referral deal registration link.
3. **Incentive Alignment**:
   - Offer reciprocal deal registration credits or 10–20% first-year ACV referral bonuses for partner account executives.

### Stage 4: Governance & Expansion
1. **Health Metrics Tracking**:
   - Track: Monthly Active Connected Accounts (MACA), integration error rates, churn delta between integrated vs non-integrated cohorts.
2. **Tier Progression**:
   - Move from Certified App -> Featured Partner -> Premier Strategic Alliance based on active install thresholds.

---

## Deliverable Format: Partnership Blueprint (`PARTNERSHIP-SPEC.md`)

```markdown
# Strategic Partnership Specification: [Partner Name]

## 1. Executive Summary & Joint Value Thesis
- **Target Audience**: [Joint ICP description]
- **Core Problem Solved**: [Specific friction eliminated by integration]
- **Mutual Customer Overlap**: [Count or % overlap]

## 2. Technical Scope
- **Integration Type**: [OAuth App / Webhook Receiver / Bi-directional Sync]
- **Authentication**: [OAuth2 / API Key / Webhook Secret]
- **Data Entities Exchanged**: [Entity A -> Entity B mapping]
- **Rate Limits & Failover**: [Requests/min, retry policy]

## 3. Joint Go-To-Market Plan
- **Launch Date**: [Target date]
- **Marketplace Listing**: [URL / Submission status]
- **Co-Marketing Assets**: [Blog post, webinar, social rollout, email blast]
- **Field Enablement**: [Joint one-pager distribution schedule]

## 4. Economic Terms & Deal Registration
- **Revenue Share / Referral Fee**: [e.g., 15% first year ARR]
- **Deal Registration Flow**: [Form link, tracking mechanism]
```

---

## Worked Example: Developer Tool Integration with Linear

- **Joint Value Proposition**: Automatically sync failed production test suites directly into Linear issues with stack traces, reproduction steps, and assigned code owners.
- **Economic Model**: Zero-fee mutual integration; shared GTM via Linear Integration Directory and launch thread.
- **Technical Flow**: Webhook on CI test failure -> Transform payload -> Linear GraphQL API `issueCreate` mutation -> Bi-directional status sync via Linear webhook.
- **Results Target**: 300 active connected workspaces within 60 days of directory listing.

---

## Verification Checklist

- [ ] Mutual customer overlap verified with at least 15 active paying accounts.
- [ ] OAuth 2.0 flow adheres to least-privilege scope requirements.
- [ ] Webhook receiver includes signature verification and replay attack protection.
- [ ] Co-marketing assets include 1 joint case study, 1 walkthrough demo video, and 1 setup doc.
- [ ] Both sales teams briefed with a 1-page "Better Together" battlecard.

---

## Anti-Patterns

- **Press Release Only**: Announcing a partnership without a functioning, production-ready integration.
- **Asymmetric Commitment**: Spending engineering months on an integration where the partner refuses to grant marketplace distribution.
- **Over-Scoping V1**: Trying to synchronize all database entities rather than the core primary event workflow.
