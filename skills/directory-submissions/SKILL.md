---
name: directory-submissions
group: Distribution
description: >-
  Submit to startup, SaaS, AI and MCP directories for backlinks and discovery, tracked. Use when
  listing products on SaaSHub, AlternativeTo, or free directories.
---

# Directory Submissions

Software and AI directory submissions are foundational distribution channels for early domain authority, backlink acquisition, and initial organic discovery. Systematic directory placement targets curated, high-trust platforms (Product Hunt, SaaSHub, AlternativeTo, GitHub Awesome lists, Indie Hackers) with accurate metadata, tracked referral loops, and verified category taxonomy.

## 1. Tiered Directory Submission Taxonomy

Categorize submission targets by authority and traffic potential:
- **Tier 1 (High-Authority / Direct Referral Traffic)**:
  - *Product Hunt*: The flagship launch discovery engine.
  - *AlternativeTo*: High-intent search traffic targeting users actively searching for alternatives to incumbents.
  - *SaaSHub*: Automated software alternative rankings and verified feature matrices.
  - *G2 / Capterra*: Essential for enterprise B2B credibility and buyer shortlists.
- **Tier 2 (Ecosystem & Open Source Directories)**:
  - *GitHub Awesome Lists*: Curated topic lists (e.g. `awesome-ai-agents`, `awesome-devtools`). Requires submitting clean pull requests adhering to repository formatting standards.
  - *Indie Hackers / Hacker News Show*: Community-driven founder discovery.
  - *MCP / Tool Registries*: For AI and agent tooling (Smithery, Glama, Composio registries).
- **Tier 3 (AI & SaaS Aggregators)**:
  - *Futurepedia, There's An AI For That, Toolify*: High-volume catalog aggregators that generate early indexing backlinks.

## 2. Standardized Submission Metadata Package
Prepare a single source-of-truth metadata file before initiating submissions:
- **Product Name**: Official brand name.
- **Homepage URL**: Root URL tagged with clean referral UTMs: `https://domain.com/?utm_source=[directory]&utm_medium=directory&utm_campaign=profile`.
- **Short Tagline (Under 60 Chars)**: Concise benefit statement: "277 production agent skills with local SQLite search."
- **Full Description (200–500 Words)**: Problem addressed, key capabilities, technology architecture, and pricing model.
- **Visual Assets**:
  - Logo / Square Icon: 512x512 px PNG with transparent background.
  - Screenshots: 3 high-resolution 1920x1080 px images with legible feature callouts.
- **Pricing Classification**: Free / Freemium / Open Source / Commercial.

## 3. GitHub Awesome List PR Protocol
Submitting to curated GitHub Awesome lists requires strict adherence to open-source etiquette:
1. Fork the repository and create a clean feature branch (`git checkout -b add-[product-name]`).
2. Alphabetize your submission within the appropriate section.
3. Keep descriptions under 1 line, strictly factual, with zero marketing fluff (e.g. `- [Product](url) - Open-source library for X with Y support.`).
4. Ensure the repository has a clear README, verified open-source license, and clean commit history before opening the PR.

## 4. Tracking & Referral Loop Management
- Maintain a centralized directory ledger tracking: *Directory Name*, *Submission Date*, *Status (Pending/Live)*, *Listing URL*, *Assigned UTM Link*, and *Monthly Referral Traffic*.
- Monitor backlink indexing via Google Search Console and Ahrefs to ensure links are discovered and followed.

## Critical Rules
1. Never use automated spam submission bots that blast hundreds of low-quality link farms; low-quality directory spam triggers Google search penalties.
2. Ensure every submission uses custom, directory-specific UTM parameters to measure exact traffic and signups.
3. Update directory profiles whenever pricing, core branding, or major features change.

## Verification Checklist
- [ ] Standardized metadata package assembled with logos and screenshots.
- [ ] Dedicated UTM referral URLs generated for every target directory.
- [ ] Submissions logged in a central tracking ledger with live listing links.
- [ ] GitHub Awesome list PRs submitted following repository contribution guidelines.
- [ ] Inbound referral traffic and conversion rates monitored in analytics.

## Anti-Patterns
- NEVER submit incomplete listings without screenshots or clear descriptions.
- NEVER pay for expensive, unvetted directory packages that promise "submission to 500 sites" (these are automated link farms).
- NEVER list incorrect pricing or deceptive "free" tags for purely commercial software.
