---
name: app-store-optimization
group: Platform and naming
description: >-
  Audit and fix App Store and Play listings: keywords, screenshots, ratings and conversion. Use
  when optimizing iOS App Store or Google Play keywords and listings.
---

# App Store Optimization

App Store Optimization (ASO) is organic conversion rate optimization and search indexing across the Apple App Store and Google Play Store. ASO combines algorithmic keyword indexation, visual asset optimization (icons, screenshots, app previews), localization, and review sentiment engineering to maximize organic installs and improve paid acquisition conversion.

## 1. App Store Search Algorithm Mechanics

### Apple App Store Indexing Fields
Apple indexes keywords from three specific metadata fields with strict character limits:
- **App Name (Title - Max 30 chars)**: Highest algorithmic weight. Include brand name + primary keyword (e.g. `Brand: Fast Task Manager`).
- **Subtitle (Max 30 chars)**: Second highest weight. Secondary keywords and core value proposition.
- **Keyword Field (Max 100 chars, hidden)**: Comma-separated, no spaces after commas.
  - *Rules*: Never repeat keywords already present in the title or subtitle; do not include competitor trademarked names; use singular forms (Apple auto-indexes plurals).
- *Total Search Space*: Apple does **NOT** index the main description text for search ranking.

### Google Play Store Indexing Fields
Google Play indexes using full semantic natural language processing (NLP):
- **App Title (Max 30 chars)**: Core keyword anchor.
- **Short Description (Max 80 chars)**: Critical for both search indexing and store listing conversion.
- **Long Description (Max 4,000 chars)**: Google indexes the entire text. Target a 2%–3% keyword density for primary search phrases; structure with clean headings and bullet lists.

## 2. Visual Asset Conversion Engineering
Visuals drive 90% of download decisions once a user lands on the listing:
- **App Icon**: Test bold, recognizable silhouette designs against white, dark, and wallpaper backgrounds. Avoid tiny unreadable text inside the icon.
- **First 3 Screenshots (The Impression Zone)**:
  - Screenshot 1 must answer: *What is this and why do I need it?*
  - Use legible, high-contrast headline captions (minimum 40pt font on mobile devices).
  - Show real, localized UI surfaces; avoid abstract lifestyle marketing graphics.
- **App Preview Video (15–30 Seconds)**: Autoplays muted. First 3 seconds must showcase live product UI in action.

## 3. Ratings, Reviews & In-App Prompt Timing
Star ratings directly affect algorithmic search visibility (apps below 4.0 stars suffer massive ranking penalties):
- **Prompt Timing**: Never prompt for a review immediately after app installation or during a critical workflow.
- **The "Happy Moment" Trigger**: Trigger the native `SKStoreReviewController` immediately after a user achieves a success state (e.g. completed their 5th task, exported a finished design).
- **Review Velocity**: Apple and Google prioritize apps with steady, recent review velocity over stagnant historical ratings.

## Critical Rules
1. Never put spaces after commas in Apple's 100-character keyword field (wastes valuable characters).
2. Never prompt users for reviews more than 3 times in a 365-day period (enforced by Apple platform guidelines).
3. Localize metadata and screenshots for top international markets (English, Spanish, Japanese, German).

## Verification Checklist
- [ ] App title and subtitle stay strictly within 30-character limits.
- [ ] Apple keyword field utilizes all 100 characters with zero repeated terms.
- [ ] First three screenshots display high-contrast, legible benefit headlines.
- [ ] Review prompt triggered exclusively during positive user achievement states.
- [ ] App description on Google Play maintains 2%–3% keyword density without keyword stuffing.

## Anti-Patterns
- NEVER include the word "free" or pricing claims in Apple App Store metadata (violates Apple Review Guideline 2.3.7).
- NEVER use generic screenshots showing bare phone bezels without clear benefit copy.
- NEVER purchase fake incentivized reviews; store algorithms detect velocity anomalies and remove apps.
