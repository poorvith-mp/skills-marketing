---
name: seo-audit
group: Search and AI discovery
description: >-
  Diagnose technical, on-page and ranking-loss issues on a live site, ranked by impact. Use when
  diagnosing technical SEO issues, crawling errors, or index drops.
---

# seo-audit

## Core Philosophy
An SEO audit is not an automated 150-page export from Screaming Frog dumped into a client's inbox. An effective technical and on-page SEO audit provides prioritized, engineering-ready remediation instructions categorized by business impact: P0 issues that actively destroy indexation and crawl budgets, P1 structural and architectural fixes that unlock keyword rankings, and P2 content optimization opportunities.

---

## 4-Step Systematic SEO Audit Protocol

### Step 1: Technical Crawlability & Indexation (P0 Gates)
1. **Robots.txt & Meta Directives**:
   - Inspect `robots.txt` for unintended `Disallow` rules blocking critical CSS/JS bundles or high-value directories.
   - Verify `X-Robots-Tag` and `<meta name="robots">` tags for rogue `noindex` directives on production pages.
2. **HTTP Status & Redirect Architecture**:
   - Crawl all internal URLs: Flag 4xx client errors and 5xx server errors.
   - Identify redirect chains ($A  o B  o C$) and redirect loops; enforce 1-hop 301 redirects directly to canonical targets.
3. **XML Sitemap Hygiene**:
   - Ensure sitemaps contain exclusively 200 OK, canonical, indexable URLs.
   - Verify sitemap submission in Google Search Console and ensure file size $< 50text{MB}$ and $< 50,000$ URLs per file.
4. **Canonicalization Verification**:
   - Audit `rel="canonical"` tags: Ensure every indexable page has a self-referencing canonical or points to its primary deduplicated URL.
   - Verify protocol and domain consistency (enforce HTTPS and non-WWW vs WWW canonicalization).

### Step 2: Core Web Vitals & Frontend Performance
1. **Google Core Web Vitals Targets**:
   - *Largest Contentful Paint (LCP)*: $\le 2.5text{s}$ (Optimize hero image preloading, eliminate render-blocking CSS).
   - *Interaction to Next Paint (INP)*: $\le 200text{ms}$ (Break up long main-thread JavaScript tasks).
   - *Cumulative Layout Shift (CLS)*: $\le 0.1$ (Set explicit `width` and `height` on all image and iframe tags).
2. **Server Response Time**:
   - Target Time to First Byte (TTFB) $\le 800text{ms}$ globally via edge caching and CDN optimization.

### Step 3: Site Architecture & Internal Linking Structure
1. **Click Depth Hierarchy**:
   - Ensure all critical conversion and SEO landing pages reside within $\le 3$ clicks from the root domain.
2. **Orphan Pages & Internal PageRank Distribution**:
   - Cross-reference sitemap URLs against crawl logs to identify orphaned pages with zero internal inbound links.
   - Optimize anchor text: Replace generic "click here" or "read more" links with descriptive, keyword-rich anchor text.
3. **URL Structure & Breadcrumbs**:
   - Enforce clean, lowercase, hyphenated URL slugs without trailing query parameters.
   - Implement BreadcrumbList Schema (`schema.org/BreadcrumbList`) in JSON-LD.

### Step 4: On-Page Content, Semantic HTML & Cannibalization
1. **Metadata & Heading Structure**:
   - Title Tags: Unique, 50–60 characters, containing primary target keyword and brand.
   - Meta Descriptions: 120–155 characters, compelling CTA for search snippet CTR.
   - Single `<h1>` tag per page matching search intent, followed by hierarchical `<h2>` and `<h3>` tags.
2. **Keyword Cannibalization Audit**:
   - Group pages ranking for identical search queries. Consolidate competing thin pages into a single authoritative pillar page with 301 redirects.
3. **Structured Data (JSON-LD)**:
   - Validate schema implementations using Google's Rich Results Test (SoftwareApplication, Article, FAQPage, Organization).

---

## Deliverable Format: Technical SEO Audit Report (`SEO-AUDIT-REPORT.md`)

```markdown
# Technical SEO Audit & Remediation Roadmap: [Domain Name]

## 1. Executive Summary & Crawl Health
- **Total URLs Crawled**: [Count]
- **Indexable URLs**: [Count]
- **Critical P0 Blockers**: [Count] | **High P1 Issues**: [Count] | **Medium P2 Issues**: [Count]
- **Core Web Vitals Pass Rate**: [LCP / INP / CLS status]

## 2. Prioritized Action Roadmap

### [P0 - Critical] Crawl & Indexation Blockers
- **Issue**: [e.g. Rogue noindex tag on product category pages]
- **Impact**: Pages completely dropped from Google index; direct traffic loss.
- **Affected URLs**: [List or pattern]
- **Engineering Fix**: Remove `<meta name="robots" content="noindex">` from `app/layout.tsx`.

### [P1 - High Impact] Architecture & Performance
- **Issue**: [e.g. LCP exceeding 4.2s on blog posts due to unoptimized PNG hero images]
- **Impact**: Fails Core Web Vitals assessment; ranking suppression on mobile.
- **Engineering Fix**: Convert hero images to WebP/AVIF and add `<link rel="preload" as="image">`.

### [P2 - Content & On-Page Polish]
- **Issue**: [e.g. Missing BreadcrumbList JSON-LD schema]
- **Engineering Fix**: Inject structured JSON-LD into head component.

## 3. Keyword Cannibalization Matrix
| Query | Competing URL A | Competing URL B | Recommended Resolution |
|---|---|---|---|
| [Target Keyword] | `/blog/post-1` | `/features/tool` | 301 redirect post-1 to features |
```

---

## Worked Example: Next.js SaaS SEO Remediation

- **Issue**: Client’s Next.js marketing site had client-side rendered metadata, causing Googlebot to crawl empty title tags and default meta descriptions.
- **Remediation**: Migrated page metadata generation to Next.js `generateMetadata` server-side export. Added self-referencing canonicals and preloaded font assets.
- **Result**: Core Web Vitals LCP dropped from 3.8s to 1.4s; organic search impressions increased 42% over 8 weeks as indexing refreshed.

---

## Verification Checklist

- [ ] `robots.txt` and meta robots tags verified with zero unintentional `noindex` directives.
- [ ] All sitemap URLs return HTTP 200 and match canonical URL tags.
- [ ] Core Web Vitals meet thresholds (LCP $\le 2.5text{s}$, INP $\le 200text{ms}$, CLS $\le 0.1$).
- [ ] Critical pages are reachable within $\le 3$ clicks from the homepage.
- [ ] All structured data validates without errors on Google Rich Results Test.

---

## Anti-Patterns

- **Automated Tool Dumps**: Presenting a 200-page automated PDF without triaging findings into prioritized engineering tasks.
- **Obsessing Over Vanity Scores**: Wasting weeks chasing a 100/100 Lighthouse desktop score while canonical tags remain broken.
- **Ignoring Search Intent**: Optimizing on-page keywords for informational terms on pages built for high-intent transactional conversion.
