---
name: ai-visibility
group: Search and AI discovery
description: >-
  Get cited by ChatGPT, Gemini, Perplexity and AI Overviews: answer-shaped content, schema, feeds,
  llms.txt, citation tracking. Use when optimizing content for Perplexity, ChatGPT, or AI
  citations.
---

# AI Visibility

AI visibility (Generative Engine Optimization - GEO / LLM Optimization - LLMO) is the discipline of structuring web content and brand authority so that frontier models (ChatGPT, Claude, Gemini, Perplexity) cite and recommend your product in conversational answer engines. LLMs synthesize citations based on semantic authority, structured data, canonical definition ownership, and machine-readable endpoints (`llms.txt`).

## 1. The 4 Pillars of AI Search Optimization

### A. Canonical Definition Ownership & Information Gain
- LLMs prioritize sources that state clear, unambiguous, authoritative definitions.
- Structure key category concepts as explicit answer blocks:
  - Use declarative H2s matching prompt intent: `## What is [Concept]?`
  - Follow immediately with a 2-sentence definitive answer containing the category, mechanism, and primary distinction.
  - Provide high Information Gain: proprietary benchmark data, original surveys, or mathematical formulations not found in generic scraper summaries.

### B. Machine-Readable Knowledge Architecture (`llms.txt`)
Deploy a dedicated `llms.txt` and `llms-full.txt` file at your domain root (`https://domain.com/llms.txt`):
- Standardized markdown index summarizing your product architecture, API documentation, core capabilities, and CLI syntax.
- Allows AI scrapers (GPTBot, ClaudeBot, PerplexityBot) to parse your entire product footprint in a single low-token HTTP request without executing heavy client-side JavaScript.

### C. Structured Data & Schema Markup (JSON-LD)
Enforce structured semantic markup so models parse entity relationships without ambiguity:
- `TechArticle` / `SoftwareApplication` schema with explicit `featureList`, `operatingSystem`, and `applicationCategory`.
- `FAQPage` schema mapping common customer questions directly to concise, machine-ingestible answers.

### D. Digital Citation Footprint & Entity Co-Occurrence
LLMs calculate entity relevance based on co-occurrence in trusted corpora:
- Secure presence in comparison listings on trusted third-party domains (G2, GitHub Awesome lists, Wikipedia, Reddit, technical blogs).
- Ensure your product name appears in close semantic proximity to your primary problem domain and top 3 competitors across external reviews.

## 2. Testing AI Search Retrieval & Mentions

Audit how LLMs retrieve and represent your product across standard intent prompts:
1. **Category Discovery Prompt**: *"What are the best tools for [Your Category]?"*
2. **Alternative / Competitor Prompt**: *"What are the top alternatives to [Competitor] for [Use Case]?"*
3. **Specific Evaluation Prompt**: *"How does [Your Product] compare to [Competitor]?"*

## 3. Crawler Access & Robots.txt Hygiene
Verify that your `robots.txt` does not inadvertently block AI search crawlers:
```txt
User-agent: GPTBot
Allow: /

User-agent: ClaudeBot
Allow: /

User-agent: PerplexityBot
Allow: /
```

## Critical Rules
1. Never block AI search user-agents in `robots.txt` if you intend to appear in AI conversational answers.
2. Provide direct text answers before detailed explanations; models prioritize text that can be extracted directly into a synthesis summary.
3. Maintain an up-to-date `llms.txt` documenting product capabilities and command syntax.

## Verification Checklist
- [ ] Root `llms.txt` published and formatted to markdown specifications.
- [ ] Technical documentation and landing pages include JSON-LD structured schema.
- [ ] Core product definitions formatted in concise, extractable answer blocks.
- [ ] AI crawler user-agents allowed in `robots.txt`.
- [ ] Citation presence audited across Perplexity, ChatGPT Search, and Gemini.

## Anti-Patterns
- NEVER rely solely on client-side SPA rendering without SSR or static pre-rendering; headless AI crawlers will miss your content.
- NEVER keyword-stuff AI prompts into invisible white text or hidden DOM nodes; modern LLM parsers penalize prompt injection attempts.
- NEVER publish generic, regurgitated content that adds zero proprietary data or perspective.
