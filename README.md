# slingmods-video

The SlingMods video production pipeline for Claude + Dan. Source of truth for the style spec,
the edit-bucket skills, and the project folder template.

## What's here

- `STYLE-SPEC.md` — the house formula, measured from the 12 most recent channel videos (2026-04 → 2026-07):
  timing skeleton, cut rhythm, script formulas, voice rules.
- `skills/` — Claude Code skills, bucketed by edit section:
  - `slingmods-video` — router: pipeline order, folder contract, hard rules
  - `slingmods-script` — product page → VO script (opener/CTA formulas)
  - `slingmods-intro` — splash + 120fps glamour assembly (0:00–0:55)
  - `slingmods-install` — chaptered install rough cut + markers + alternates
  - `slingmods-outro` — the templated ~29s CTA/logo block
- `templates/project-folder-README.md` — copy of the `M:\_template` project folder contract.
- `analysis/summary.json` — raw measurements (cuts, shot lengths, VO timing, transcripts) behind the spec.

## Install on a new machine

Copy each folder in `skills/` into `~/.claude/skills/`. The project template lives at `M:\_template`
(office PC) — copy it per project and rename `vendor_vehicle_product`.

## Maintaining

The spec describes the channel as of 2026-07. When the house style shifts, re-run the measurement
(scene detection + transcripts on recent uploads), update `STYLE-SPEC.md`, and update the skills to match.
Edit skills in THIS repo first, then re-copy to `~/.claude/skills/` — the repo is the source of truth.
