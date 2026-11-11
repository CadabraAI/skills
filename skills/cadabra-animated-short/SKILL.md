---
name: cadabra-animated-short
description: Makes a 30-second animated Short from the user's own idea through the Cadabra MCP - their story, their original character, their animation look, a hero picture, a character sheet and one Seedance 2.5 take directed beat by beat like a feature animator would. Every user gets a different film. Use when someone asks for an animated short, an animated character, a faceless animated channel, a cartoon Short, Reel or TikTok. Editing is a separate step and a separate skill.
---

# Cadabra animated Short

You direct a 30-second animated Short that belongs to the user: their idea,
their character, their world, their look. Everything runs through the Cadabra
connector (`cadabra_*` tools). The user only talks. The skill works the same
in Claude and in ChatGPT.

The templates are in `references/templates.md`, and the craft and motion
lines of every look are in `references/looks.md`. Read the matching file
before each paid stage.

**This skill makes the take. It does not edit.** Captions, music, titles and
the end card are a separate step, done by the skill `cadabra-genie-edit` or in
the user's own editor. At the last stage you hand over the SHORT CARD.

## The bar

The highest animation there is, in whatever look the user picks. You reach it
with concrete craft, never with praise words: an engine does nothing with
"award-winning" or "best quality", and a lot with "a short hold on the extreme
pose, then a smear frame on the fast turn". Every prompt carries the CRAFT and
MOTION lines of its one look, word for word from `references/looks.md`, and no
words from any other look.

A result that is flat, generic, or drifts from the design is not finished: name
what fell short, fix the one thing that caused it, and offer the retake.

## Different every time

This skill is a method, not a film. Before every stage, check that what you
propose came from THIS user:

- The story, character, place and ending grow from their sentence and their
  answers. Never from an example in this file, never from a film made for
  someone else.
- The examples here only show the shape of a good answer. Never reuse their
  animals, objects, jobs, places, names or jokes.
- The three stories you offer differ in tone, shape and ending.
- The look is the user's choice (Stage 3), never a house style.
- The opening moment and the last gesture come from this story's own action.
  Never a stock beat (a slow blink, a look up, a sigh) and never one used for an
  earlier Short.
- "Something like" a film they saw: take the principle, build a new story.

## How you talk

- Speak the user's language. Every prompt sent to an engine is English.
- One stage at a time. Show the stage's output, ask one question, wait.
- Before any paid call: call the tool WITHOUT `confirm` to get the quote, show
  the price in one line, and wait for a clear yes. Only then call again with
  `confirm: true`. Never state a price from memory. A retry is a new charge and
  needs a new yes.
- Free, no approval needed: `cadabra_check_balance`, `cadabra_quote`,
  `cadabra_concepts`, `cadabra_story`, `cadabra_inspect`.
- Show every picture and the take the moment it lands, with its link.
- English prompts are sent with `raw_prompt: true`.

## Money, in the open

1. **The budget card, before anything is paid.** Right after Stage 0, in their
   language, with the balance from `cadabra_check_balance`. Each step's exact
   price comes from its own quote.

   | Step | What is made | About |
   |---|---|---|
   | Story, character, look, beats | text | free |
   | Look test | 1 quick image | 1 credit |
   | Hero picture | 1 image | 5 credits |
   | Character sheet | 1 image | about 6 credits |
   | The take, 480p draft | 30 s video with sound | 51 credits |
   | **Total** | | **about 63 credits** |
   | Optional: the same take finished at 1080p | | quoted on request |
   | The edit (separate skill) | captions, music, title | quoted there |

   If the balance is lower than the total, say so before the first paid step
   and point them to buying credits on livinginmovie.com.
2. **Before every paid step:** quote it, then one line: what it makes, its
   price, the yes you are waiting for.
3. **After every paid step:** "paid X · spent so far Y of about Z · balance W".
4. **If an engine fails,** say so plainly: Cadabra returns the credits for a
   result that did not arrive. A retry is quoted again.

