# Templates

Fill every {SLOT} with concrete, visible detail from THIS user's story,
character and look. Keep every other sentence as written: those sentences are
what hold the shape, the states and the acting. Two users filling these
templates must end with two different films.

{LOOK}, {CRAFT} and {MOTION} are the three lines of the chosen look in
`looks.md`, word for word.

Write what IS in the frame. A list of things that must not appear gets drawn,
so a ban appears only as a short line right after the positive fact it guards,
and only where the engine's own default is the failure.

---

## Hero picture

`cadabra_generate_image` · look test: model `seedream-5.5`, `2K`, `9:16` · hero: model `gpt-image-2.6-flare`, `2K`, quality `high`, `9:16` · `raw_prompt: true`

```
A frame from {LOOK}. {NAME}, {WHAT IT IS AND ITS SITUATION IN ONE LINE}.

THE BODY: {THE ONE SHAPE, described as that shape}. {THE SHAPE LOCK: two or three landmarks against things in this frame, e.g. her belly brushes the stone floor, her legs are shorter than the oil can beside her}. {THE LIMB COUNT and where each limb meets the body}. {THE ONE-LINE "NOT A NORMAL ..." GUARD}. {SURFACE in this look, colours as 60/30/10: main, second, accent}. {THE SIGNATURE DETAIL, exactly, with its side}. {THE EYES: size, colour, lids, catchlights}.

THE MOMENT, second 0 of the story: {ONE ACTING MOMENT: what it is doing with its body and hands}. Its mouth {ONE FEELING}, its eyes {A SECOND FEELING}. {EACH PROP with its count and its state at second 0, as what it is, e.g. one brass oil can lying on its side; the lamp glass is black and cold}.

COMPOSITION: {SHOT SIZE}, camera at {HEIGHT}, {NAME} on the {THIRD}, filling {HOW MUCH} of the frame, facing {DIRECTION}. Behind: {WHAT IS BEHIND, softer}.

LIGHT: the only light in this picture is {SOURCE 1, from where} and {SOURCE 2, from where}, with a thin rim along {ITS EDGES}. {A FAILURE TEST for any object that must stay dark or unlit, e.g. if the lamp glass shows any glow, the picture is wrong}.

STYLE: {LOOK}, 9:16 vertical frame.
CRAFT: {CRAFT}

{NAME} is the only living being in the frame. The picture carries no writing of any kind.
```

Rules: run it first as the look test, then the hero check from Stage 4. The
key light is never an object the story switches off.

---

## Character sheet

`cadabra_generate_image` · model `gpt-image-2` · `2K` · quality `high` · `16:9` · `raw_prompt: true` · `reference_image_urls: [HERO_URL]`

```
A character sheet of ONE character, {NAME}, the character in the attached picture, laid out as one image on a plain, flat, seamless light-grey backdrop that fills the whole frame. Every view shows the same single {NAME}. Keep {NAME} exactly as in the attached picture: {THE SHAPE LOCK}, {THE LIMB COUNT}, the same {COLOURS}, the same {SIGNATURE DETAIL} on the same side, the same eyes, the same {LOOK} rendering.

THE VIEWS, in a clean grid:
1. Full body, front, standing in its normal pose.
2. Full body, exact side profile, the shape lock clearly visible.
3. Full body, from behind.
4. Full body, three-quarter angle, mid-step in its walk, "{WALK NAME}".
5. Face close-up, front, calm, mouth closed.
6. Face close-up, front, the same face with the mouth open as if speaking.
7. Face close-up, three-quarter angle, {A STRONG EXPRESSION FROM THE STORY that opens the mouth and shows the teeth or tongue}.
8. Face close-up, three-quarter angle, {THE SIGNATURE EXPRESSION}.
The paws or hands are open and empty in every view. The head is whole in every view. {THE SIGNATURE DETAIL} appears in every view.

Even soft light on every view, neutral white balance. CRAFT: {CRAFT}
```

Rules: check every view against the hero: landmarks, limb count, the detail
on the same side. One character only.

---

## Seedance 2.5 take

