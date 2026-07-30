---
name: slingmods-intro
description: Assemble the intro section of a SlingMods video — splash, 120fps glamour selects, VO timing. Use when building the first ~45-55 seconds of any SlingMods video after the script/VO exist.
---

# SlingMods Intro Assembly

The intro is the creative end of the formula: beauty over information. Measured law from the channel:

## Timing skeleton
1. `Slingmods Splash 4k.mp4` at 0:00 (from `03_graphics\logos\`), music from frame 0.
2. **VO enters at 0:05–0:06** (observed range 0:03–0:07 across 12 videos). Never earlier than the splash resolve.
3. Intro runs until ~0:45–0:55, then hands off to install/features.

## Shot selection
- Source: `01_footage\glamour\` — verify with ffprobe; 120fps (or 60fps) files are the slow-mo candidates.
  Conform 120fps → 23.976/29.97 timeline rate for the slow-motion look (Dan's timeline rate rules).
- **Cut every 4–6 seconds** (measured intro avg 4.2–6.0s). Vary within that band; don't metronome.
- Order shots wide → detail: establish the vehicle/product, then move closer as VO gets specific.
- B-roll of the product being USED (demo) belongs here; wrenches/install shots never appear in the intro.
- Line up shot changes with VO sentence boundaries when possible; a new sentence = a good cut point.

## When glamour footage is thin
Generate coverage with HyperFrames/Remotion instead of stretching weak shots: product stills
(`01_footage\images\`) with slow push-ins, spec callout cards, kinetic text of the product name.
Render to `03_graphics\overlays\` and place like footage.

## Deliverable
Intro section assembled on the timeline against `intro-v1.mp3`, markers on any shot Claude is unsure about.
