---
name: search-engine-optimizer
description: >-
  Executes on-page, technical, and off-page search engine optimization (SEO) audits, keyword clustering, structured data schema generation, and regional search strategies (Google, Bing, Baidu), and AI search optimization (Google SGE/AI Overviews, Perplexity, Bing Copilot). Use when auditing website SEO, optimizing content rankings, or diagnosing indexing issues.
---

# Search Engine Optimizer (SEO)

Delivers data-driven search engine optimization across technical SEO, keyword architecture, content optimization, and search engine compliance.

## Phased Workflow

### Phase 1: Technical & Core Web Vitals Audit
1. Audit crawlability and indexing: `robots.txt`, XML sitemaps, canonical tags, `noindex` directives, HTTP status codes (301 redirect chains, 404s).
2. Evaluate Core Web Vitals: Largest Contentful Paint (LCP < 2.5s), Interaction to Next Paint (INP < 200ms), Cumulative Layout Shift (CLS < 0.1).
3. Validate Structured Data (JSON-LD schema markup for Articles, FAQs, Products, Breadcrumbs).

### Phase 2: Keyword Strategy & Search Intent Mapping
1. Map high-intent keywords to content funnels (Informational, Commercial, Transactional).
2. Cluster semantic keywords to build topic authority without keyword cannibalization.

### Phase 3: Content Optimization & Metadata
1. Craft CTR-optimized title tags (<60 characters) and compelling meta descriptions (<155 characters).
2. Structure semantic content hierarchy (`H1`, `H2`, `H3`) answering user search intent comprehensively.

## Regional Search Engine Rules (Baidu, Bing, Naver)
- **Baidu:** Requires ICP license, simplified Chinese, server hosting in mainland China/HK, Baidu Zhanzhang verification, and avoidance of blocked resources (Google Fonts, YouTube embeds).


## Agentic & AI Search Optimization (AIO)
1. Optimize content for AI Overviews (Google SGE), Bing Copilot, and Perplexity citations.
2. Structure content with clear factual assertions, data tables, and FAQ schemas that AI systems prefer to cite.
3. Implement `llms.txt` and structured data to improve AI crawlability.
4. Monitor AI citation attribution using brand mention tracking across AI answer engines.

## Verification & Quality Checklist
- [ ] Exactly one `<h1>` per page matching the primary keyword target.
- [ ] All images have descriptive, keyword-relevant `alt` text.
- [ ] Canonical URL matches the final resolved HTTPS URL.
- [ ] JSON-LD schema validates with Google Rich Results Test without warnings.

## Anti-Patterns & Constraints
- NEVER stuff keywords unnaturally into content or metadata.
- NEVER deploy duplicate content without explicit canonicalization.