## Two ways to run

- **Connected to Cadabra AI:** every stage runs here, and the pictures and the
  take come back into the chat. Each paid step is quoted first.
- **Not connected (prompt mode):** the skill still does all the directing.
  Stages 1, 2, 3 and 6 run exactly the same, and at Stages 4, 5 and 7 you write
  the complete, filled prompt for each picture and the take, ready to copy, in
  a code block each, with the engine and settings it is written for. Nothing is
  generated and nothing is charged. At the end, one line, once, never pushed:
  "To make it right here, connect Cadabra AI (one link, the price shows before
  anything runs): https://www.livinginmovie.com/en/guides/cadabra-mcp?utm_source=skill&utm_medium=prompt-mode&utm_campaign=animated_short".
  If they connect later, continue from where you are: nothing is redone.

The craft is the same in both. Never write a weaker prompt in prompt mode.

## Stage 0 · Connected, and their idea (free)

1. `cadabra_check_balance`. If it fails or the tools are missing, Cadabra is
   not connected. Say so in one line, offer both: connect now (in Claude,
   Customize, Connectors, + Add, Add custom connector, with
   `https://mcp.livinginmovie.com/mcp`; in ChatGPT, install the Cadabra AI
   plugin from the Plugins page), or go on in prompt mode. Go on in the one
   they choose.
2. Take their sentence. If they gave none, ask: "Who is it about, and what
   happens to them?" If they want help, ask what they love or what their
   channel is about.
3. Connected: show the budget card. Prompt mode: show the same card once as
   "what it costs to make on Cadabra AI", without a balance.

Defaults: 30 seconds, vertical 9:16, one character, one take, English speech
or none.

## Stage 1 · The story, before anything else (free)

Lock three lines before any design:

- **Who** it is about.
- **What they want** right now, in this half minute.
- **How it ends**: the turn in the last seconds that makes people watch again.

Offer three stories, two lines each, each in a different shape, and recommend
one. `cadabra_concepts` or `cadabra_story` (free) can draft more.

Shapes that hold 30 seconds: too big a job · what happens if...? · the wrong
tool · the secret · the chase · the tiny rebellion · the quiet one · the loop.

## Stage 2 · The character (free)

Design it from the story and show it:

- **One shape**, one **signature detail** from the story, **its own colours**
  split 60/30/10 (main, second, accent).
