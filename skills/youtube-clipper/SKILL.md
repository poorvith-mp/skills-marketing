---
name: youtube-clipper
description: >-
  Finds the highest-performing moments in a long video and cuts them into short clips with hooks
  and timestamps. Use when repurposing long-form video into shorts.
---

# YouTube Clipper
You turn a YouTube video into short-form clips using the \*\*Higgsfield MCP\*\* — specifically the personal clipper tools (\`mcp__claude_ai_Higgsfield__personal_clipper_\*\`, powered by FNF Clipify). All clipping happens through the Higgsfield MCP server; do not attempt to clip via ffmpeg, yt-dlp, or any other tool.
## Required Inputs
- A YouTube URL (from \`\$ARGUMENTS\` or the user's message). If missing, ask once and stop.
- Default to \*\*10 clips, 9:16 aspect, "Inter" subtitle font\*\* unless the user specified otherwise. Don't re-ask if they already said "10 clips" — just confirm the defaults in one line and proceed.
## Workflow
1. \*\*Load Higgsfield MCP clipper tools\*\* via ToolSearch (the Higgsfield MCP tools are deferred and must be loaded before use):
```plain text
   select:mcp__claude_ai_Higgsfield__personal_clipper_create,mcp__claude_ai_Higgsfield__personal_clipper_status,mcp__claude_ai_Higgsfield__personal_clipper_jobs,mcp__claude_ai_Higgsfield__list_workspaces,mcp__claude_ai_Higgsfield__balance
```
2. \*\*Sanity check workspace + credits\*\* (parallel): \`list_workspaces\` + \`balance\`. If \`is_selected\` workspace is missing or credits look insufficient, stop and tell the user.
3. \*\*Create the job\*\* with \`personal_clipper_create\`:<br>   - \`urls\`: \`\[\<youtube_url\>\]\` (it's an array)<br>   - \`clips_num\`: 10 (max 20)<br>   - \`clip_aspect\`: \`"9:16"\` (also valid: \`"1:1"\`, \`"16:9"\`)<br>   - \`subtitle_font\`: \`"Inter"\` (or any of: Noto Sans, Noto Serif, Noto Sans Display, IBM Plex Sans, M PLUS Rounded 1c, Bebas Neue, Archivo Black, Unbounded, Montserrat, Bangers, Permanent Marker, Playfair Display, Caveat)<br>   - Capture the returned \*\*\`row_id\`\*\* (UUID) — that's what status polling needs.
4. \*\*Poll \`personal_clipper_status\`\*\* with \`row_id\`:<br>   - Clipping takes several minutes. Use \`ScheduleWakeup\` — first wake at \`delaySeconds: 270\` (stays in prompt cache), then 600–1200s for subsequent checks.<br>   - On failure, surface the error verbatim and stop.
5. \*\*Deliver clips\*\* when complete:<br>   - Numbered markdown list with: hook/title, duration, any score returned, and the playable/download URL.<br>   - Report the actual count returned — never claim 10 if fewer came back.
## Critical Rules
1. Never invent a YouTube URL — ask if missing.<br>2. Always use the \*\*Higgsfield MCP\*\* for clipping — never ffmpeg, yt-dlp, or any other local tool.<br>3. Always load Higgsfield MCP tools via ToolSearch before calling them.<br>4. \`urls\` must be an array, even for a single video.<br>5. Status polling uses \`row_id\` (UUID), not "job_id".<br>6. Don't busy-poll. Use \`ScheduleWakeup\` at 270s+ intervals.<br>7. \`clips_num\` is capped at 20.<br>8. Echo the actual clip count returned; don't pad.<br>9. Surface every per-clip field the API returns (hook, score, duration, transcript) — that's the signal users pay for.
## Quick Template — Final Delivery
```plain text
Done — N clips from <video title or URL> (row_id: <uuid>):

1. **<Hook>** — 0:42 · score 87
   https://higgsfield.../clip/...

2. ...
```
Use \`\$ARGUMENTS\` as the YouTube URL when present.


## Output format
- Lead with the result the user asked for.
- Use clear headings and bullet lists where helpful.
- Call out assumptions and open questions at the end.
- Stay specific to the YouTube Clipper workflow; avoid generic filler.

## Verification & Quality Checklist

- [ ] Success metric and its current baseline defined before launch, not after.
- [ ] Target segment named specifically enough to exclude someone.
- [ ] Channel-specific limits respected (character counts, aspect ratios, policy rules).
- [ ] Compliance checked for the channel (CAN-SPAM, GDPR, platform ad policy).

## Anti-Patterns & Constraints

- NEVER launch without a stated kill criterion and review date.
- NEVER claim a result without naming the attribution window and method.
- NEVER make a comparative or outcome claim the product cannot substantiate.
