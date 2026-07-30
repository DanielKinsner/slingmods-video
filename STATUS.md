# STATUS — slingmods-video pipeline

Updated: 2026-07-30 (office PC)

## Done
- MCP stack installed & verified: premiere-pro (hetpatel-11), davinci-resolve (samuelgursky, mcp<2 pin), HyperFrames skills + smoke render. Office PC only.
- Style spec measured from 12 recent channel videos → `STYLE-SPEC.md` (+ raw data in `analysis/`).
- 5 skills built & installed to `~/.claude/skills/`: slingmods-video / -script / -intro / -install / -outro.
- Project template deployed: `M:\_template` (numbered pipeline folders). Old `M:\folder format` reorganized in place.
- Claude workspace created: `E:\claude\{projects,cache,resolve,renders,_archive}`.
- `WORKFLOW-RULES.md` drafted — **awaiting Dan's edit/approval.**

## Open — Dan's court
- [ ] Approve/edit `WORKFLOW-RULES.md` (then Claude updates skills to reference the Resolve-draft flow).
- [ ] ElevenLabs: API key + voice ID into a local `.env`; tell Claude the path. (Blocks pilot VO.)
- [ ] One-time clicks: Premiere → Window → Extensions → MCP Bridge → Start Bridge · Resolve → Preferences → General → External scripting = Local.
- [ ] Music source: where beds come from (library/subscription/folder).
- [ ] Offsite backup decision (second external at home or cloud) — flagged, Dan's call.

## Open — Claude's court (after the above)
- [ ] Round-trip test: dummy cut in Resolve on E: → MCP rebuild in Premiere → verify linked & frame-accurate.
- [ ] Point Resolve cache/optimized-media locations at `E:\claude\resolve\` (needs Resolve open).
- [ ] Update skills for the Resolve-draft handoff once rules are approved.
- [ ] Capture Dan's sequence preset (res/fps) from a real .prproj during pilot; bake into skills.
- [ ] Possible `slingmods-publish` skill: YouTube title/description/chapters/tags formula (titles follow "Product for the Vehicle" pattern — data already in analysis/summary.json).

## Next milestone
**Pilot video** (option B): Dan copies `_template` into `E:\claude\projects\`, drops footage from a recent
shoot, gives product URL → Claude runs footage log → script (Dan approves) → VO → Resolve rough cut → review.

## Machines
Office PC = fully set up. Home PC / MacBook = nothing installed yet (repo README has install steps; MCPs would need per-machine setup).
