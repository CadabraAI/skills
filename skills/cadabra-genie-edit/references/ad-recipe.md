# The cinematic ad recipe (route D)

The edit of the cinematic ad is ONE EditPlan rendered by `cadabra_render_plan`,
made from the files the `cadabra-cinematic-ad` skill hands over. Read
`cadabra_editor_manual` sections "overview", "lexicon", "shape" and "motion"
first; the manual is the authority on field names.
`assets/raffaello-editplan.json` is the exact plan that rendered the example at
30.0 s (checked again on 2026-10-20: the engine accepts every field, 30.0 s, 5
credits): copy its structure and change the content. All times below are on
the ad's 30-second clock:

| Beat | Window |
|---|---|
| HOOK | 0-4 s |
| THE LEGEND | 4-8 s |
| THE CRAFT | 8-13 s |
| THE HERO | 13-18 s |
| THE LOOK | 18-22 s |
| THE REVEAL | 22-27 s |
| THE HOLD | 27-30 s (a spare tail; the end card takes over from 27.5 s) |

## Picture

- `width: 1080`, `height: 1920`, `masterLufs: -14`, `font: "heebo"`,
  `letterbox: "none"`, `grade: "none"` (the take already has its look),
  `grain: 0.05`, `vignette: 0.15`, `transition: "none"`.
- One clip: the take URL, `trimStartSec: 0`, `trimEndSec: 26.9`, `volume: 0.45`
  (the foley stays under the voice), `fit: "cover"`, `motion: "none"`,
  `freeze: {atSec: <reveal second>, durationSec: 0.6}`.
- The freeze defaults to 22.9 s: the reveal whip-pan starts at 22.0 s and clears
  in under a second. `cadabra_inspect` returns at most 8 evenly spaced frames, so
  it cannot find the exact second; check the freeze in the finished film and
  move it 0.2 to 0.4 s if it caught blur or a face.
- Plan times are output times: everything after the freeze plays 0.6 s later
  than in the raw take. The second music cue starts at the end of the freeze
  plus 0.1 s (23.6 in the example).
- Runtime = 26.9 + 0.6 freeze + 2.5 end card = 30.0.

## Motion graphics (`hud`), the order that worked

| When | kind | What | Example |
|---|---|---|---|
| 0.0-3.8 | grid | a gold frame over the upper 60% while the drone dives | area x 0.08, y 0.08, w 0.84, h 0.6 |
| 0.2-1.8 | scan | a scan line down the same area | |
| 0.4-3.7 | type | the fantasy place and a time, typed, small, top | "איטליה · 06:12" at y 0.11 |
| 4.2-5.8 | callout, brackets | names the hero from behind, label beside him | "השף" / "40 שנה מול האש" |
| 8.8-10.5 | callout, dot | names the material at the hands | "בצק" / "72 שעות התפחה" |
| 10.7-12.5 | ring | on the anchor during the fly-in | orange, glow 0.6 |
| 13.4-15.0 | brackets with `track` | follows the hero as he turns | track points from the frames |
| 13.6-17.5 | type, echo 2 | the legend name, very large, accent colour | "*רפאלו*" textSize 0.088 |
| 14.3-17.5 | type | the legend's title under it | "השף האגדי" |
| 22.9-23.6 | type | one word over the freeze, top, white | "רגע." |
| 22.95-23.6 | callout, dot | on the anchor during the freeze | "אותו תנור" |
| 25.7-27.5 | callout, ring, `track` | follows the delivery out of frame | "משלוחים" |

Positions: x and y are 0-1 of the frame. Put every label on the side AWAY from
the face in that beat, using the frames you read. Never on a face.

## Particles, numbers, light

- `particles`: the trade's dust during THE LEGEND (flour `dust`, drift, 4.0-8.4)
  and its heat during THE CRAFT (`embers`, up, from the bottom, 10.3-13.5).
  Florist: petals. Barber: talc. Garage: sparks.
- `graphics`: one `counter` with a real number of the craft during the fly-in
  (0 to 485°, "חום התנור", 10.4 s, 2.5 s, top). Other trades: a barber's blade
  0 to 0.5 mm ("גובה הדירוג"), a bakery 0 to 48 hours ("שעות התפחה"), a florist
  0 to 120 stems ("גבעולים בזר"), a garage 0 to 9,000 rpm, a coffee bar 0 to 93°
  ("חום המים").
- `lightLeaks`: three, warm hue 28-36: a `sweep` when the name lands (13.4),
  a `bloom` on THE LOOK (18.2), a `corner` on the hold (27.3).

## Sound

- The six voice files go into `sfx` as `src` with `atSec` at their script times
  (0.3, 4.4, 13.6, 18.4, 23.6, 27.15), `volume: 1`.
- Built-in accents, quiet (0.18-0.3): `tick` with the typed stamp, `swish` on
  the gesture, `click` on each callout, `riser` into the name, `subdrop` on the name,
  `glitch` on the freeze, `chime` on the offer. Never a whoosh (the example
  plan still carries one quiet `whooshLong` at 3.9 s; leave it out).
- The four trade sounds as `src`, each trimmed with `trimStartSec` and
  `durationSec` to the moment it belongs to (material 1.2 s, anchor 3.3 s with
  `fadeOutSec`, finished work 1.0 s, street 0.8 s on the freeze).
- `musicCues`, the hard stop: cue 1 from 0 to the freeze second, volume 0.55;
  cue 2 the SAME file from the end of the freeze to the end, volume 0.45,
  fade in 0.3. Both `duck: true`, `duckAmount: 0.35` so the voice sits on top.
  A cue always plays from the start of its file, so cue 2 restarts the quiet
  opening: that is the playful return.

## Words

- `captionStyle: "pop"`, `captionColor: "#FFFFFF"`, `captionPosition: "bottom"`,
  `captionY: 0.76`, `captionScale: 0.62`.
- `captions`: the first five lines with `startMs`/`endMs` matching the voice
  files, numbers as digits ("רחוב הדקל 7"); the legend-name line gets the accent
  `color` and `scale: 1.2`. The hero's own line is captioned too. The sixth line
  (the offer) is not captioned: it is spoken over the end card, which shows it.
- `titles`: the business name on the reveal, top, `anim: "letterPop"`, size `l`,
  weight 900, accent colour (23.6 s, 3.9 s).
- `endCard`: `headline` the business name, `cta` street, offer, delivery,
  `durationSec: 2.5`, dark `bgColor`, accent `textColor`.

## Before paying

Call `cadabra_render_plan` with `target_seconds: 30` and no `confirm`. It returns
the measured runtime and the price, and refuses a plan more than 0.5 s off.
After the render, read frames of the finished film: the freeze on the anchor,
no word on a face, the end card whole.
