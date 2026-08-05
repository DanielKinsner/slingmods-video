# STATUS — slingmods-video pipeline

Updated: 2026-08-05 end of day (office PC)

## 2026-08-05 — f3t exhaust motion-graphics session (Premiere MCP, live in Dan's project)
- **thermal_spyder f3t exhaust:** Dan's near-final edit got a full graphics pass, built in a
  lab duplicate ("CLAUDE LAB — f3t graphics") of his `f3t_exhaust_install_v01`; his sequence
  untouched, originals disabled-not-deleted. VERIFIED on the timeline (readback, 0 frame
  deltas) and saved: Bench Scan tools card (capsules traced around real tools, anchor-verified
  vs the photo's live transform), Torque Target bolt callout (old yellow circle was ~350px off
  the actual hanger bolt — retargeted to the real fastener), The Scale Tips weight scene
  (Dan's Photoshop muffler cutouts on a hairline balance beam, real Mettler scale-readout
  crops as proof insets, count-roll to 11.55 lb, −4.2 LB stamp; synthesized SFX bed muted on
  A1), Machined Pills end card (lands on his existing click SFX beats), 3 Machined Tags, an
  optional chapter light-sweep, and two template-matched "Important" banners (cool-down @1:23,
  torque spec @2:36, exact wording from Dan's references). Whisper VO transcripts drove all
  callout timing. Receipts: project `99_claude\event-log.md` (3 rounds) + `99_claude\gfx\`
  (design bible, PICK-LIST, anchor-check composites).
- **The session's big lesson → TASTE 20c:** graphics direction is reference-first (prose →
  "lackluster"; concept-doc verdicts → good; Dan's frame references → "slay"), and the asset
  pipe runs both ways — ask Dan to generate/produce assets even for agent ideas.
- **New MCP gotchas → skill §5:** export_frame/capture_frame are silent no-ops (ffmpeg on
  source media is the frame-truth fallback); Premiere file-locks block in-place .mov
  overwrites (new-filename + re-place recipe; timestamp-verify every batch conversion —
  two silent stale-file failures in one session).
- **Open next:** POLISH PASS (Dan, tomorrow) — retry a few scenes with the reference-first +
  Dan-makes-assets loop; his generated brushed-steel balance-beam prop swaps into the weight
  scene (queued in project PICK-LIST); weight-scene SFX bed audition; Dan turned in the
  review-version cut today.

## 2026-07-31 afternoon — VO-first pipeline opened up (carplay), Premiere automation proven
- **Slingshot CarPlay video (E:\claude\projects\evolutionr_usb car play):** first VO-first build.
  Lead session wrote reference anatomy (Can-Am act 1) + build brief; Fable builder agent delivered
  Act1+Sections2-3 (4:05, `slingshot_carplay_act12_v02_review.mp4`) with 16 GFX overlays, hidden
  OPTIONS track (Dan's favorite elements), honest flags (no lit LED / Allow-dialog never filmed /
  no clean start-press). Dan's feedback encoded same-day (TASTE 18-22, 17c/17d, 20b, 9 rewritten,
  10b reversed). Freestyle motion-design agent FIRED with design bible
  (`99_claude\freestyle-animation-designs.md`: 7 full-screen scenes, 5 overlays, transitions
  addendum) + style law v2 (Apple-launch sleekness; NOT the doodle look). Renders land in
  `overlays\generated\freestyle\`.
- **Premiere MCP automation proven live in Dan's project** (lab sequence "CLAUDE LAB — carplay
  act1", his sequence untouched): read-framing→relative keyframing (30 kfs/11 clips), generated
  assets (ProRes 4444 alpha round trip — HUD frame, callout chips, ripple transitions, kinetic
  type, doodle card, bg plates in `overlays\generated\lab\`), import→place→save. Doctrine + API
  gotchas encoded in skill §5 (ES surface is a STUB — don't diagnose bridge dead from it).
- **Dan's pipeline caveats (his words, the CarPlay lessons):** VO must be paced/phrased right the
  first time; some shots off base; footage usability must be verified up front (camera-guy risk);
  agents need clear direction, not "be creative"; SKU/product page must exist for final; written
  install instructions needed BEFORE rough cut; boss-driven changes kill overlay timing →
  graphics pass belongs LAST. Perfect-world one-shot prompt drafted in transcript.
- **Open next:** Phase-0 backtest (agent drafts install instructions from exhaust footage cold;
  grade vs Dan's verified RT doc — Dan has projects queued, waiting for a work session); grade
  freestyle portfolio (keepers graduate style to TASTE/STYLE-SPEC); Dan finesses exhaust v01 +
  handguards v02; possible slingmods-spot skill once VO-first style settles.

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
