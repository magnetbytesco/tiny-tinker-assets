# Asset Ledger — Live State

Last updated: 2026-08-13 12:57 PKT, after Day 1 push (9 posts scheduled: `6a7d787f`, `6a7d7892`, `6a7d7896`, `6a7d78ad`, `6a7d78bc`, `6a7d78c8`, `6a7d78d7`, `6a7d78f1`, `6a7d78f5`).

**Purpose:** ground truth for the nightly auto-topup routine. Read this before pulling any asset — do not re-derive from folder listings, and do not re-use anything listed as used/sent/flagged below. Update this file at the end of every topup run.

**Day boundary: 8:00 PM PKT to 7:59 PM PKT next day.** Topup runs nightly at 7:00 PM PKT (1 hour before day start) to fill the next day's slots.

**Daily cap (per-day target, not to exceed): Pinterest 4, Instagram 3 (100% video), Facebook 2 = 9 total.**
**Buffer hard cap: 10 scheduled posts organization-wide at any moment — never schedule past this; check `list_posts` status=scheduled count first.**

---

## Instagram: must be 100% video (Reels). No static IG posts.

### Real (non-converted) video — highest priority, use before any converted reel
| File | Status |
|---|---|
| `pins-new/reel-waiting-room.mp4` | SENT to Instagram 2026-08-13 03:30 PKT. Available to crosspost to **Pinterest only** (as a video pin, new caption) — not IG again. |
| `pins/SimpleSixSkills.mp4` | SCHEDULED Instagram 2026-08-14 01:05 PKT (post `6a7d78c8`). Exhausted. |
| `pins-new/reel-travel-kit.mp4` | SCHEDULED Instagram 2026-08-13 21:05 PKT (post `6a7d78bc`). Exhausted. |
| `pins-new/reel-gift-idea.mp4` | SCHEDULED Instagram 2026-08-14 09:05 PKT (post `6a7d78d7`). Exhausted. |

**Zero real unused video remains for Instagram as of this update.** Converted reels (below) are required for Day 2 onward.

### Converted reels (static→motion, Ken Burns/text-reveal build)
Populated by the production agent. Until this section has entries, the topup routine **must not** post a static image to Instagram — skip the IG slot and flag it rather than break the 100%-video rule.

| File | Source pin | Status |
|---|---|---|
| *(pending production run)* | | |

---

## Pinterest: static-first (~65/35 static/video), video pins welcome

### Unused fresh static
| File | Notes |
|---|---|
| `pinboards-fixed-domain/pin-22-travel-kit.png` | Guilt-Relief pillar |
| `pinboards-fixed-domain/pin-09-six-skills.png` | Offline-Learning pillar |
| `pinboards-fixed-domain/pin-38-cinematic-maze.png` | Puzzle-Curiosity pillar |
| `pinboards-fixed-domain/pin-39-cinematic-village.png` | Puzzle-Curiosity pillar |
| `pinboards-fixed-domain/pin-26-gift-idea.png` | Not-a-Worksheet pillar |

### Unused fresh video
| File | Notes |
|---|---|
| `pins-new/reel-waiting-room.mp4` | Already sent on IG — fine to crosspost here, new caption, not yet used on Pinterest |

### Used today (Day 1) — do not reschedule
`pin-24-waiting-room.png`, `pin-20-maze-teaser.png`, `pin-36-cinematic-repair.png`, `pin-37-cinematic-driftworlds.png`

---

## Facebook: ~50/50 static/video

### Unused fresh static
| File |
|---|
| `pinboards-fixed-domain/pin-22-travel-kit.png` *(if not used on Pinterest first — do not duplicate same asset same week across platforms without checking this file)* |
| `pinboards-fixed-domain/pin-09-six-skills.png` *(same caveat)* |

### Used today (Day 1) — do not reschedule
`pin-23-restaurant-wait.png`, `pin-27-stocking-stuffer.png`

---

## Permanently excluded — never schedule, any platform

- `TheCrash-fixed.mp4` — duplicates IG organic posts from 2026-05-25/28 (crash-landing narrative already told)
- `pin-14-rainy-day.png` — duplicates sent `SimpleRainyDay.mp4` (verbatim phrase reuse)
- `pin-11-hates-reading.png` — duplicates sent `pin-reluctant-reader.mp4`
- `pin-13-no-nagging.png` — duplicates sent `pin-no-nagging.mp4` / `SimpleNoNagging.mp4`
- `SimpleLeadMagnet.mp4` — duplicates sent 08-02 IG post
- `SimpleNotAWorksheet.mp4` — duplicates sent `pin-08-not-a-worksheet.png`
- `pin-back-to-school.mp4`, `pin-meltdown-countdown.mp4`, `pin-no-nagging.mp4`, `pin-roadtrip.mp4` — dead-domain bug, live on Pinterest; fixed versions exist in `pins-fixed/` if a swap is ever authorized
- All 10 files in `pinboards/` listed in FULL-ASSET-CATALOG.md Section 5.4 — dead domain burned into frame, unfixed
- `puzzle-assembly.mp4`, `spot-the-difference.mp4` — inconclusive verification, needs human re-check before use
- Everything in `pins-final/` (stale, 45 files, confirmed different/superseded content)
- Everything in `video-studio/out/` predating the `pin-*`/`Simple*`/`Reel*`/`reel-*` naming (never pushed to CDN, unverified)

---

## When this ledger runs dry

If Instagram's converted-reels table and Pinterest/Facebook's unused-fresh tables are all empty on a given topup run: **do not schedule a repeat or a flagged asset to hit the daily count.** Skip the slot, note it in this file under a "GAPS" section, and surface it to the user at the next conversation — do not silently lower quality to hit a number.
