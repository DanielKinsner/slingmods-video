# SlingMods Video Project

> Copy `M:\_template` → rename to `vendor_vehicle_product` (example: `thermal_slingshot_sport-exhaust`).
> Fill in the PROJECT INFO below. Everything else has a home — use it and Claude can run the pipeline.

## PROJECT INFO (fill this in)

- **Product:**
- **Product URL:** https://www.slingmods.com/
- **Vehicle:** (Slingshot / Spyder RT / Spyder F3 / Ryker / Canyon)
- **Vendor:**
- **Vendor install instructions:** (PDF in `00_docs\` — yes/no)
- **Status:** footage dumped ☐ · script approved ☐ · VO generated ☐ · rough cut ☐ · finessed ☐ · exported ☐

## Folder map (numbered = pipeline order)

| Folder | What goes in it | Who fills it |
|---|---|---|
| `00_docs\` | Approved script, script drafts, vendor install PDF, product page notes | Claude (Dan approves) |
| `01_footage\glamour\` | 120fps beauty shots for the slow-mo intro | Camera guy |
| `01_footage\install\` | The install footage, in shoot order | Camera guy |
| `01_footage\broll\` | Product demos, riding shots, everything else | Camera guy |
| `01_footage\talking-head\` | On-camera host bits (rare now) | Camera guy |
| `01_footage\stock\` | Licensed stock clips | Dan |
| `01_footage\images\` | Product stills, vendor photos | Dan |
| `02_audio\voiceover\` | ElevenLabs VO renders, named `intro-v1.mp3`, `install-v1.mp3`, `outro-v1.mp3` | Claude |
| `02_audio\music\` | Music beds | Dan |
| `02_audio\sfx\` | Sound effects | Dan / Claude |
| `03_graphics\logos\` | Brand splash + outro (already in template) | Template |
| `03_graphics\overlays\` | Generated overlays: callouts, lower thirds, spec cards | Claude |
| `03_graphics\backgrounds\` | Background plates | Dan |
| `03_graphics\stills\` / `screenshots\` | PNGs, frame grabs, thumbnail source images | Dan |
| `04_edit\` | The `.prproj` and autosaves. Nothing else. | Premiere |
| `05_exports\review\` | Rough-cut review copies from Claude | Claude |
| `05_exports\final\` | The deliverable | Dan |
| `05_exports\thumbs\` | Thumbnail exports | Dan |
| `99_claude\` | Claude's workspace: footage log, cut list, event log, analysis cache. Safe to delete anytime. | Claude |

## Rules that keep the pipeline working

1. **No spaces in new folder or file names.** Use `-` or `_`. (Spaces break scripts.)
2. Footage goes in the right bucket at card-dump time — that's the whole organization job. Claude sorts glamour vs install automatically by frame rate as a backstop, but buckets keep it honest.
3. One project = one folder. Never point a project at another project's media.
4. `_trash\` anywhere means "Claude wanted to delete this but left it for Dan."
