---
name: link-building
last_reviewed: 2026-09-06
group: Search and AI discovery
description: >-
  Earn links: prospect targets, guest posts, digital PR, broken-link and unlinked-mention
  outreach, and when to disavow. Use when acquiring high-quality backlinks, mentions, or digital
  PR links.
---

# Link Building

Link building is the acquisition of editorially earned, high-authority external backlinks to build domain authority, enhance search ranking velocity, and drive referral discovery. Modern link acquisition rejects black-hat link schemes, automated spam outreach, and paid PBN link farms, focusing instead on digital PR, original research citations, unlinked brand mention recovery, and resource page placements.

## 1. High-Authority Link Acquisition Strategies

### A. Original Research & Benchmark Data (Link Magnets)
- The highest-yielding backlink strategy is publishing proprietary industry data that other journalists and writers must cite as a source:
  - *Example*: "Analysis of 500,000 LLM API calls: Average latency and failure rates across 8 providers."
  - *Mechanism*: Tech journalists, bloggers, and industry analysts writing about AI latency search for benchmark statistics and naturally link to your original dataset as their citation.

### B. Unlinked Brand Mention Reclamation
- Scan the web for journalists, podcasts, or blog posts that mention your product, founders, or open-source libraries by name but forgot to include an active hyperlink:
- Send a polite, low-friction note:
  ```txt
  Subject: Quick note regarding your article on [Topic]

  Hi [Name],

  Loved your recent breakdown of agentic orchestration workflows. Noticed you mentioned
  our open-source library, Skillary, in paragraph 4 — really appreciate the shoutout!

  Would you be open to hyperlinking the mention to https://github.com/poorvith-mp/skillary
  so your readers can easily find the repository?

  Either way, thanks for the great analysis!
  ```

### C. Strategic Guest Contributions & Technical Columns
- Write definitive, in-depth technical guides for established developer publications (FreeCodeCamp, Smashing Magazine, HackerNoon, respected engineering blogs).
- Anchor links within the body must be contextual, technical, and directly relevant to the topic, not promotional sales pitches.

### D. Broken Link Building on Resource Pages
- Identify authoritative industry resource pages and curated link directories that contain broken 404 links to dead tools.
- Inform the webmaster of the broken link and suggest your live, maintained tool/guide as an updated replacement.

## 2. Evaluating Backlink Quality & Toxicity
Not all links are beneficial; low-quality links harm domain reputation:
- **Domain Rating (DR) / Authority**: Prioritize links from sites with DR > 50 and verified organic search traffic.
- **Topical Relevance**: A single link from a relevant developer engineering blog carries vastly more algorithmic weight than 50 links from unrelated lifestyle sites.
- **Link Placement**: Editorial in-content contextual links outperform footer, sidebar, or author-bio links.

## 3. Disavow Protocol (Google Search Console)
When your domain is targeted by negative SEO or accumulated toxic spam links:
- Maintain a `disavow.txt` file listing spammy domains (`domain:spamsite.xyz`).
- Submit via Google Search Console Disavow Links Tool only when manual actions or clear algorithmic suppression is observed.

## Critical Rules
1. Never pay third-party link brokers for backlinks; paid links without `rel="sponsored"` or `rel="nofollow"` directly violate Google Search Essentials.
2. Every link outreach email must be personalized to a specific article and author; automated blast outreach is instantly deleted.
3. Anchor text must appear natural and diversified; never force exact-match commercial keywords into 100% of backlinks.

## Verification Checklist
- [ ] Proprietary data or unique technical resources published as linkable assets.
- [ ] Unlinked brand mentions monitored using Google Alerts or Ahrefs.
- [ ] Outreach emails sent to named individual editors with custom context.
- [ ] Backlink profiles audited quarterly for spam and toxic link anomalies.
- [ ] Acquired links verified indexable (`dofollow` where editorially appropriate).

## Anti-Patterns
- NEVER participate in reciprocal link exchange networks ("link to me and I'll link to you").
- NEVER purchase links on Fiverr or unvetted guest-posting networks.
- NEVER send generic outreach asking webmasters to "check out our awesome blog post" without identifying a specific broken link or editorial gap.
