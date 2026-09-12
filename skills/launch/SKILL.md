---
name: launch
last_reviewed: 2026-09-06
group: Distribution
description: >-
  Run a launch end to end: sequencing, assets, waitlist, Product Hunt and the HN day-of playbook.
  Use when orchestrating Product Hunt, Show HN, or major launch days.
---

# Launch

A software launch is a synchronized distribution event, not a single social media post. High-velocity launches choreograph pre-launch waitlist momentum, platform-native communities (Hacker News "Show HN" and Product Hunt), and real-time founder engagement into a concentrated 24-hour surge that overcomes initial algorithmic inertia.

## 1. Pre-Launch & Waitlist Sequencing

Build momentum before going public to guarantee day-one engagement:
- **T-14 Days (Waitlist Landing Page)**: High-converting hero copy, 30-second product demo video, email capture with referral incentives (e.g. move up the queue by sharing on X/LinkedIn).
- **T-7 Days (Beta Tester Mobilization)**: Invite early community members and power users into a private channel to test onboarding, find edge-case bugs, and prepare genuine day-of feedback.
- **T-2 Days (Asset Finalization)**: Freeze production deployments; stress-test database connection limits and CDN caches for 10x traffic spikes; verify automated transactional emails.
- **T-0 (Launch Hour)**: Synchronized push across email waitlist, Product Hunt, Hacker News, X/LinkedIn founder threads, and relevant subreddits.

## 2. Hacker News "Show HN" Playbook

Hacker News demands technical substance, intellectual honesty, and zero marketing puffery:

### A. Title Convention
- **Format**: `Show HN: [Product Name] – [Plain, factual description of what it does]`
- *Good*: `Show HN: Skillary – 277 agent skills with SQLite FTS5 search`
- *Fatal Anti-Pattern*: `Show HN: The revolutionary next-generation AI agent framework that changes everything` (downvoted or flagged immediately).

### B. Submission Text / Maker Opener
Include a top-level text body covering four required elements:
1. **Why I Built This**: The specific developer pain or technical constraint that led to creating it.
2. **How It Works**: Architecture, languages used, key algorithms, and tradeoffs (e.g. "We chose SQLite FTS5 over vector databases for local-first zero-telemetry search").
3. **Trade-offs & Constraints**: State clearly what the tool does NOT do yet. Engineering transparency disarms skeptics.
4. **Call for Feedback**: Ask specific architectural or UX questions: "Curious how you handle branch protection in your CI workflows?"

### C. Algorithmic Hygiene & Rules
- **NEVER solicit upvotes**: Sending links to friends asking for upvotes or mass-linking in Slack triggers the HN vote-ring detector, permanently penalizing the post.
- **Engage in the Comments**: Reply to every technical question within 15 minutes. Treat criticisms as valid engineering data.

## 3. Product Hunt Launch Mechanics

### A. Metadata Specifications
- **Name**: Product Name.
- **Tagline**: Strictly under 60 characters. Benefit-focused, zero buzzwords (no "AI-powered", "revolutionary", "seamless").
- **Visual Assets**:
  - Thumbnail: Clean 240x240px GIF or logo.
  - Gallery: 1 animated 30-second demo GIF/video + 4–5 screenshots with legible callouts (1270x760px).
- **Pricing Tag**: Declare Free / Freemium / Paid accurately.

### B. Day-of Schedule (Pacific Time)
- **00:01 AM PT**: Product goes live on PH.
- **00:05 AM PT**: Maker publishes first comment: origin story, key features, discount/free-tier code for the community.
- **07:00 AM PT**: Send email blast to the pre-launch waitlist announcing the launch.
- **09:00 AM PT**: Publish founder launch thread on X and LinkedIn with short demo clip.

## 4. Launch Day War Room Checklist
- [ ] Error tracking (Sentry) and server CPU/memory dashboards open on a dedicated screen.
- [ ] Welcome emails, transactional signup tokens, and payment webhooks tested in production.
- [ ] Live chat or dedicated support channel monitored with <5 minute response target.

## Critical Rules
1. Never solicit artificial upvotes on Hacker News or Product Hunt; organic user curiosity and real community engagement are the only sustainable vectors.
2. Ensure the product has an unauthenticated interactive playground, interactive demo video, or open repository link; gating behind a sales call destroys launch conversion.
3. Fix critical blocking onboarding bugs immediately during launch day; push hotfixes without breaking active sessions.

## Verification Checklist
- [ ] Waitlist email notification drafted, tested, and scheduled.
- [ ] "Show HN" title and technical explainer text drafted with clear limitations stated.
- [ ] Product Hunt gallery images, demo GIF, and maker comment prepared.
- [ ] Infrastructure capacity verified to sustain 10x traffic surge without crashing.
- [ ] Analytics tracking events verified across landing page, signup, and activation.

## Anti-Patterns
- NEVER launch on a Friday or weekend if targeting business software buyers; launch Tuesday through Thursday.
- NEVER argue defensively with critics in public comment sections; thank them for the critique and explain the technical rationale.
- NEVER launch without testing the entire signup and onboarding funnel on mobile devices.
