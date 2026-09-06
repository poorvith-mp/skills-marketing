---
name: social-listening
group: Distribution
description: >-
  Monitor mentions, competitors and buying-intent threads, and surface where to reply today. Use
  when tracking brand mentions, competitor chatter, or social queries.
---

# social-listening

## Core Philosophy
Social listening is not vanity follower-count monitoring or ego-searching your brand name. Effective social listening is an active intelligence-gathering and lead-generation engine. It detects high-intent buying signals, competitor churn moments, and user frustrations across developer communities (Reddit, X, Hacker News, Discord) in real time—allowing you to provide authentic, helpful technical answers exactly when decisions are being made.

---

## 4-Step Social Listening Framework

### Step 1: Query Syntax & Boolean Listening Architecture
1. **Keyword Bucket Architecture**:
   - *High-Intent Commercial Signals*: Queries seeking recommendations or alternatives.
     - Formula: `(recommend OR alternative OR "looking for" OR "switching from") AND ("Competitor A" OR "Competitor B" OR "[Category]")`
   - *Competitor Dissatisfaction & Churn*: Queries signaling frustration with outages, price hikes, or broken features.
     - Formula: `("Competitor A" OR "Competitor B") AND ("price increase" OR "outage" OR "hate" OR "broken" OR "down" OR "support sucks")`
   - *Direct Brand Mentions*: Unprompted feedback or questions about your product.
     - Formula: `"[Your Brand]" OR "@[YourHandle]"`
   - *Industry Problem Spaces*: Technical questions regarding pain points you solve.
     - Formula: `"how to" AND ("zero downtime migrations" OR "postgres table lock")`

### Step 2: Channel Monitoring & Triaging Stack
1. **Target Channels & Mechanics**:
   - *Reddit*: Subreddits specific to your domain (e.g. `r/webdev`, `r/devops`, `r/startups`, `r/sysadmin`).
   - *Hacker News*: Monitor Ask HN and comment threads using Algolia HN Search API (`hn.algolia.com/api`).
   - *X / Twitter*: Search API streams with filtered retweets (`-filter:retweets`).
   - *GitHub Discussions & Issues*: Monitor competitor public repositories for open issue complaints.
2. **Signal Triaging Tiers**:
   - *Tier 1 (Immediate - 30m SLA)*: Direct buying requests or competitor churn vents.
   - *Tier 2 (Same Day - 4h SLA)*: General technical troubleshooting questions in your domain.
   - *Tier 3 (Weekly Digest)*: Macro sentiment shifts, recurring feature complaints, and market trends.

### Step 3: The Authentic Engagement & Reply Protocol
1. **The 90/10 Rule of Community Reply**:
   - 90% of the response must be genuine, stand-alone technical value that solves the user's problem immediately without clicking any link.
   - 10% (at the very end, with full transparency): Mention your tool only if it directly eliminates the stated pain.
2. **Banned Reply Behaviors**:
   - Never use automated AI bots to post canned marketing pitches.
   - Never pretend to be an unbiased third-party user if you work on the product; always state affiliation clearly ("Disclosure: I'm the founder of [X]").

### Step 4: Closed-Loop Feedback to Product & Sales
1. **Product Intelligence Logging**:
   - Tag competitor complaints and route directly into product backlog (e.g. "Competitor X just dropped free tier -> launch migration guide").
2. **Lead Routing**:
   - Tag qualified enterprise buyer threads and alert account executives in dedicated Slack channel (`#intent-signals`).

---

## Deliverable Format: Social Listening Playbook (`SOCIAL-LISTENING-SPEC.md`)

```markdown
# Social Listening & Intent Monitoring Spec: [Brand Name]

## 1. Boolean Query Architecture
| Bucket | Platforms | Search Query String | Alert SLA |
|---|---|---|---|
| High Intent | Reddit, X | `(alternative OR recommend) AND ("Vendor A" OR "Vendor B")` | < 1 hour |
| Competitor Pain | X, HN | `("Vendor A" OR "Vendor B") AND (outage OR "price increase" OR migration)` | < 2 hours |
| Technical Problem | Reddit, StackOverflow | `"how to fix" AND "DDL table lock postgres"` | Same day |

## 2. Platform Monitoring Matrix
- **Reddit Subreddits**: `r/devops`, `r/aws`, `r/kubernetes`
- **Hacker News Keywords**: `[Competitor]`, `[Category Problem]`
- **X Lists**: Curated list of 50 industry engineering leaders

## 3. Authentic Response Template
**Context**: User venting about Competitor X's sudden price increase.

**Response**:
"Hey [User], dealing with [Competitor's] seat-based pricing spike is painful once you scale past 20 engineers. If you're looking to migrate, here is the standard script to export your historical telemetry into ClickHouse without data loss: [Code snippet].

*(Disclosure: I'm the founder of [Product Name]—we built an open-source alternative with flat-rate infrastructure pricing specifically because of this issue. Let me know if you run into migration snags.)*"

## 4. Signal Escalation & Logging
- **Slack Alert Channel**: `#social-leads`
- **Product Feedback Log**: Notion Database: Competitor Intelligence
```

---

## Worked Example: Database Tool Intent Capture

- **Trigger**: Developer posted on `r/devops`: *"Struggling with Postgres migrations locking production tables during high traffic. What are people using?"*
- **Action**: Engineering founder replied with a detailed 4-paragraph technical breakdown explaining `ALTER TABLE ADD COLUMN` lock mechanisms in Postgres 14+ and how to avoid them manually using raw SQL.
- **Disclosure**: Added a 1-sentence note at the bottom noting their CLI tool automates that exact safety check.
- **Result**: Post received 45 upvotes; drove 230 GitHub repo visits and 14 new active CLI installs within 24 hours.

---

## Verification Checklist

- [ ] Boolean queries exclude retweets, spam, and non-English results.
- [ ] Tier 1 intent queries trigger automated Slack or webhook notifications.
- [ ] Reply policy enforces 90% technical solution before any tool mention.
- [ ] Full affiliation disclosure is mandatory in every outbound response.
- [ ] Insights and competitor feature gaps are logged in a structured product backlog.

---

## Anti-Patterns

- **Astro-Turfing**: Creating fake anonymous accounts to praise your own product in comment threads.
- **Link Dropping**: Dropping a naked signup URL with "Check out my tool" without answering the person's question.
- **Arguing with Trolls**: Wasting executive time engaging in unproductive flame wars on social platforms.
