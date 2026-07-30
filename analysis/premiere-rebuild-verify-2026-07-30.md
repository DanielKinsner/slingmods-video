# Premiere rebuild verification — handguards_install_v01

2026-07-30. Resolve draft → MCP-native Premiere rebuild (no XML). Project:
`04_edit\evolutionr_canyon_handguards.prproj`, sequence `handguards_install_v01`
(3840×2160 @ 23.976, timebase readback 10,594,584,000 ticks/frame — exact).

## Final result: 23/23 track items frame-exact vs cut-list.md, 0 deltas, 0 unlinked

All 20 V1 cuts + 3 V2 alternates match cut-list.md exactly on source file, source in/out,
timeline in/out (frames @ 23.976, tick-precision readback). V2 hidden + A2 muted (alternates).
8 markers (4 chapter green, 3 question red, 1 blue cold-open) at chapter frames.

## What the first pass measured (THE fractional-fps finding)

First placement used seconds = frame × 1001/24000 as float64. Result: **6 of 23 items
off by one frame** — 3 cuts one frame short (1-frame timeline gaps), 3 source-shifted −1.
Cause: floats that land a hair BELOW the frame boundary get FLOORED a full frame by Premiere.
Fix that worked: re-place with **+2 ms bias** on time/sourceIn/sourceOut (safely inside the
intended frame, far under half a frame = 20.9 ms). Second pass: all exact.
Also: removing a linked video item can leave a 1-frame orphaned audio sliver from the old
placement (found one on A2, removed) — always re-verify audio tracks too, not just video.

## Environment findings (Premiere 26.3, hetpatel-11 MCP)

- `create_project`, `open_project`, ES `app.newProject`/`app.openDocument` ALL refuse
  (return false, stay on current project). Project open/create is a HUMAN step; the bridge
  works only inside the already-open project.
- `save_project_as` behaves as "save a copy" (writes the file, does NOT switch to it) and
  its response mangles backslashes in the reported path (file lands correctly).