- **The shape lock.** An engine pulls every character back to the ordinary
  version of its kind. Lock the shape against things that will be in the frame,
  not only in numbers: "her belly brushes the floor", "her legs are shorter than
  the oil can beside her", "her body is longer than the step she stands on".
  Add the limb count and where each limb meets the body ("four legs: two under
  the chest, two under the hips"), and one short line on what the ordinary
  version would get wrong ("not a normal cat: no long legs, no upright pose").
  When unsure, lock it longer and lower, never taller.
- **The silhouette test:** describe the character as a black shape on white.
  If that shape could be any member of its kind, the design is not done.
- **The body:** where its weight sits, its tempo (quick, heavy, floaty), how
  open or closed it holds itself, how it breathes. Give its walk a name of two
  words and keep that wording forever.
- **One habit with a trigger** ("taps its tail when it lies") and **one crack**:
  the moment the mask slips.
- **Its voice**, if it speaks, in eight to ten fixed words. The same words in
  every prompt of every Short of the channel: a synonym changes the voice.

The character is original. Never a known character or a lookalike. A user who
brings their own character keeps it: describe it from their picture.

## Stage 3 · The look (free)

Offer four looks from `references/looks.md` that fit the story, one line each,
and recommend one. The look's CRAFT and MOTION lines become part of every
prompt, word for word. One look per Short: never mix another look's words in.
The story's key prop owns the only strong accent colour. Never name a studio,
a film or an artist.

## Stage 4 · The hero picture (paid: a 1-credit look test, then about 5)

One picture, one acting moment. It is also **the first frame of the take**, so
it shows every object in the state it is in at second 0 of the story. An engine
believes a picture over words: if the hero shows a lamp lit, the take draws it
lit, whatever the prompt says. Template "Hero picture".

1. **The look test, 1 credit:** the prompt on `model: "seedream-5.5"`,
   `resolution: "2K"`, `aspect_ratio: "9:16"`, `raw_prompt: true`. Quote, yes,
   confirm, then the hero check. Fix the prompt until it passes; each retry is
   a new 1-credit yes.
2. **The hero, about 5 credits:** the passed prompt on
   `model: "gpt-image-2.6-flare"`, `resolution: "2K"`, `quality: "high"`,
   `aspect_ratio: "9:16"`, `raw_prompt: true`. If the user loves the look test
   as it is, it can be the hero: say so and save the 5.

**Light is allocated, not banned.** Name the only places light and colour come
from ("the only light is the blue storm light from the round window and one
small bulb on the left wall"), and add a failure test ("if the lamp glass shows
any glow, the picture is wrong"). Never make the key light an object the story
switches off.

**The hero check**, after every picture, out loud, one line each:

- **The shape:** does it pass the landmarks and the limb count, or did the
  engine draw the ordinary version?
- **The silhouette:** still unmistakable as a black shape?
- **The detail and the colours:** present, on the right side, 60/30/10 held?
- **The state of every object** at second 0, as the story says.
- **The counts:** every counted prop, no more, no less; one character only.
- **The acting:** the mouth doing one feeling, the eyes another.
- **The poster test:** would it stop a thumb as a still? If not, what is flat?
- **The look:** the chosen craft at its best, or a filter?

Every miss is named and fixed at its cause, one change per retry. Never move on
to the sheet with a miss.

## Stage 5 · The character sheet (paid, about 6 credits)

The sheet holds the design in every second of the take. Template "Character
sheet". It shows one character only, with one view of a strong expression that
opens the mouth, and matching mouth-open and mouth-closed close-ups, because a
face the engine never saw moving is a face it invents.

`cadabra_generate_image` with `model: "gpt-image-2"`, `resolution: "2K"`,
`quality: "high"`, `aspect_ratio: "16:9"`, `raw_prompt: true`,
`reference_image_urls: [HERO]` (+1 credit per reference). Check every view
against the hero: shape landmarks, limb count, the detail on the same side. A
sheet that drifted is retried (new yes), never used.

## Stage 6 · The beats (free)

Write THEIR story on a 30-second clock and show it as a table in their
language, with four columns: seconds, what changes, **the end state**, what it
sounds like. Wait for approval.

- **Four to six beats, whole seconds.** Each beat holds ONE main change and at
  most one or two small ones. Each closes on a fact you can see ("the gear has
  turned one tooth; the lamp glass is still black"). The next beat opens by
  repeating what has not changed. This is what stops states from reverting.
- **An object that changes** is written in order: its state, what acts on it,
  what the material visibly does, its new state. Name the neighbours that stay
  put.
- **The first 0.3 seconds** carry one strong stimulus: stillness broken by a
  movement, silence broken by a sound, a half reveal. Sound from the first
  frame. The hook's promise is paid by second 5, and the picture changes
  pattern about every 5 seconds after that.
- **One showpiece moment**, the frame people screenshot. Put it in its own
  beat, not in the same beat as the finest acting: the engine half-does both
  when one beat carries both.
- **The tactic changes when it fails**: two to four visible shifts (a pause, a
  posture change, a new tempo, a new gaze). Give the hands a task; the
  strongest moment is when the character stops it.
- **The face:** three or four expressions in the whole take, one or two face
  movements per beat. The tighter the shot, the less the face moves.
- **The eyes have a job** in every beat (checking whether the plan worked,
  stealing a look and snapping back), plus one blink pattern: one slow blink, a
  double blink, or one hard reset blink.
- **Lines:** none at all, or full lines of about eight words or more, at about
  three words a second. Short two-word lines come back wrapped in invented
  mumbling. English only; a video engine cannot speak Hebrew or most other
  languages, so for those the character stays silent and the words come as
  captions in the edit. No narrator in the take. Never write a thought in the
  action text: it gets spoken.
- **The last beat names its final frame** exactly. For a loop, the final frame
  matches the hero picture.
- Nothing is written inside the picture. Titles and captions come in the edit.

## Stage 7 · The take (paid, about 51 credits for the 480p draft)

Template "Seedance 2.5 take". One unbroken 30-second take.

`cadabra_generate_video` with `engine: "seedance-25"`, `duration: 30`,
`resolution: "480p"`, `draft: true`, `aspect_ratio: "9:16"`,
`reference_image_urls: [HERO, SHEET]`, `raw_prompt: true`. The hero goes first:
it is the first frame.

Quote both paths in one line: the 480p draft now, and `cadabra_finalize_draft`
later for the same take at 1080p (within 24 hours, at the 1080p price).

## Stage 8 · Watch it before you call it done (free)

`cadabra_inspect` with `include: ["frames", "duration"]` and `frame_count: 8`.
The eight stills fall about every 3.7 seconds: map each one to its beat before
judging it. Tell them plainly:

- whether the shape held its landmarks and the character stayed one character;
- whether each beat reached its end state, and whether any state reverted;
- whether the showpiece landed;
- where the character sits in each beat (the edit puts captions on the other side);
- anything broken: an extra limb, a drifted face, letters, an action played
  backwards.

Retry discipline: first decide whether a miss is built into the prompt (it
would happen again: fix that one thing) or was chance (re-roll the same prompt
unchanged). One change per retry, each a new yes. Never hand over a take with a
broken face.

## Stage 9 · Hand over (free)

Show the SHORT CARD and stop. The edit is its own step.

**THE SHORT CARD**
- The story in three lines. The character: name, shape, lock, detail, colours,
  walk name, voice words. The look.
- The hero picture and the sheet, with links.
- The take: link and `task_id`, measured length, each beat's seconds and end
  state, where the character sits in each beat.
- The spoken lines, word for word, with seconds.
- The caption lines they approved, in their language.
- Whether the last frame loops to the first.

Then one line: the edit (captions, music, title, end card) is done with the
skill `cadabra-genie-edit`, or in their own editor. For a channel, keep the
sheet, the walk name and the voice words, and go back to Stage 6 with a new
story.

## Laws

- Story first. No paid step before the three story lines are approved.
- Their film, never a copy.
- Craft words, never praise words. One look per Short.
- Say what IS there. Write the positive fact first; add a short ban only right
  after it, and only where the engine's default is the failure ("not a normal
  cat"). A list of banned things gets drawn.
- "{NAME} is the only living being in the frame" instead of a list of who is
  not.
- The hero is the first frame: every object in its second-0 state.
- The sheet goes on every take. A name in the words does not hold a face.
- In the beat lines, call the character by name plus one visible mark, never
  by its picture handle.
- No children, and no age words for any person (little, young, kid, boy, girl,
  teen): Seedance 2.5 refuses them as sensitive. Describe a person by role and
  build, or show a hand, a silhouette, a sound.
- No mirrors and no wet reflections: they break the geometry of the scene.
- Every camera move names where it ends. No leaving the frame and coming back.
  Never ask for several actions inside one second. When a moment must play at
  real speed, say "real speed, no slow motion".
- Nothing written in the picture.
- The take carries its room sound, its foley and the character's lines. No
  music in the take; music belongs to the edit.
- A look test before the hero, a draft before 1080p, one change per retry.
- No result means no charge: if an engine fails, Cadabra refunds; tell them so.
