# SlingMods Video Style Spec

Reverse-engineered 2026-07-30 from the 12 most recent channel videos (uploads 2026-04-28 → 2026-07-29,
all host-less / VO-era). Source data: scene detection + transcripts, `analysis/summary.json` in this repo.

## The two video types

| | Product Spot | Install Video |
|---|---|---|
| Runtime | 2:00 – 2:40 | 5:25 – 10:50 |
| Structure | intro → feature tour → CTA | intro → install chapters → CTA |
| Median shot length | 3.3 – 5.9s | 3.9 – 9.7s (cutty demo moments) |
| Long takes | rare | 40 – 130s locked-off install shots |

## Universal timing skeleton

1. **0:00 – ~0:05 — Splash.** Brand splash (`Slingmods Splash 4k.mp4`), music starts. VO enters at
   **0:03–0:07** in all 12 videos (median 0:05–0:06). This number is law.
2. **Intro — until ~0:45–0:55.** Glamour/product beauty (120fps slowed) + demo B-roll, cut every
   **4–6 seconds**, VO runs the opener formula. The one chaptered install video marks
   Introduction as 0:00–0:55.
3. **Body.**
   - *Spot:* feature-by-feature tour, each feature = 1 VO sentence + 1–2 shots.
   - *Install:* chapter blocks named like the real chapter set observed —
     `Introduction / [Part] removal / New [part] installation / Custom adjustments / Conclusion`.
     Cutting relaxes: long real-time takes with VO explaining, occasional insert close-ups.
4. **Outro — final ~28–30s.** Benefit recap → CTA → logo outro (`slingmods Logo Outro 2.mov`).
   The ~29s final block is remarkably consistent (4 of 5 measurable videos: 28.1–29.4s).

## Script formulas (measured, not invented)

**Opener (6 of 12 verbatim-pattern, rest are close variants):**
> "If you own a [YEAR+] [VEHICLE] and want [BENEFIT], we have the perfect solution.
> Introducing the [VENDOR] [PRODUCT NAME]. Designed specifically for [FITMENT]…"

Variants seen: "If you're looking for…", "If you're planning to run…", and problem-first
("…you know shoulder and back pain can cut your ride short. The problem often isn't you, it's your handlebars.")
Problem-first is used when the product solves a pain, formula-first when it adds a capability.

**CTA closer (near-verbatim in all 12):**
> "[Benefit recap — 'Once installed, you'll have…']
> If you're ready to [BENEFIT], head over to slingmods.com or click the link in the description below
> [to pick/grab one up for yourself]. And don't forget to like and subscribe to stay up to date…"

## Voice & tone

- Second person, benefit-led, zero hype-words ("premium" comes from product names, not adjectives piled on).
- Vendor is always credited by name ("from the team over at Evolution R").
- Fitment years/models stated precisely ("2020 or newer Spyder RT") — this is a trust signal, never rounded.
- Sentences short enough to breathe; VO reads ~140–150 wpm.

## Assembly rules distilled

- Music from frame 0; VO never starts before the splash resolves (~5s).
- Intro visuals never show the install; wrenches appear only after the intro.
- Install VO explains WHILE the action happens (long takes), with close-up inserts on the fastener/connection.
- End card / outro block gets a full ~29s: recap + CTA + logo sting. Don't rush it.
