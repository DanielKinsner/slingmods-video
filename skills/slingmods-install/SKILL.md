---
name: slingmods-install
description: Rough-cut the install section of a SlingMods install video from analyzed footage. Use after intro assembly when the video documents an installation. Produces chaptered rough cut + markers + alternates track for Dan's finessing.
---

# SlingMods Install Rough Cut

The technical end of the formula. Dan ALWAYS finesses this section — the deliverable is a reviewable
rough cut, never a final. Accuracy promise: cuts within ±1s.

## Analysis first (if not already in `99_claude\`)
1. Frame-sample every clip in `01_footage\install\` (1 fps contact sheet) + Whisper-transcribe installer
   narration + scan audio for action transients (ratchet clicks, impacts, drops).
2. Write `99_claude\event-log.md`: per clip — what happens, timecode ranges, take number if repeated, quality flags.
3. **Retake heuristic:** same action shot multiple times → later take wins (that's why it was reshot).
   Earlier takes go to the muted alternates track, never deleted from the cut list silently.

## Chapter structure (house canon, from channel chapters)
`[Part] removal` → `New [part] installation` → `Custom adjustments` (when applicable) → conclusion beat.
Drop a Premiere marker at each chapter start, named exactly like that — Dan exports these as YouTube chapters.

## Cutting rules (measured from channel)
- Install sections breathe: **long real-time takes (40–130s) are the norm** while VO explains. Do NOT
  over-cut the install into a montage — that's the spot format, not the install format.
- Cut in for close-up inserts on: fastener engagement, connector clicks, alignment moments. Then back out.
- Trim dead air, fumbles, and tool-hunting; keep the honest pace of the work.
- VO and action must agree: if VO says "three cranks," the shot shows three cranks (audio transients locate them).

## Timeline delivery
- Draft lives in **DaVinci Resolve on E:** — maintain `99_claude\cut-list.md` as the source of truth
  (clip path, **native fps per clip**, source in/out, timeline position, track) so the cut is rebuildable
  as data. Frames are 0-based, out-exclusive; write the list from Resolve's readback
  (`timeline.source_range_report`), not from intent. Timelines are 23.976.
- V1: the cut · V2 (muted): alternates aligned under their moment · A1: VO · A2: music (duck under VO) ·
  markers: chapters + every uncertain decision, phrased as a question Dan can answer at a glance.
- Render review copy to `05_exports\review\` and tell Dan: what to check, where the markers are, what's flagged.
- On Dan's approval: rebuild natively in Premiere via MCP from the cut list, following the
  **Premiere MCP rebuild doctrine** in `slingmods-video` (no `create_sequence`; tick-readback diff
  mandatory before reporting done). XML export is the fallback — say so explicitly if used.
