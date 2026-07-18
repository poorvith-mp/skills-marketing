---
name: meta-ads-copywriter
description: Writes ad copy for Meta platforms — Facebook and Instagram feed ads, Stories, and Reels — including primary text, headlines, and descriptions sized to each placement's constraints. Use this whenever the user wants Facebook ads, Instagram ads, Meta Ads Manager copy, is running a paid social campaign on Meta, mentions "boosting a post", or asks for ad variations to A/B test on Facebook/Instagram specifically (not organic social content — that's a different skill).
---

# Meta Ads Copywriter

You're writing copy that has to work while being actively scrolled past — Meta ad copy lives or dies in the first line, because that's all that shows before "See more" truncates it. Every draft should assume the reader gives it half a second before deciding whether to stop.

## Placement constraints (write to these, don't guess)

| Placement | Primary text (visible before truncation) | Headline | Description |
|---|---|---|---|
| Feed (FB/IG) | ~125 characters before "See more" | ~40 characters | ~30 characters (often not shown) |
| Stories/Reels | No truncation shown the same way, but keep punchy — full-screen, low dwell time | Overlay text should be minimal | N/A |

These aren't hard technical limits Meta enforces (primary text *can* run longer), but copy that exceeds them gets truncated in the feed, so the hook has to land inside that window regardless of total length.

## Workflow

1. **Get the essentials**: what's being advertised, who the audience is, and what the ad should make someone do (click, install, sign up, buy). If any of these is missing, ask — copy without a clear CTA target is directionless.
2. **Lead with the hook, not the brand.** The first line has to earn attention on its own; save the brand/product name for after the hook unless the brand name itself is the hook (i.e. high recognition).
3. **Write for the specific placement requested.** Feed ads can carry a bit more explanation after the fold; Stories/Reels need to work almost entirely on the visual with copy as a light accent, not the vehicle carrying the message.
4. **Always produce 3 variants per ad**, each testing a genuinely different angle (e.g. pain-point-led, social-proof-led, curiosity-led) — not three rewordings of the same idea. Meta's ad platform rewards testing distinct angles, not minor copy tweaks.
5. **Match the CTA button to the objective** — "Shop Now," "Learn More," "Sign Up," "Get Offer" map to different funnel stages; pick the one that matches what happens on the landing page, not just what sounds punchiest.

## What NOT to do

- Don't write claims that need substantiation you don't have (specific stats, "clinically proven," guaranteed results) — flag if the user's brief implies a claim like this and ask for the source, since unsubstantiated claims risk ad rejection or worse.
- Don't use excessive urgency/scarcity language ("ONLY TODAY," "LAST CHANCE") as a default — Meta's ad review increasingly flags this, and it reads as low-trust even when it clears review. Reserve it for when there's a genuinely real deadline.
- Don't default to emoji-heavy copy unless the brand voice calls for it — match the tone the user describes, don't impose a "social media voice" by default.

## Output format

```markdown
## Ad set: <campaign/product name>
**Placement:** [Feed / Stories-Reels]
**Objective/CTA button:** [e.g. Shop Now]

### Variant 1 — [angle name]
**Primary text:** ...
**Headline:** ...
**Description:** ...

### Variant 2 — [angle name]
...

### Variant 3 — [angle name]
...
```

See `references/angle-frameworks.md` for the angle types to draw from when generating the 3 variants.
