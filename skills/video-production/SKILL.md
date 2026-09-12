---
name: video-production
last_reviewed: 2026-09-06
group: Assets
description: >-
  Script and produce demos, explainers, UGC-style ads and avatar video. Use when scripting or
  producing product demos, walk-throughs, or videos.
---

# video-production

## Core Philosophy
Modern tech and developer audiences skip high-production corporate marketing videos filled with generic stock footage and upbeat corporate ukulele music. High-converting software video production prioritizes authentic, dense, screen-recorded utility: live terminal sessions, sharp IDE code walkthroughs, crisp UI interactions, honest technical trade-offs, and zero wasted seconds.

---

## 4-Step Technical Video Production Pipeline

### Step 1: Screenplay & High-Density Scripting
1. **The 3 Core Video Formats**:
   - *The 60-Second Release Teaser*: Fast-paced social launch video focusing on 1 killer capability.
   - *The 3-Minute Technical Deep Dive*: Architectural explanation + end-to-end code demonstration.
   - *The Interactive Changelog Walkthrough*: 90-second monthly feature rundown for existing users.
2. **The First 5 Seconds Rule**:
   - Never begin with a 10-second animated logo bumper.
   - Start immediately with the finished result or the pain point:
     - *"In the next 60 seconds, we're going to deploy a resilient Kafka cluster on Kubernetes with zero yaml."*
3. **Script Table Formatting**:
   - Maintain a two-column script: Visual Cue (Left) vs Audio Voiceover (Right).

### Step 2: Screen Capture Environment Setup & Hygiene
1. **Display & Terminal Calibration**:
   - Screen Resolution: Native 1920x1080 (1080p) or 2560x1440 (1440p) at 60 FPS.
   - Font Sizing: Set IDE and terminal font to 18–22pt so code remains perfectly legible on mobile devices.
   - Theme: High-contrast dark theme (e.g. Catppuccin Mocha or Tokyo Night); disable window transparency.
   - Cursor: Scale mouse cursor to 1.5x or 2x size; enable subtle click highlight rings.
2. **Distraction Elimination**:
   - Enable "Do Not Disturb" on macOS/Windows.
   - Clear desktop icons, dock/taskbar auto-hide, and browser bookmarks bar.
   - Use clean, realistic seed data (no `asdf`, `test123`, or offensive placeholder names).

### Step 3: Audio Engineering & Voiceover Recording
1. **Acoustic & Microphone Standards**:
   - Microphone: Dynamic broadcast microphone (Shure SM7B, PodMic, or high-end USB like Rode NT-USB) positioned 3–5 inches from mouth with pop filter.
   - Voiceover Pacing: 140–160 words per minute; crisp articulation.
2. **Audio Post-Processing Chain**:
   - High-Pass Filter: Cut sub-bass frequencies below 80Hz.
   - Compressor: 3:1 ratio to even out vocal dynamics.
   - Loudness Normalization: Target -16 to -18 LUFS (standard for web/YouTube).
   - Background Music: Keep ambient audio at -24 to -28dB below the spoken voice track.

### Step 4: Editing, Motion Graphics & Pacing
1. **Ruthless Editing Discipline**:
   - Cut all typing pauses, terminal compilation delays, and loading spinners unless specifically showing speed.
   - Use subtle digital zooms (115–125%) to draw the viewer’s eye to specific terminal flags or UI buttons.
2. **Keyboard Shortcut Overlays**:
   - Display on-screen keystroke callouts (e.g. `Cmd + K`, `Ctrl + Shift + P`) during shortcut demonstrations.
3. **Export & Encoding**:
   - Codec: H.264 / MP4, 15–20 Mbps bitrate, 60 FPS, color profile Rec.709.

---

## Deliverable Format: Video Production Script (`VIDEO-SCRIPT.md`)

```markdown
# Video Production Script: [Video Title]

## 1. Video Specifications
- **Format**: [60s Teaser / 3-minute Deep Dive / Product Demo]
- **Target Audience**: [Senior Backend Engineers / DevSecOps]
- **Core Value Takeaway**: [Specific outcome demonstrated]
- **Resolution**: 1920x1080 @ 60 FPS

## 2. Audio-Visual Screenplay
| Timecode | Visual Screen Action (What Viewer Sees) | Voiceover Script (What Speaker Says) |
|---|---|---|
| 0:00 - 0:05 | Full screen terminal; rapid CLI command execution. | "Tired of AWS IAM permission errors killing your CI pipeline?" |
| 0:05 - 0:18 | Zoom in 120% on error log; switch to browser UI. | "Here is how to automatically simulate and validate IAM policies in local Docker containers before pushing to production." |
| 0:18 - 0:42 | Split screen: VS Code on left, local emulator on right. Running test suite. | "First, install the CLI via Homebrew. Run `policy check`. Notice how our engine catches the wildcard resource violation instantly..." |
| 0:42 - 0:55 | Clean success checkmark in terminal; GitHub PR merge. | "Zero cloud roundtrips. 100% offline verification. All in under 200 milliseconds." |
| 0:55 - 1:00 | Clean end card with GitHub repo URL and star badge. | "Check out the repo at github.com/[org]/[repo]. Link in description." |

## 3. Production Checklist
- [ ] Terminal font size set to 20pt.
- [ ] Desktop notifications silenced.
- [ ] Audio normalized to -16 LUFS.
- [ ] Code snippets pre-tested and syntax highlighted.
```

---

## Worked Example: 60-Second Developer Launch Teaser

- **Product**: Fast JSON parser CLI tool in Rust.
- **Opening Shot**: Side-by-side terminal benchmark: standard `jq` processing a 5GB JSON file (taking 14 seconds) vs the new CLI parsing it in 1.2 seconds.
- **Narrative**: No intro logo. Direct side-by-side timer. Voiceover explains the SIMD vectorization mechanics in 3 concise sentences.
- **Impact**: Video generated 120,000 views on X and 1,800 GitHub stars in 48 hours.

---

## Verification Checklist

- [ ] First 5 seconds immediately demonstrate the problem or final result.
- [ ] Screen recordings use large font sizes (18pt+) legible on mobile devices.
- [ ] All idle typing pauses, compilation delays, and wait times are cut out.
- [ ] Vocal audio is normalized to -16 LUFS with background music kept at -26dB.
- [ ] End screen includes a clear, single call to action (URL or GitHub repo).

---

## Anti-Patterns

- **Vanity Intros**: Spending the first 10 seconds of a video displaying spinning 3D logos.
- **Unreadable Code**: Recording an entire 4K desktop monitor where terminal text is microscopic on mobile screens.
- **Mumbling & Bad Audio**: Using tinny laptop microphones with room echo and uncompressed background noise.
