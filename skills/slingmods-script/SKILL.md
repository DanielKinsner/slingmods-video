---
name: slingmods-script
description: Write a SlingMods VO script from a product page (and optional vendor install instructions). Use when a video needs a script, when Dan drops a slingmods.com product URL, or before any ElevenLabs VO generation. Output goes to 00_docs\ for Dan's approval.
---

# SlingMods Script Writer

Scripts are 95% derived from the slingmods.com product description. Fetch the product page, then
transform catalog copy → spoken copy. Target ~140–150 wpm when timing sections.

## Opener formula (pick by product type)
- **Capability product** (adds something): "If you own a [YEAR+] [VEHICLE] and want [BENEFIT], we have the
  perfect solution. Introducing the [VENDOR] [PRODUCT]. Designed specifically for [FITMENT]…"
- **Pain-solving product**: open with the pain — "…you know [PAIN] can [CONSEQUENCE]. The problem isn't you,
  it's your [PART]. That's why we're proud to bring you the [PRODUCT]…"
- Alternate first line when ownership framing is awkward: "If you're looking for…" / "If you're planning to…"

## Body
- Spot: one sentence per feature, ordered by what the footage can show. Benefit before mechanism.
- Install: narrate the action as it happens ("With the two factory bolts removed, the new bracket drops
  right into place"). Sections mirror chapters: removal → installation → adjustments.
- Credit the vendor by name once ("from the team over at [VENDOR]").
- Fitment stated precisely, copied from the product page ("2020 or newer Spyder RT"). Never round.

## CTA closer (near-verbatim house formula)
"[Once installed, benefit recap sentence.] If you're ready to [BENEFIT], head over to slingmods.com or
click the link in the description below to grab one for yourself. And don't forget to like and subscribe
to stay up to date on the latest [VEHICLE] products."

## Catalog → spoken transforms
- Kill spec-sheet lists; convert to "which means…" benefits. Keep numbers that sell (capacity, minutes-to-install).
- Sentences under ~20 words. Read it aloud mentally; if a sentence needs two breaths, split it.
- No hype adjectives that aren't in the product name. The voice is a knowledgeable friend, not a commercial.

## Output format → `00_docs\script-v1.md`
Sections labeled `## INTRO` / `## INSTALL` (or `## FEATURES`) / `## OUTRO` with an estimated read time per
section. Dan approves (or edits) before any VO is generated — no exceptions. VO renders per-section to
`02_audio\voiceover\{intro,install,outro}-v1.mp3` via ElevenLabs (API key + voice ID from local .env).
