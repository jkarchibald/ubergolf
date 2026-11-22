# ubergolf — Become the Golfer tracker

A single-page tracker for a 12-week golf plan, 23 Nov 2026 to 14 Feb 2027.
No build step, no dependencies. GitHub Pages serves it as-is.

## Layout

    index.html                             the app
    AI-CONTEXT.md                          paste this into a new AI chat first
    README.md
    plan/12-week-plan.md                   the full plan and the reasoning
    data/golf-trackman-data-master.json    every session, one entry per club
    data/lifts.csv                         lifting log
    raw/2026-11-17.json                    original TrackMan export
    raw/2026-11-18-reconstructed-partial.json
    raw/2026-11-19-reconstructed.json
    raw/EXTRACTION-LOG.md                  which screenshot each reconstructed number came from

## Using it

Open the published page. Four views:

- **Today** — the session for today, as a checklist, with a notes box.
- **Plan** — all 12 weeks, day by day, with checkpoints and the month gate flagged.
- **Data** — every session from the master file, with path colour-coded against the gates.
- **Notes** — saved notes, plus backup and restore.

Ticks and notes are saved in **that browser only**. Use the backup box in Notes before clearing your
browser or moving to another device.

## Adding a session

1. After a bay session, export the JSON from the TrackMan portal.
2. Start a chat. Attach `AI-CONTEXT.md`, `data/golf-trackman-data-master.json`, and the new export.
3. You get back the updated master file.
4. Commit it, plus the raw export as `raw/YYYY-MM-DD.json`.
5. The app picks it up on the next load.

Round data goes in with `"type": "round"` and is never pooled with block statistics.

## Noise lines

A change smaller than these is measurement noise, not improvement:

| Metric | Smallest real change |
|---|---|
| Club path | 1.8 deg |
| Face to path | 4.7 deg |
| Impact offset | 0.55 in / 14 mm |
| Smash factor | 0.05 |
