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

## Pipeline order
1. **Ingest** — inventory `01_footage\`; auto-split glamour vs install by fps (`ffprobe` — 120/60fps = glamour
   candidates). Frame-sample + transcribe narration + audio-transient scan. Write `99_claude\footage-log.md`
   and flag garbage (blur/exposure). Show Dan the log BEFORE cutting.
2. **Script** — `slingmods-script`. Dan approves before VO generation. Always.
3. **VO** — ElevenLabs (key in local .env, never in chat). Render per-section files to `02_audio\voiceover\`.
4. **Assemble** — `slingmods-intro`, then `slingmods-install` (install videos only), then `slingmods-outro`.
   Premiere MCP does timeline work; requires Dan's Premiere open with MCP Bridge panel started.
5. **Review** — export rough cut to `05_exports\review\`, tell Dan exactly what to check and where markers are.

## Hard rules
- Never edit while Dan is actively cutting (MCP drives his live Premiere).
- Dan finesses every install section — deliver rough cut + markers + muted alternates track, not "final."
- Rough-cut accuracy promise is ±1s per cut. Don't claim better.
- Fitment years/models in any copy come from the product page verbatim — never paraphrase fitment.
