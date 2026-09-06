---
name: paid-campaigns
group: Paid
description: >-
  Structure, target, bid and optimise campaigns across Google, Meta, LinkedIn and X. Use when
  planning or optimizing Google, LinkedIn, or Meta ad campaigns.
---

# Paid Campaigns

Paid advertising campaigns across Google, Meta, LinkedIn, and X are predictable acquisition engines when governed by strict unit economics and algorithmic targeting. Paid acquisition fails when campaigns lack disciplined conversion tracking, bid beyond maximum allowable CAC ceilings, or fail to segment retargeting from cold prospecting.

## 1. Platform Selection & Intent Archetypes

Select the advertising platform that matches your audience's intent state:
- **Google Search (High Intent / Problem-Aware)**:
  - *Mechanism*: Bidding on exact user queries (e.g. "enterprise agent orchestration framework").
  - *Strategy*: Exact Match and Phrase Match keywords only; negative keyword lists to filter out job seekers ("jobs", "salary", "free").
- **LinkedIn Ads (B2B Account-Based Targeting / Firmographics)**:
  - *Mechanism*: Targeting by job title, company name, industry, and company headcount.
  - *Strategy*: High CPC ($8–$20); reserve strictly for high-ACV deals ($5,000+ ARR). Use Lead Gen Forms to reduce mobile conversion friction.
- **Meta Ads (Facebook & Instagram - Algorithmic Discovery)**:
  - *Mechanism*: Broad demographic targeting powered by pixel conversion data.
  - *Strategy*: Low CPC/CPM; ad creative is the targeting lever. Scale winning visual angles with Advantage+ campaign structures.

## 2. Campaign Structure & Funnel Segmentation
Never mix cold traffic and warm retargeting inside the same campaign:
- **Top of Funnel (TOF - Cold Prospecting - 70% Budget)**:
  - Audience: Lookalike audiences, broad algorithmic targeting, non-brand search keywords.
  - Objective: High-converting landing page traffic, free tool usage, trial signups.
- **Middle of Funnel (MOF - Engagement - 15% Budget)**:
  - Audience: Website visitors past 30 days, video viewers (>50% watch time), newsletter subscribers.
  - Objective: Case study reads, product demo views, interactive sandbox sessions.
- **Bottom of Funnel (BOF - High-Intent Retargeting - 15% Budget)**:
  - Audience: Pricing page visitors, uncompleted signups, trial users nearing expiration.
  - Objective: Overcome objections, offer live onboarding, trigger purchase.

## 3. Mathematical Bidding & CAC Ceilings
Calculate maximum allowable cost-per-click (Max CPC) before launching:
$$\text{Max CPC} = \text{Target CAC} \times \text{Landing Page Conversion Rate (\%)} \times \text{Lead-to-Customer Rate (\%)} $$
- *Example*:
  - Target CAC = $300
  - Visitor-to-Lead Conversion Rate = 5% (0.05)
  - Lead-to-Customer Conversion Rate = 20% (0.20)
  - $\text{Max CPC} = 300 \times 0.05 \times 0.20 = $3.00$
  - Any bid above $3.00 mathematically results in an unprofitable acquisition campaign.

## 4. Negative Keyword Lists (Google Search Hygiene)
Deploy universal negative keyword lists to prevent budget waste:
- Careers: `careers`, `jobs`, `internship`, `salary`, `glassdoor`, `resume`.
- Education: `course`, `tutorial`, `free book`, `pdf`, `how to learn`.
- Support: `customer service phone number`, `login`, `portal`, `headquarters`.

## Critical Rules
1. Never launch a paid campaign without verified conversion tracking (Google Enhanced Conversions, Meta CAPI) in place.
2. Separate brand search keywords from generic non-brand search into independent campaigns.
3. Pause any ad set that spends 2x target CAC without generating a single qualified conversion.

## Verification Checklist
- [ ] Conversion tracking pixels and server-side APIs verified in staging and production.
- [ ] Max allowable CPC calculated based on conversion rates and target CAC.
- [ ] Negative keyword lists applied to all Google Search ad groups.
- [ ] Cold prospecting separated cleanly from warm retargeting audiences.
- [ ] Ad copy and landing page headlines mirror target keyword intent.

## Anti-Patterns
- NEVER use Google Broad Match keywords without extensive negative keyword lists.
- NEVER scale daily campaign budgets by more than 20% every 48 hours (triggers ad network algorithmic re-learning).
- NEVER direct paid traffic to your generic homepage; send traffic to tailored, message-matched landing pages.
