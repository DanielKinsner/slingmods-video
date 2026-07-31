---
name: slingmods-video
description: Router for producing SlingMods product/install videos with Dan (media director). Use when Dan mentions a SlingMods video, a product URL + footage, a new install video, or any stage of the video pipeline. Establishes the pipeline, folder contract, and routes to slingmods-script / slingmods-intro / slingmods-install / slingmods-outro.
---

# SlingMods Video Pipeline (router)

The house formula, run ~1000 times: **splash → VO intro (glamour) → install/feature body → CTA outro.**
Full measured numbers live in `STYLE-SPEC.md` in the `slingmods-video` repo (Documents/GitHub/slingmods-video).

## Two video types
- **Product Spot** (2:00–2:40): no install section, feature tour instead. Skills: script → intro → outro.
- **Install Video** (5:30–11:00): chaptered install body. Skills: script → intro → install → outro.

## Project folder contract
Every project is a copy of `M:\_template`, named `vendor_vehicle_product`. Read its `README.md` first —
PROJECT INFO block has product URL, vehicle, vendor, and status checkboxes. Key paths:
- `00_docs\` scripts + vendor PDFs · `01_footage\{glamour,install,broll,stock,images}`
- `02_audio\{voiceover,music,sfx}` · `03_graphics\{logos,overlays,...}` · `04_edit\` (.prproj)
- `05_exports\{review,final,thumbs}` · `99_claude\` (YOUR workspace: footage-log.md, cut-list.md, event-log.md)

## Drives & rules of the road (full text: WORKFLOW-RULES.md in the repo)
- Claude works on **E:** (projects live in `E:\claude\projects\`). **M: is hands-off until Dan specifies.**
- **Kickoff gate: confirm with Dan that E: is backed up** before starting any project.
- Drafting happens in **DaVinci Resolve**; Premiere is Dan's bay — MCP touches it only on Dan's go, and any
  work on a final timeline starts with Save As → `*_claude.prproj` version.

## Pipeline order
1. **Ingest** — inventory `01_footage\`; auto-split glamour vs install by fps (`ffprobe` — 120/60fps = glamour
   candidates). Frame-sample + transcribe narration + audio-transient scan. Transcribe CREW audio too —
   off-hand remarks settle part/side identity (proven 2026-07-30: "It's the right side" drove side
   selection + continuity). Write `99_claude\footage-log.md`
   and flag garbage (blur/exposure). Show Dan the log BEFORE cutting.
2. **Script** — `slingmods-script`. Dan approves. Always.
3. **VO** — *current phase:* Dan generates ElevenLabs VO himself and drops per-section files in
   `02_audio\voiceover\`. Dan also places music for now.
4. **Draft** — `slingmods-intro`, then `slingmods-install` (install videos only), then `slingmods-outro` —
   assembled in **Resolve on E:**, keeping a data cut list (`99_claude\cut-list.md`: clip path, in, out, track).
5. **Review** — render review copy to `05_exports\review\`, tell Dan exactly what to check and what's flagged.
6. **Handoff** — on approval, rebuild the timeline **natively in Premiere via MCP from the cut list**
   (no XML, no baked re-detect; XML is fallback — using it is a finding to report, not a silent switch).
   Rebuild is not done until the readback diff (below) is clean. Dan transfers/relinks to M: on his side.

## Premiere MCP rebuild doctrine (proven by round-trip test 2026-07-30 — receipt: `analysis/roundtrip-verify-2026-07-30.md`)

**Sequence standard: 23.976 fps (24000/1001).** Sources are mixed-rate (120fps glamour, 29.97 install, etc.) —
the cut list must record each clip's native fps (`ffprobe`), never assume it.

1. **NEVER call the MCP `create_sequence` tool.** Without a preset it opens Premiere's modal New Sequence
   dialog and the whole bridge goes deaf (even ping) until a human dismisses it. Create sequences via
   `execute_extendscript`: `app.project.createNewSequenceFromClips(name, [projectItem])` (dialog-free,
   matches the seed clip's format — seed with a clip of the target format), then lift the seed clip
   (video and audio are separate track items; remove both).
2. **Placement is seconds-based** (`add_to_timeline_batch`: `time`, `sourceInPoint/sourceOutPoint`).
   Convert with rational math at full precision: timeline frame N @23.976 → `N * 1001 / 24000` s;
   source frame F → `F / native_fps` s (rational, e.g. `F * 1001 / 30000` for 29.97) — **then add
   +2 ms to every value** (time, in, out). Measured 2026-07-30 (Premiere 26.3): raw float values
   land a hair below the frame boundary and Premiere FLOORS a full frame — 6/23 items came in
   off-by-one (short cuts with 1-frame gaps, shifted sources) until the +2 ms bias fixed all of
   them. Removing a linked video item can also strand a 1-frame audio sliver — re-verify audio.
   The batch result's `inPoint/outPoint` are TIMELINE positions, not source — never diff against them.
   Project open/create via API refuses on Premiere 26.3 (create_project/open_project/app.newProject
   all return false): Dan opens the target .prproj manually; the bridge works only inside it.
3. **Mandatory verification — no rebuild is reported done without it.** Read every track item back via
   `execute_extendscript` in **ticks** (254,016,000,000 ticks/sec; integer per frame at every Premiere rate)
   and diff against `cut-list.md`: source path, source in/out, timeline in/out, track — show the table.
   Ticks per frame: 23.976 → 10,594,584,000 · 29.97 → 8,475,667,200 · 30 → 8,467,200,000 ·
   59.94 → 4,237,833,600 · 60 → 4,233,600,000 · 120 → 2,116,800,000.
   Pass = 0 frame deltas at the timeline rate. Any nonzero delta or unlinked item = stop and report.
4. **Resolve side:** `create_timeline_from_clips` `end_frame` is out-**exclusive** (probed on
   Studio 20.2.2.10). Cut lists use 0-based frames, out-exclusive, and are written from Resolve's
   readback (`timeline.source_range_report`), never from intent.

## Discovery mode (when inputs are missing — common, not exceptional)
Many real projects arrive incomplete: no product page yet, no script, no VO, thin vendor instructions.
**The pipeline is a default, not a gate.** Never block or nag for missing inputs — adapt:
- No script/VO → cut **picture-first** (silent/MOS): sequence the install logically from the footage +
  whatever docs exist (vendor PDF, Dan's notes), pace it watchably, leave room for VO to be written to
  the cut later ("cut first, write to picture" — the reverse of the formula, equally legitimate).
- No product page → skip script formulas; note what's missing in the review handoff, don't invent facts.
- **Vendor docs never veto footage.** `00_docs` often holds sheets for similar-but-differently-named
  products. If the footage shows a step (e.g. washers onto screws), it's IN the cut even if the
  best-matching doc omits it — footage is ground truth for what happened; docs only inform order and
  naming. Never conclude a hardware step "belongs to the other product."
- The style spec still applies where it can (chapter order, insert close-ups, honest pacing) — as
  reference, not requirement. Creative judgment over formula compliance. When in doubt, make the cut
  and flag the doubt as a marker instead of stopping to ask.

## Resolve review renders (measured 2026-07-30)
- Always set `FormatWidth/FormatHeight` **1920×1080** on review renders — Resolve defaults to
  timeline resolution (4K ≈ 4.7GB for 4½ min).
- The render range covers DISABLED tracks' extent: **muted V2 alternates must never extend past
  V1's end** or the render grows a black tail. Trim alternates flush.
- After rendering: ffprobe the frame count against the cut list AND contact-sheet-watch the
  render itself (catches dead-air tails and black gaps that per-cut QC misses).

## Hard rules
- **Read `TASTE.md` (repo root) before cutting anything, and check every chapter against it
  before rendering** — it's Dan's editing-style ledger, grown from finesse-diffs; the
  hardware-completeness checklist (rule 5b) is verified with full-res frame crops, not
  contact sheets.
- Dan finesses every install section — deliver rough cut + markers + muted alternates track, not "final."
  Alternates are placed AT the beat they'd replace (never parked at the timeline head) and trimmed
  flush with V1's end.
- **"The footage doesn't show X" is a verified claim, not an observation** (TASTE 5c): save the checked
  full-res crops to `99_claude\qc\` and re-check at different timestamps before writing it. A false
  absence silently deletes real beats (proven 2026-07-31: a false "no tool at the bench" removed the
  tool-tightening beat from both sides of a cut).
- Rough-cut accuracy promise is ±1s per cut. Don't claim better.
- Fitment years/models in any copy come from the product page verbatim — never paraphrase fitment.
- Subagents get exact paths, never "go find it." Externals are never touched, connected or not.
