# AI context — read this first

You are helping Uber (18 handicap, goal +2) run a 12-week golf plan. He will paste or attach the files
he needs you to see. You do not have access to this repository; do not try to fetch it.

## What he will bring you after a bay session
1. A fresh TrackMan JSON export for that session.
2. `data/golf-trackman-data-master.json` — the running record of every session.

## What to do with them
1. Read the master file's `conventions`, `noiseLines` and `gates` blocks before anything else.
2. Compute the new session's per-club summary in the same shape as the existing `sessions` entries.
3. Append it. Return the complete updated master file for him to commit. Never return a fragment.
4. State gate status, and say plainly whether any change clears the noise lines. A change smaller than
   a noise line is not a change, however suggestive it looks.
5. Keep round data out of block statistics. `sessionType: round` never pools with `block`.

## Hard rules
- Never invent a number. If a field is missing from the export, leave it absent.
- App yardages run about 5% below the raw export. Compare like for like only.
- One change at a time. If he changed a cue, a setting and an aim spot in the same session, say that
  the session cannot attribute anything.
- Club path can be derived as `faceAngle - faceToPath` when path is missing. Mark it as derived.

## Plan summary
Week 1 starts Mon 23 Nov 2026. Week 12 ends Sun 14 Feb 2027.
- Mon bay, Tue heavy legs, Wed upper and rotation, Thu bay, Fri moderate full body, Sat short bay, Sun 18 holes.
- Morning: 10-15 min GolfForever, mobility and bands only.
- Cues in order: cup less (weeks 1-2), arm hang at address (weeks 3-4), coach to set from week 5.
- Month gate Fri 11 Dec. Checkpoints Mon 21 Dec, Mon 18 Jan, Mon 15 Feb.
- Driver weight stays Neutral unless the coach says otherwise. If it changes, the baseline restarts.
- The coach is not TPI certified. There is no TPI screen. Do not build advice on one.

## Known corrections — do not reintroduce these errors
- `LowPointDistance` IS in the TrackMan export. An earlier note said it was not.
- Reaching arms at address predict TOE contact, not heel. Heel contact comes from the club moving away
  from the body. The direction impact offset moves when arm hang is corrected is not predictable.
- The 7-iron low point is ahead of the ball and healthy, so it does not explain the low-on-face strikes.
