# STATUS — slingmods-video pipeline

Updated: 2026-07-30 evening (office PC)

## Done
- **Round-trip test PASSED (2026-07-30): Resolve draft → MCP-native Premiere rebuild, 12/12 track
  items frame-accurate, 0 off-by, 0 unlinked, no XML fallback needed.** Test project:
  `E:\claude\projects\_roundtrip-test\` (cut-list.md + roundtrip-verify.md in `99_claude\`).
  Key gotchas captured in roundtrip-verify.md: MCP `create_sequence` opens a modal dialog and
  deadlocks the bridge (use ExtendScript `createNewSequenceFromClips` instead); Premiere batch
  placement is seconds-based (exact at integer fps, needs tick-math care at 29.97); Resolve
  `create_timeline_from_clips` end_frame is out-exclusive (probed).
- MCP stack installed & verified: premiere-pro (hetpatel-11), davinci-resolve (samuelgursky, mcp<2 pin), HyperFrames skills + smoke render. Office PC only.
- Style spec measured from 12 recent channel videos → `STYLE-SPEC.md` (+ raw data in `analysis/`).
- 5 skills built & installed to `~/.claude/skills/`: slingmods-video / -script / -intro / -install / -outro.
- Project template deployed: `M:\_template` (numbered pipeline folders). Old `M:\folder format` reorganized in place.
- Claude workspace created: `E:\claude\{projects,cache,resolve,renders,_archive}`.
- `WORKFLOW-RULES.md` drafted — **awaiting Dan's edit/approval.**

## Open — Dan's court
- [ ] Approve/edit `WORKFLOW-RULES.md` (then Claude updates skills to reference the Resolve-draft flow).
- [ ] Offsite backup decision (second external at home or cloud) — flagged, Dan's call.

## Decided 2026-07-30
- [x] One-time clicks DONE in both Premiere (MCP Bridge started) and Resolve (external scripting = Local).
- **ElevenLabs: Dan carries VO himself for now** (company account; wants to see edit quality first). Claude
  works against Dan-supplied VO files in `02_audio\voiceover\`. Revisit after successful tests.
- **Music: deferred the same way.** After confirmation, Dan supplies a folder of licensed Artlist/Epidemic
  regulars for Claude to pick from. Until then Dan places music.

## Open — Claude's court (after the above)
- [x] Round-trip test: dummy cut in Resolve on E: → MCP rebuild in Premiere → verify linked & frame-accurate. **PASSED 2026-07-30, see Done.**
- [ ] Update skills with round-trip gotchas: never call MCP `create_sequence` (modal deadlock);
  sequence creation via ExtendScript `createNewSequenceFromClips` + lift seed clip; verify every
  rebuild with tick-precision readback diff against cut-list.md; 29.97 fps tick-math handling
  before pilot uses real footage.
- [ ] Point Resolve cache/optimized-media locations at `E:\claude\resolve\` (needs Resolve open).
- [ ] Update skills for the Resolve-draft handoff once rules are approved.
- [ ] Capture Dan's sequence preset (res/fps) from a real .prproj during pilot; bake into skills.
- [ ] Possible `slingmods-publish` skill: YouTube title/description/chapters/tags formula (titles follow "Product for the Vehicle" pattern — data already in analysis/summary.json).

## Next milestone
**Pilot video** (option B): Dan copies `_template` into `E:\claude\projects\`, drops footage from a recent
shoot, gives product URL → Claude runs footage log → script (Dan approves) → VO → Resolve rough cut → review.

## Machines
Office PC = fully set up. Home PC / MacBook = nothing installed yet (repo README has install steps; MCPs would need per-machine setup).
