# Workflow Rules — working doc

> Status: **Working doc**, Dan-approved 2026-07-30. Evolves as the workflow proves itself;
> Dan has final say on changes, Claude keeps skills in sync with this file.

## Drive roles

| Drive | Role | Claude access |
|---|---|---|
| **M:** | Dan's projects and finishing world | **Hands off until Dan specifies.** Deliveries (VO, overlays, MCP rebuilds) happen when Dan says go. |
| **E:** | Claude's drive | Free to work — **precondition: E: is backed up before any project starts; confirm with Dan at kickoff.** Claude's work stays organized under `E:\claude\`. |
| **14TB external(s)** | Backup truth | **Never touched, connected or not.** Stays physically disconnected except during Dan's transfer sessions. |

## Backup gates (before work begins)

- **E:** Dan backs up E: before handing Claude a project; Claude confirms "backup current?" at every project kickoff.
- **M:** Dan populates a separate external backup of M: before ever handing Claude access to it.

## E:\claude layout

`projects\` (one folder per video, exact `_template` structure) · `cache\` (frame samples, analysis — deletable anytime) ·
`resolve\` (Resolve caches/optimized media for Claude's drafts) · `renders\` (HyperFrames/Remotion output awaiting delivery) ·
`_archive\` (stale; off-limits unless Dan says otherwise)

## Parallel work

1. **Division:** Claude drafts in DaVinci Resolve (on E:), Dan edits in Premiere. No collisions by design.
2. **Premiere is Dan's bay.** Claude drives it via MCP only when Dan hands it over ("bay's yours") and stops when Dan says he's in.
3. **Motion-graphics exception:** Claude may work a final Premiere timeline **with permission per instance**, and the
   first action is always Save As → a new versioned copy with `claude` in the filename
   (`project_v03_claude.prproj`). Dan's original file is never opened for writing. The project-file versions
   folder gets mirrored to an external on Dan's transfer days.

## Media integrity

4. **Source filenames never change** between copies (relink matches by name). Analysis proxies are separate files;
   cut lists always reference copies of the originals.
5. **Identical folder trees on E: and M:** — transfer = copy the whole project folder; relink is one click or unnecessary.
6. **Verified copies only** for card→E:, →external, →M: transfers (robocopy or TeraCopy with verification).
7. **Per-card subfolders** inside `01_footage\` so camera numeric filenames can't collide.

## Handoff (draft → final)

8. Claude drafts install cut in Resolve → renders review copy to the project's `05_exports\review\`.
9. On approval: Claude rebuilds the timeline natively in Premiere via MCP from the cut list (no XML, no baked
   export). Rebuild may happen on E: before transfer; Dan transfers to M: and relinks (his step, always).
   XML export is the fallback if MCP rebuild misbehaves — and using it gets reported, never silently.
   **A rebuild is verified by a frame-level readback diff against cut-list.md before Dan is told it's ready.**
10. Dan paces/finesses every install final. Claude's deliverable is rough cut + chapter markers + muted
    alternates track + flagged questions.

## Hygiene

11. Nothing at E:\claude root — files live in the five known folders. Ambiguous/stale things go to `_archive\`,
    never deleted by Claude (`_trash\` inside projects means "Claude wanted to delete, Dan decides").
12. Subagents inherit all of the above and get exact paths, never "go find it."

## Current phase (revisit after successful tests)

13. **VO:** Dan generates ElevenLabs VO himself (company account) and drops files in `02_audio\voiceover\`.
14. **Music:** Dan places music; a folder of licensed Artlist/Epidemic regulars comes to Claude later.
