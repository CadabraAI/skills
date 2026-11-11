# The edit prompt

Written in English, shown to the user in full before anything is rendered,
then sent as the `brief` of `cadabra_assemble` (route A) or turned into an
EditPlan for `cadabra_render_plan` (routes A and D). Every on-screen word is in
the user's language, exactly as approved. Fill every {SLOT} with what you read
in Stage 2; leave out a section that has nothing in it.

---

## Any film from their footage

```
EDIT PROMPT: "{FILM TITLE}", a {LENGTH}-second {SHAPE} {what it is: ad / reel / product film / the story of the business} for {BUSINESS}, edited in Cadabra's Genie.

Do exactly what is written below, and nothing else. Total runtime {LENGTH} seconds. Keep the clips in the order given. Never put any text over a face. All on-screen words are {LANGUAGE}, exactly as quoted. Quote first and show me the price and the measured length; render only after my yes.

FORMAT
{1080x1920 vertical 9:16 / 1920x1080 / 1080x1080}. {No colour grade, the footage keeps its own look / the look they chose}. Tempo: {calm / dynamic / one shot / chaotic, or their words}. Master loudness -14 LUFS.

PICTURE
{one line per clip, in their order: clip N · in-out seconds · what it shows · why it is here (the hook, the proof, the product, the people, the payoff)}
{the opening: what grabs the eye in the first second}
{the ending: what the last shot lands on before the end card}

MOTION GRAPHICS, in {brand colour} with white labels
{one line per element: start-end s · what it is (title, callout, counter, label that follows a subject) · where in the frame, away from the face · its exact words}

VOICE
{their narration file with its script, or the speech inside the clips, or none}

MUSIC
{track · where it starts and stops · under the voice by how much · how it ends (on the film's last frame)}

SOUND
{the clips' own sound: keep, lower to N%, or mute · any sound on a cut or a word, never a whoosh}

CAPTIONS
{style, position (bottom, clear of faces), size, which words are emphasised, numbers as digits}

TITLE
{start-end s · the words · where · how it enters}

END CARD
The last {2.5-3} seconds: headline "{BUSINESS NAME}", under it "{the call to action: street, offer, phone, link}", {background and text colour}.

CHECK BEFORE AND AFTER
Runtime {LENGTH} s before paying. After the render, frames: no word on a face, every number readable, the end card whole, no black frames at the end.
```

---

## The cinematic ad (route D, from the creation skill's files)

Same sections and order as `raffaello-edit-prompt.md`, filled with THEIR
business, files and seconds:

```
EDIT PROMPT: "{BUSINESS}", a 30-second vertical ad for {what the business is}, edited in Cadabra's Genie.

Build ONE edit plan for cadabra_render_plan (read cadabra_editor_manual sections "overview", "lexicon", "shape" and "motion" first) that does exactly what is written below, and nothing else. Total runtime 30.0 seconds: the take trimmed to 26.9 s, plus a 0.6 s freeze, plus a 2.5 s end card. Quote first and show me the price and the measured length; render only after my yes. All on-screen words are Hebrew, exactly as quoted. Never put any text over a face.

FORMAT
1080x1920, vertical 9:16, no letterbox. No colour grade. Light film grain (0.05), soft vignette (0.15), no transitions. Font Heebo. Master loudness -14 LUFS.

PICTURE
The take from 0 to 26.9 s, normal speed, filling the frame, its own sound at 45%. At {reveal second} s, on the first sharp frame of {the anchor} after the reveal whip-pan, freeze for 0.6 s.

MOTION GRAPHICS, in {brand colour} with white labels
{one line per element: start-end s · what it is · where in the frame (away from the face) · its exact Hebrew words}

PARTICLES AND NUMBERS
{the trade's dust in THE LEGEND, its heat or sparkle in THE CRAFT, one counter with a real number of the craft and its Hebrew label, three light leaks}

VOICE (six separate recordings, each placed on its second, full volume)
{second · voice name · the exact Hebrew line}

MUSIC
{track name} in two cues, both ducking under the voice by 35%: cue 1 from 0 to the freeze at 55%; cue 2, the same file, from the end of the freeze plus 0.1 s to the end at 45%, fade in 0.3 s, fade out 0.4 s.

SOUND EFFECTS
{second · sound · length and volume, the four trade sounds trimmed to their moments, built-in accents at 18-30%, never a whoosh}

CAPTIONS
White pop captions, one sentence at a time, near the bottom (height 76%), 62% size: {five lines with their in and out seconds, numbers as digits, the legend-name line in the brand colour, 1.2x}. The offer line is spoken over the end card and not captioned.

TITLE
{start-end s} · the business name at the top, large, brand colour, letters popping in one by one: "{BUSINESS NAME}".

END CARD
The last 2.5 seconds: dark card, brand-colour text. Headline "{BUSINESS NAME}", under it "{street · offer}".

CHECK BEFORE AND AFTER
Runtime 30.0 s before paying; after the render, frames: the freeze on the anchor, no word on a face, the name readable, the end card whole.
```
