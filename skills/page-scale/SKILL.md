---
name: page-scale
group: Search and AI discovery
description: >-
  Build templated pages from a dataset — locations, integrations, use cases — without tripping
  thin-content filters. Use when building programmatic SEO pages or templated content at scale.
---

# Page Scale

Programmatic SEO (pSEO) is the disciplined creation of high-utility, templated web pages at scale driven by structured databases. Programmatic SEO fails when teams generate thousands of thin, repetitive, low-value pages that trigger Google's Helpful Content System and spam penalties. Building high-authority programmatic surfaces requires rich relational datasets, proprietary local insights, dynamic schema injection, and indexation controls.

## 1. Programmatic Keyword Pattern Architecture
Identify scalable search patterns with repeatable query syntax:
- **Category + Attribute / Integration**:
  - `[Tool] integration for [Platform]` (e.g. "PostgreSQL connector for Next.js", "Slack alerts for Trigger.dev").
- **Persona / Use Case + Solution**:
  - `[Software Type] for [Niche]` (e.g. "Invoicing software for freelance copywriters").
- **Comparative Pairs**:
  - `[Tool A] vs [Tool B] for [Specific Use Case]`.
- **Location + Service (Local pSEO)**:
  - `[Service] in [City, State]`.

## 2. The Anti-Thin-Content Architecture (Information Gain)
To avoid manual search penalties, every programmatic page must deliver substantial unique content beyond simple keyword swapping:
- **Dynamic Data Visualization**: Render interactive charts, benchmark tables, or schema maps unique to that specific entity pair.
- **Entity-Specific Data Points**: Include at least 5 unique database attributes per page (e.g. API authentication type, rate limits, supported webhooks, latency benchmarks, documentation links).
- **Curated Community Reviews & Code Snippets**: Inject real, tested code integration examples specific to that language or platform pair.
- *Rule*: If you strip the target keywords from the page, does the remaining page still contain valuable, unique technical data? If no, do not publish.

## 3. Database Schema & Template Design

```json
{
  "integration_slug": "github-actions-to-slack",
  "source_tool": "GitHub Actions",
  "target_tool": "Slack",
  "category": "CI/CD Notifications",
  "protocol": "Incoming Webhooks",
  "code_snippet_yaml": "name: Notify Slack
on: [push]...",
  "setup_time_minutes": 5,
  "required_scopes": ["incoming-webhook", "chat:write"],
  "common_errors": [
    { "error": "invalid_auth", "resolution": "Verify SLACK_BOT_TOKEN secret in GitHub repository settings" }
  ]
}
```

## 4. Phased Rollout & Indexation Governance
Never publish 10,000 programmatic pages on day one; mass publishing triggers algorithmic spam flags:
- **Batch 1 (Alpha Tier - 50 Pages)**: Deploy top 50 highest-value pages. Monitor crawl frequency, indexing rate, and search impressions in Google Search Console for 30 days.
- **Batch 2 (Beta Tier - 250 Pages)**: If Alpha pages achieve >80% indexation and positive rankings, publish the next tier.
- **Indexation Guardrails**: Use `noindex, follow` on any programmatic page that lacks complete database records or original commentary.

## Critical Rules
1. Never publish programmatic pages generated solely by automated AI text spinners without a proprietary structured dataset.
2. Every programmatic page must be linked within a clear HTML sitemap and category breadcrumb hierarchy.
3. Automatically apply canonical tags and structured JSON-LD schema (`SoftwareApplication` or `ItemPage`) to every page.

## Verification Checklist
- [ ] Query syntax verified with measurable search volume and commercial intent.
- [ ] Underlying dataset contains rich, entity-specific technical attributes.
- [ ] Every page includes working code snippets, diagrams, or benchmark data.
- [ ] Phased publishing schedule limits initial rollout to <= 50 high-quality pages.
- [ ] Indexation and crawl health monitored via Google Search Console XML sitemaps.

## Anti-Patterns
- NEVER generate 5,000 pages that only swap a city name or tool title while keeping identical boilerplate text.
- NEVER let broken or incomplete database records publish empty placeholder fields onto live URLs.
- NEVER hide programmatic pages from internal navigation; pages must be discoverable via natural link hierarchies.
