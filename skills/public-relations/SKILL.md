---
name: public-relations
group: Earned and partnerships
description: >-
  Find journalists, pitch stories, newsjack and answer reporter requests. Use when pitching tech
  journalists, press releases, or earned media.
---

# public-relations

## Core Philosophy
Modern tech PR is not sending generic press releases over wire services for $1,500. Journalists, newsletter curators, and tech editors are overwhelmed with low-effort pitches. High-impact PR is built on three pillars: breaking newsworthy business facts, sharing proprietary primary data studies, and rapid newsjacking of macro-trends with direct, concise commentary.

---

## 4-Step Technical PR Execution Playbook

### Step 1: Newsworthiness & Angle Engineering
1. **The 3 Legitimate PR Hooks**:
   - *Primary Data Reports*: Analyze anonymized product data to publish unique industry benchmarks (e.g. "We analyzed 10M API calls: 40% of microservices fail on token timeouts").
   - *Hard Business Milestones*: Funding rounds with disclosed amounts, major Tier-1 customer acquisitions, or open-source milestone adoption (10k GitHub stars).
   - *Counter-Intuitive POV / Newsjacking*: Injecting contrarian, authoritative perspectives into a breaking news cycle (e.g., outage post-mortems, regulatory changes).
2. **The Journalist Value Equation**:
   - Ask: "Why would their readers click this without caring about our company?" If the story only benefits you, it is an ad, not news.

### Step 2: Targeted Media List & Relationship Mapping
1. **Curate a Precision List (25–40 Contacts)**:
   - Identify journalists who actively write about your niche (TechCrunch, The Verge, Wired, VentureBeat, Ars Technica, or specialized Substacks/newsletters).
   - Verify recent articles: Ensure they published a story on your exact sub-topic within the last 45 days.
2. **Dossier Data Fields**:
   - Journalist Name, Publication, Recent Relevant Article URL, Beat Focus, Preferred Pitch Channel (Email vs X/Twitter DMs), and Timezone.

### Step 3: The Cold Pitch Crafting (Under 150 Words)
1. **Subject Line Rules**:
   - Format: `[STORY / DATA]: {Specific compelling finding in <= 8 words}`
   - Avoid: "PR Announcement", "Exclusive Partnership", or hyperbolic fluff.
2. **Pitch Anatomy**:
   - *Lede (1 sentence)*: Direct hook referencing their recent coverage or breaking trend.
   - *The Core Finding / Angle (2–3 bullet points)*: High-impact facts with data points.
   - *The Offer (1 sentence)*: Exclusive access, raw dataset, or 15-minute executive interview.
   - *Clear Embargo terms*: Specify exact date, time, and timezone if news is under embargo.

### Step 4: Press Kit & Distribution Orchestration
1. **Clean Press Kit Repository**:
   - Host assets on a public, non-gated link (Notion page or GitHub repo):
     - High-resolution founder headshots (transparent and studio backgrounds).
     - Product screenshots with real data (no blurry mockups).
     - Executive quotes cleared for publication.
     - 1-page company factsheet (founding date, funding, metrics, HQ).
2. **Day-of Launch Execution**:
   - Send embargo lifts at 6:00 AM ET.
   - Coordinate internal executive social posts to amplify the story simultaneously.

---

## Deliverable Format: PR Campaign Kit (`PR-PITCH-KIT.md`)

```markdown
# PR Campaign Kit: [Campaign Title]

## 1. Story Angle & Core Hook
- **Story Type**: [Proprietary Data / Milestone / Newsjacking]
- **Headline**: [Proposed journalistic headline]
- **Core Thesis**: [1-2 sentences on why this matters right now]

## 2. Media Pitch Email
**Subject**: [DATA]: 68% of enterprise engineering teams fail SOC 2 continuous audit checks

Hi [First Name],

Read your piece on [Recent Article Topic]. Given your coverage of compliance automation, thought you'd find this new data compelling:

We analyzed anonymized infrastructure telemetry across 450 engineering organizations and found:
- 68% of continuous SOC 2 audit checks fail due to misconfigured AWS IAM roles.
- Average time to remediate an active policy violation is 26 days.
- Teams with automated drift detection remediate in under 4 hours.

Full anonymized dataset and benchmark report attached. Happy to provide an exclusive look or connect you with our CTO for technical commentary if you're interested.

Best,
[Your Name]

## 3. Media Target Roster
| Name | Publication | Recent Article | Beat | Contact Email |
|---|---|---|---|---|
| [Reporter A] | [Tech Outlet] | [Link] | Cloud Infra | [Email] |
| [Reporter B] | [Newsletter] | [Link] | DevSecOps | [Email] |

## 4. Press Kit Link
- **Press Assets**: [Clean URL with headshots, screenshots, and fact sheet]
```

---

## Worked Example: Open-Source Benchmark Launch

- **Story**: Performance benchmark comparing Node.js, Bun, and Go for high-concurrency websocket handling.
- **Journalist Target**: Software architecture bloggers and tech reporters at *The New Stack* and *InfoQ*.
- **Pitch**: Sharing an open-source reproducible benchmark repository with raw telemetry data showing 3x throughput differences.
- **Outcome**: Organic coverage in 3 major developer newsletters and top placement on Hacker News.

---

## Verification Checklist

- [ ] Pitch email is under 150 words and contains zero promotional buzzwords.
- [ ] Subject line clearly specifies the data finding or core story hook.
- [ ] Every media contact on the list has published a story on the exact topic within the last 60 days.
- [ ] Press kit includes high-res images, founder bio, and copy-paste factsheet with no registration gate.
- [ ] Embargo timeline clearly specifies date, time, and timezone.

---

## Anti-Patterns

- **Wire Spraying**: Paying thousands to wire services hoping for organic editorial coverage.
- **Embargo Extortion**: Pitching an "exclusive embargo" to 100 reporters simultaneously without establishing prior interest.
- **Self-Serving Angles**: Expecting journalists to write about minor feature updates or internal executive promotions.
