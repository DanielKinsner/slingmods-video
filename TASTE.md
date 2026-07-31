# TASTE — Dan's editing style ledger

Living doc. Every finesse-diff adds rules here; every future cut gets checked against this
BEFORE Dan sees it. Source for each rule is noted. Started 2026-07-30 from the
evolutionr_canyon handguards finesse (Claude 4:27 / 20 cuts → Dan 2:40 / 33 cuts).

## Cutting grammar (install bodies)

1. **Micro-beat cutting, not long takes.** Dan's average cut ≈ 5s vs Claude's 13s. Each
   hardware action is its own short cut. MOS "breathing room" does NOT mean long takes —
   it means clean short beats. (finesse 2026-07-30)
2. **Hardware loosening/tightening: show the "break" + ~3–4 full tool turns (~3s), never
   the full run-down** unless the process is genuinely short. T-handle pattern when
   available: break with the top of the T (full torque), then spin with the bottom.
   The rest of the action is inferred. **Rough cuts should run LONGER than final pace** —
   it's harder to add than to cut; Dan trims ends. The non-negotiable is that the ACTION is
   fully in frame so trimming is all he needs to do. Beats can lengthen whenever uncertain.
2b. **Fastener groups: first fastener gets most/all of its action; subsequent fasteners in
   the group get progressively less screen time.** (Dan, 2026-07-30)
2c. **Cut the transit, keep the action.** Cut points live in the dead space BETWEEN
   fasteners/positions — never on the action itself. v03 kept a long uncut walk from the
   top screw to the bottom screw, then cut away just as the bottom screw's loosening began.
   The move between fasteners is what gets removed; the moment work starts is what stays.
   (Dan, v03 notes 2026-07-31)
2d. **One pass per fastener — never bounce back.** Once the edit leaves a fastener it never
   returns (v03 went top screw → one turn on bottom → BACK to top). Fastener screen time is
   monotonic per rule 2b: first gets most, each next gets less, none gets a second visit.
   (Dan, v03 notes 2026-07-31)
2e. **Fumble filter.** Segments where the installer fumbles, hesitates, or handles the part
   awkwardly are ALWAYS cut — choose the smoothest coverage of every action so the
   installer looks professional. If the only coverage of an action includes a fumble, trim
   to the clean portion. (Dan, v03 notes 2026-07-31: "always should be cut out")
3. **Removal of an OE piece gets shown ~95% of the time, in frame** (e.g. bracket coming
   off the bar end). Never infer the part leaving the vehicle. **"OE piece" means every
   separable part, not just the main assembly** — if any bracket, cap, or spacer leaves the
   vehicle as its own object, its coming-off moment goes on screen, however brief (both
   fresh agents read "OE piece" as the big assembly only; debriefs 2026-07-31).
4. **Reassembly grammar (the canonical beat template):** bring bracket/part into frame →
   insert hardware finger-tight → tighten 3–4 turns with tool → optional
   "torquing" motion as the ender. Same rules as removal, mirrored. **Finger-tight and
   tool-turn stages are WANTED beats whenever the footage contains them** — earlier
   "(if shown)" wording read as optional and fed both fresh agents' skipped driver beats.
5. **Complete the micro-action.** Don't clip a beat before its point lands (washer fully
   seated on screw before cutting; finger-tight means you saw it get finger-tight).
   **This is inclusion guidance, not just trim guidance:** hardware prep — washers or
   spacers going onto screws — is a beat of its own, not b-roll (v02 read this rule as
   where-to-end-a-cut and skipped the washer zone wholesale; debrief 2026-07-31).
5b. **Hardware-completeness checklist — graded misses from fresh-test v02 (2026-07-30):**
   every install chapter gets checked against these before locking: (a) OE piece removal
   shown (rule 3 — v02 skipped the outer bracket coming off); (b) washers-onto-screws shown
   when the installer shows it; (c) tool tightening beat present with a VERIFIED on-screen
   tool turn — a still with a tool in hand can be pickup or repositioning, not tightening
   (v02 shipped exactly that); confirm the turning motion at frame level; (d) the
   FIRST fastener of a group gets its longer rotations, not only the hard "torque snap";
   (e) part brought INTO frame before attachment (rule 4 opener). These details are
   invisible at contact-sheet resolution — verify hardware beats with full-res frame crops.
   **Chronic misses: (a) OE-removal, (b) washers, and (c) tool beat were ALL missed again
   by v03 on a different model — treat these three as the highest-risk items every run.**
