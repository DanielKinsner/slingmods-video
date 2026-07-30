# Round-trip verification — 2026-07-30

Resolve `roundtrip_v01` (project `_roundtrip-test`) → Premiere `roundtrip_v01_rebuild`
(in `E:\claude\cache\mcp_scratch.prproj`). Rebuild was **MCP-native** (no XML fallback needed).

Premiere readback method: ExtendScript over the bridge, reading each trackItem's
`start/end/inPoint/outPoint` in **ticks** (8,467,200,000 ticks/frame @ 30fps), divided to exact
frame numbers. No float rounding involved. Frames 0-based, out-exclusive — same convention as cut-list.md.

## Diff: cut-list.md vs Premiere readback (video V1)

| # | Clip | Src in (list→PPro) | Src out (list→PPro) | TL in (list→PPro) | TL out (list→PPro) | Δ |
|---|---|---|---|---|---|---|
| 1 | RT_C001_BARS  | 30 → 30  | 120 → 120 | 0 → 0     | 90 → 90   | 0 |
| 2 | RT_C002_RED   | 60 → 60  | 180 → 180 | 90 → 90   | 210 → 210 | 0 |
| 3 | RT_C003_GREEN | 0 → 0    | 90 → 90   | 210 → 210 | 300 → 300 | 0 |
| 4 | RT_C001_BARS  | 180 → 180| 270 → 270 | 300 → 300 | 390 → 390 | 0 |
| 5 | RT_C004_BLUE  | 45 → 45  | 165 → 165 | 390 → 390 | 510 → 510 | 0 |
| 6 | RT_C002_RED   | 200 → 200| 260 → 260 | 510 → 510 | 570 → 570 | 0 |

Audio A1: 6 linked items, identical numbers to V1 on every clip — 0 deltas.
Media paths: all 12 track items resolve to the correct files under
`01_footage\install\card01\` — nothing unlinked, nothing offline.

**Result: 12/12 track items frame-accurate. 0 off-by errors. 0 unlinked.**

## Findings (workflow, not failures)

1. **`create_sequence` (MCP) deadlocks the bridge.** Without a preset file it opens Premiere's
   modal New Sequence dialog; all scripting (even ping) times out until a human dismisses it.
   Rule for skills: NEVER call `create_sequence` — create sequences via
   `app.project.createNewSequenceFromClips` (ExtendScript, dialog-free, auto-matches media
   format), seed clip lifted afterwards.
2. **`create_sequence_from_clips` (MCP tool) couldn't find items** ("No project items found")
   with both `projectItemIds` and `clipIds` param spellings; the ExtendScript route worked
   first try. Treat the ES route as canonical until the tool is understood.
3. **`import_media` binName is cosmetic-at-best**: items requested into bin "roundtrip-test"
   landed at project root (readback showed 0 bins).
4. **Premiere batch placement takes seconds, not frames.** At integer 30fps conversion is exact;
   at 29.97 (real footage) frame→seconds must go through ticks/frame math, then verify by
   readback. The batch tool's returned `inPoint/outPoint` are TIMELINE positions, not source —
   don't diff against those; use the tick readback.
5. **Resolve `create_timeline_from_clips` end_frame is out-EXCLUSIVE** (probed mechanically,
   Studio 20.2.2.10 / MCP 2.68.2).
