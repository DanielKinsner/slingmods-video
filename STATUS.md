# STATUS — slingmods-video pipeline

Updated: 2026-07-31 morning (office PC)

## Done
- **Fresh-test round 2 (Opus 5, xhigh) analyzed + debriefed (2026-07-31):** v03 cut 4:53/37 —
  stronger reasoning (evidence-driven side pick, punch-ins, kit-contents idea), weaker perception
  (false "no tool" claim traced to a crop window that excluded the tool; verified from its own
  saved crops). Both fresh agents were interrogated post-hoc; their answers + Dan's v03 notes are
  encoded in TASTE (rules 2c-2e, 3-5 rewording, 5c/5d, 12, 17) and the skill (frame-level
  verification pass, docs-never-veto-footage, crew-audio-as-hint) — commits 972fc1d, 717f1d9.
  **Decision: v02 (Fable fresh) is the keeper for handguards** — Dan finesses it (~2 min of work);
  timeline intact in Resolve project "evolutionr_canyon handguards FRESH", cut list + render in
  `99_claude\`/`05_exports\review\`. No Premiere rebuild needed (Dan's own edit lives in the
  04_edit prproj). Caveat noted: agent debriefs are post-hoc reasoning — rules were kept
  behavioral, not tuned to this footage's specifics.
- **Fresh-agent generalization test PASSED (2026-07-30 evening):** a context-free session cut the
  same footage from repo docs alone (WORKFLOW-RULES + TASTE + skills; STATUS/receipts/renders
  quarantined). Result `handguards_install_v02_fresh`: 4:01 / 22 cuts — structurally Dan-shaped
  (one side only, glamour shot as the "repeat other side" beat, pointing inserts dropped, beats
  deliberately long for trimming) where v01-with-context was 4:27 and structure-divergent.
  Verdict: TASTE.md + skills carry the editing knowledge; remaining gap is pacing/fastener
  screen-time distribution (intentionally long) and open taste questions (cold-open placement,
  glamour enders in install body). Caveat: TASTE was derived from this footage — true
  generalization test is the next new shoot. Three-way diff vs Dan's finesse (2:40 / 33 cuts)
  in this session's transcript; Dan's finesse lives in `04_edit\evolutionr_canyon_handguards.prproj`
  as "handguards_install_v01 DAN FINESSE".
- **Discovery pilot CUT (2026-07-30): evolutionr_canyon handguards — picture-first MOS install
  edit, no script/VO/product page.** 4:27 rough cut in Resolve (`handguards_install_v01`),
  20 cuts + 3 muted V2 alternates, 4 chapter + 4 question markers, review render in
  `05_exports\review\`. What the footage supported: full BRP-deflector story (remove → bench
  assembly → reinstall → final), side A full / side B compressed. Judgment calls that came up:
  (1) the two instruction docs describe DIFFERENT products — BRP PDF matches footage, Dan's
  photographed sheet is a different aftermarket kit, kept for reference only; (2) presenter
  points at things in insert clips 5744/5745 — inaudible without transcription, kept + flagged;
  (3) no Loctite, film-peel, or mirror-readjust moments on camera — VO/pickup flags in markers.
  Process learning: 4s contact sheets alone misplace ~30% of cut points (6/20 landed on empty
  frames/dead beats) — a boundary-frame QC pass before render is now the discovery-mode norm,
  plus a contact-sheet watch of the RENDER itself (caught a 5s dead-air tail and a V2 alternate
  overhanging the timeline end → 6s black tail). Resolve render gotchas: default render is
  timeline-resolution 4K (~4.7GB) — always set FormatWidth/Height 1920x1080 for review copies;
  render range covers disabled tracks' extent, so alternates must never extend past V1's end.
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
- `WORKFLOW-RULES.md` approved as working doc (Dan, 2026-07-30) — E: backup-gated, M: hands-off until specified.
- **23.976 sequence standard confirmed against ground truth 2026-07-30:** all sampled channel uploads are 24000/1001. Tick-math table in skills independently re-verified (6/6 exact-integer match).

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
- [x] Update skills with round-trip gotchas — done 2026-07-30: rebuild doctrine in `slingmods-video`
  skill (no `create_sequence`, ES sequence creation, mandatory tick-readback diff, fps/tick table),
  cut-list conventions in `slingmods-install`, verification line in WORKFLOW-RULES §9.
  **Sequence standard confirmed by Dan: 23.976** (sources mixed: 120fps glamour, 29.97, etc.).
- [ ] Point Resolve cache/optimized-media locations at `E:\claude\resolve\` (needs Resolve open).
- [ ] Update skills for the Resolve-draft handoff once rules are approved.
- [ ] Capture Dan's sequence preset (res/fps) from a real .prproj during pilot; bake into skills.
- [ ] Possible `slingmods-publish` skill: YouTube title/description/chapters/tags formula (titles follow "Product for the Vehicle" pattern — data already in analysis/summary.json).

## Next milestone
**f3t exhaust v01 PASSED the generalization test (2026-07-31, Opus high):** 2:34/18 cuts, all six
doc steps landed incl. OE-removal (the chronic miss), rule-5c absence evidence used correctly
(off-camera nut removal, 3 saved uncropped frames), washer-trap avoided in both directions, zero
dead air, mechanics frame-exact. Dan's grade: near-perfect rough; misses = opener composition
(edge-cropped tool-hold → TASTE 9/9b rewritten: tool-ID isn't house style, tools get their own
segment) + minor pacing trims. Opus agent to rebuild it in Premiere next (rebuild block is in the
cut list). VO conform is permanently Dan's (TASTE 17b).

Previous milestone (for reference):
**thermal_spyder f3t exhaust — INSTALL SECTION ONLY, fresh-agent generalization test** (the first
run on footage TASTE was not derived from; no quarantine needed). 5 install clips @23.976 (~6 min
total). `00_docs\spyder RT instructions as reference.txt` is Dan-authored + verified from a
near-identical RT install: treat as expected beat structure, footage stays ground truth. B-roll
(28 clips) is explicitly out of scope for this pass; glamour/talking-head/stock buckets empty;
README PROJECT INFO unfilled. Claude-lead grades the result against TASTE + Dan's finesse.

## Machines
Office PC = fully set up. Home PC / MacBook = nothing installed yet (repo README has install steps; MCPs would need per-machine setup).