5c. **Absence claims require saved evidence.** "The footage doesn't show X" is as dangerous
   as "it's fixed" — v03 reported "no driver ever appears in 5743, checked full-res crops
   at 16 timestamps" while a screwdriver is plainly in use at 120.5–127s, and that false
   negative deleted the tool beat from BOTH sides of the edit. Before claiming any 5b item
   absent: SAVE the checked crops to `99_claude\qc\` (timestamp in each filename) and
   re-check on a second pass at DIFFERENT timestamps. **Absence is only provable from
   UNCROPPED frames sampled at ≤1s** — a crop is a bet about where the thing will be; v03's
   crop window physically excluded the raised driver ("sixteen samples of the wrong region
   is zero samples"). A wrong absent-beat claim silently deletes real beats.
   (forensics + debrief 2026-07-31)
5d. **No dead air inside beats.** Trim heads and tails to the action — more than ~2s of
   nothing-happening in frame is a miss (v03 shipped 6s of empty frame after the mirror
   came off and 6–7s of dead air heading the both-guards display shot). Verify by sampling
   frames through the INTERIOR of every chosen range, not just its boundaries;
   motion-energy scans are hints for finding candidates, never verification of the pick.
   **"Display beat" is not an exemption:** any held beat over ~3s gets 1s sampling to
   confirm the stillness is intentional (subject held on purpose, per rule 6) rather than
   dead — v03 pre-authorised two dead beats with its own labels and read the unchanged
   contact-sheet cells as confirmation. (Dan, v03 notes + debrief 2026-07-31)
6. **Show the product assembled** once put together (bench display beat earns its length —
   Dan held ~13s on the finished-guard display).
7. **Reference wide before ambiguous close-up.** If the next close-up could be anywhere on
   the vehicle, precede it with a quick wide/orienting shot. Dan also punches in (scales)
   4K shots in post when the framing needs help. **When adding an orienting wide, choose
   the portion of the take with purposeful action — not the installer getting their
   bearings** (v03's establishing-wide instinct was right, its section pick was the
   milling-around part; Dan, v03 notes 2026-07-31).
8. **Insert moments (pin holes, alignment features): show, then move.** Once the thing is
   inserted, cut quickly. Lingering is acceptable when unsure.
9. **Tool-ID shots are NOT house style.** Dan's videos carry a dedicated tools segment
   BEFORE the install (motion-graphics tool list + a shot of the tools laid out) — the
   install cut never needs to show a tool off. An installer tool-hold is utility footage:
   park ONE on the muted alternates track as pacing filler for longer VO, don't spend a
   V1 beat on it. (Dan, 2026-07-31 — REPLACES the earlier "tool-ID shots are keepers"
   rule, which was a wrong inference.)
9b. **Presence-verified ≠ composition-verified.** Any shot chosen for a communicative job
   (opener, orienting wide, display) gets a full-res COMPOSITION check: is the subject
   actually framed and readable, or edge-cropped/disembodied? The f3t v01 opener
   "verified" the wrench in hand while the installer was 90% out of frame — the crop
   proved the tool existed, nobody asked what the shot READS. (2026-07-31)

## Structure

10. **Mirrored L/R installs: pick ONE side and stay there.** Evaluate BOTH sides at ingest —
    installers often shoot the FIRST side in more detail, but execute the SECOND side more
    smoothly (familiarity). Go with whichever side you have more end-to-end confidence in.
    Never bounce left↔right through the edit. **The "repeat on the other side" beat is a
    GLAMOUR shot of the other side already installed** — not work footage of the second
    side. (Dan, 2026-07-30) **One-side applies to the BENCH too:** assembling the second
    guard/part at the bench is still second-side content — cut it (fresh-test v02 graded
    down for two second-guard bench beats). Dan's finesse: zero guard-2 bench beats; the
    both-guards display served as the cold open instead.
10b. **Punch-ins are authorized.** Scale/reposition 4K shots whenever framing is ambiguous
    or the action is small in frame — commit to it confidently; Dan can adjust easily and
    everything added is appreciated. Reference-wide first, then the punched close-up.
11. **Cold-open product tease: nice-to-have, not mandatory** — the installer doesn't always
    shoot that material. Keep when the footage gives it.
12. **Presenter pointing/explainer shots without known meaning: cut them.** Dan dropped both
    5745-style pointing inserts. They only earn a slot when VO (or a transcript) gives them
    a job — except concrete demonstrative ones (pointing at the alignment-pin hole) which
    can stand alone. **A pointing shot indicating a specific locating feature — dowel, pin,
    hole, tab — is demonstrative and SHIPS; absence of VO is not grounds to demote it**
    (v03 quoted this rule and still applied the general case to a shot that met the
    exception; debrief 2026-07-31).
13. **End the install body on the completed side, clean shot.** No both-sides victory-lap
    wide required in the body (that's outro/glamour territory).

## VO-first cuts (product spots, graphics-led) — started 2026-07-31, slingshot carplay v01

18. **The VO line is proven on screen.** Whatever the narration names must be visible while
    the line plays — "plug in your iPhone" needs the phone/plug on screen. If no footage
    proves the line, a graphic or animation can stand in (a phone-charging animation counts).
    (Dan's 55s note, 2026-07-31)
19. **Vehicle continuity between cuts.** Stick to as few vehicle switches between adjacent
    cuts as possible — hopping vehicles jars the viewer. Batch same-vehicle shots; change
    vehicles at section boundaries, not mid-thought. (Dan, 2026-07-31)
20. **Overlay graphics: lean in.** Hi-tech overlay elements are encouraged and safe to
    OVER-include in a rough — they're an easy cut if overdone (rule 2's rough-runs-long
    philosophy, applied to graphics). Full-screen Remotion/HyperFrames animation scenes are
    welcome too, not just overlays. Park experimental/bonus graphics on the muted "hidden"
    track — Dan rates these among his favorite elements; keep feeding that track.
20b. **Motion-graphics house style is OPEN — do not mimic prior videos.** Dan historically
    used downloaded templates; the Can-Am CarPlay video was his first custom callout pass
    ever, so its graphic vocabulary is NOT canon to copy. Never imitate an earlier video's
    graphics style unless Dan explicitly says "copy that style." Propose your own; Dan
    curates via feedback and the keepers graduate into this doc and STYLE-SPEC. The ONE
    persistent element that predates all of this: the red/black product footer, spec'd in
    STYLE-SPEC §Graphics. (Dan, 2026-07-31)
21. **Masking + transforms are open season.** Cut UI displays out with a mask and reuse them
    as design elements over action shots; take liberties with color correction, scaling,
    positioning, and keyframed transforms whenever it serves the VO. (Dan: "i'd encourage it")
22. **Footage identity includes vehicle GENERATION.** Right-family/wrong-generation footage
    (a 2018 Slingshot dash in a video for the 2020+ system) is UNUSABLE for a product tied
    to a specific system — verify the generation/UI on screen against the product's target
    before cutting it in. Extends rule 17's identity discipline. (Dan, 2026-07-31)

## Workflow facts

14. Dan strips audio entirely from MOS finesse timelines (his finesse had 0 audio items).
15. Dan duplicates Claude's sequence and finesses the copy — diff is always
    claude-sequence vs "<name> DAN FINESSE", markers on his copy carry the WHY.
16. **V2 alternates sit at the timeline position of the V1 beat they'd replace** (and are
    trimmed so they never extend past V1's end). Parking them at the timeline head is
    wrong — v03 regression, 2026-07-31.
17b. **MOS rough is the deliverable; conforming the cut to VO is Dan's job, permanently.**
    Leave beats long and actions complete (rule 2) so trimming to VO is all he needs —
    never try to pre-time an MOS cut to unwritten narration. (Dan, 2026-07-31)
17c. **120fps footage defaults to 23.976 by interpretation** (conform, not retime — motion
    plays at ~20%, buttery). That's the standing read for glamour material. EXCEPTION:
    real-time demos that happen to be shot at 120fps (e.g. a screen-capture demo of a UI
    boot animation) stay real-time. Decide per clip at ingest and note it in the footage
    log. (Dan, 2026-07-31)
17d. **VO channel QC.** Narration must be centered/dual-mono on the timeline — a stereo
    source can still land left-speaker-only via clip channel mapping (happened 2026-07-31).
    Verify mechanically on the RENDER: ffprobe channel count + per-channel loudness
    (ffmpeg astats); near-equal RMS both sides or it's a miss.
17. **Footage-log labels come only from frames actually viewed.** Never label a beat from a
    motion-energy curve or audio scan alone — v03's "mount coming off" labels were
    curve-inferred guesses; it shipped the bracket-removal moment without knowing it held
    it, while red-flagging the beat as missing. Side/part identity (left vs right) comes
    from on-screen geometry, never from transcript audio alone — transcripts are hints; if
    geometry doesn't settle it, log it as UNKNOWN. (v03 debrief 2026-07-31)
