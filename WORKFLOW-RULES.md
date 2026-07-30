# Workflow Rules — DRAFT (pending Dan's approval)

> Status: **DRAFT.** Dan owns codification. Edit, strike, or rewrite anything here; Claude follows the
> approved version and updates the skills to match only after Dan signs off.
> Agreed in conversation 2026-07-30.

## Drive roles

| Drive | Role | Claude access |
|---|---|---|
| **M:** | Dan's finishing world — Premiere projects, final media | Deliver-only: VO files, overlays, MCP timeline rebuilds. Never reads source media from M:. |
| **E:\claude\** | Claude's entire world — drafts, caches, Resolve work, renders | Full. Everything Claude touches lives here. |
| **E:\ (rest)** | Dan's existing projects and caches | Off-limits. |
| **14TB external(s)** | Backup truth | **Never touched, connected or not.** Stays physically disconnected except during Dan's transfer sessions. |

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
   XML export is the fallback if MCP rebuild misbehaves.
10. Dan paces/finesses every install final. Claude's deliverable is rough cut + chapter markers + muted
    alternates track + flagged questions.

## Hygiene

11. Nothing at E:\claude root — files live in the five known folders. Ambiguous/stale things go to `_archive\`,
    never deleted by Claude (`_trash\` inside projects means "Claude wanted to delete, Dan decides").
12. Subagents inherit all of the above and get exact paths, never "go find it."