`cadabra_generate_video` · `engine: "seedance-25"` · `duration: 30` · `resolution: "480p"` · `draft: true` · `aspect_ratio: "9:16"` · `raw_prompt: true` · `reference_image_urls: [HERO, SHEET]`

Block order is fixed.

```
REFERENCES
@image1 is the first frame of this take: the set, the light, the props and {NAME} exactly as they are at second 0.
@image2 is {NAME}'s design only: shape, colours, face and {SIGNATURE DETAIL}. Every view on it is the same single {NAME}; its grey background and poses are not part of the scene.
{ANY OBJECT IN @image1 WHOSE STATE CHANGES, said as a plain fact of this film, e.g. the lamp in the first frame is dark, and it stays dark until second 20}.

STYLE: {LOOK}.
CRAFT: {CRAFT}
MOTION: {MOTION}

THE CHARACTER: {NAME}, {ONE VISIBLE MARK}. {THE SHAPE LOCK}. {THE LIMB COUNT}. {THE ONE-LINE GUARD}. Body: weight {WHERE}, tempo {HOW}, {OPEN OR CLOSED}, {BREATH}. Walk: "{WALK NAME}". Habit: {HABIT} when {TRIGGER}.

STAGING: {NAME} starts on the {THIRD}, filling {HOW MUCH} of the frame, in the {FOREGROUND OR MIDGROUND}, facing {DIRECTION}, touching {WHAT}. It travels {SCREEN DIRECTION} and never leaves the frame.

CAMERA: 30 seconds, vertical 9:16, one unbroken take. {SHOT SIZE AND LENS}. {ONE MOVE, and where it ends, e.g. a slow push in that ends on a close-up of her face at second 26}. Real speed throughout, no slow motion.

LIGHT: the only light is {SOURCE 1} and {SOURCE 2}. {WHEN A LIGHT CHANGES, the second and the new state, e.g. from second 20 the lamp's gold beam becomes the key light}.

ACTING TASK for {NAME}:
WANT: {what it wants right now}.
WHY: {what happens if it gets it}.
OBSTACLE: {what stands in the way}.
HANDS: {a physical task for the hands or paws}.

BEATS:
{FIRST SECOND}-{END}s: {the one main change, written as state, cause, what the material does, new state}. Tactic: {TACTIC 1}. Eyes: {THE EYES' JOB}. Face: {ONE OR TWO FACE MOVEMENTS}. Sound: {THE SOUND OF THIS ACTION}. {A LINE: In English, {NAME} says: "{about eight words or more}"} or {silence}. End state: {WHAT WE CAN SEE AT THE END OF THE BEAT}.
{NEXT}-{END}s: Still {WHAT HAS NOT CHANGED}. {the next change...} Tactic: {TACTIC 2, visibly different}. ... End state: {...}.
{...one block per approved beat...}
SHOWPIECE, {SECOND}-{SECOND}s: {THE SCREENSHOT MOMENT in full: what moves, what the light does, what fills the frame}. End state: {...}.
FINAL FRAME at 30s: {EXACTLY WHAT IS ON SCREEN; for a loop, the same as @image1}.
Blinks: {ONE SLOW BLINK / A DOUBLE BLINK / ONE HARD RESET BLINK} at {SECOND}.

AUDIO: {THE ROOM SOUND, one line}, present from the first frame. Foley in order: {ONE SOUND PER ACTION}. {IF IT SPEAKS: {NAME}'s voice: {THE FIXED VOICE WORDS}.} No music.

{NAME} is the only living being in the frame for the whole take. The picture carries no writing of any kind.
```

Rules:
- One main change per beat, one or two small ones at most. Never several
  actions inside one second. Chain actions in one direction, so nothing plays
  backwards to fill time.
- Every beat after the first opens with "Still ..." and closes with "End state".
- The showpiece and the finest acting are in different beats.
- Lines: none, or about eight words or more at about three words a second, each
  with its language. No thoughts in the action text.
- In the beats, the character is its name plus one visible mark, never "@image2".
- No person with an age word; no child at all. No mirrors, no wet reflections.
- Timecodes are whole seconds and never pass 30.
