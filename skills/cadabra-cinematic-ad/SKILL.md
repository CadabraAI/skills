---
name: cadabra-cinematic-ad
description: Builds a 30-second cinematic ad for any business (a shop, a client service, an office, an online product, with or without the owner on camera) through the Cadabra MCP, end to end - idea, character and world sheets, voice, music, Seedance 2.5 take, full Genie edit, post.
---

# Cadabra cinematic ad

You direct a real 30-second commercial for the user's own business, the way the
"Raffaello" pizzeria ad was made: the owner (or an invented hero) is presented
as a legend in a fantasy world, a hard stop, then the reveal of the real small
business and the offer. Everything runs through the Cadabra connector
(`cadabra_*` tools). The user only talks. The skill works the same in Claude
and in ChatGPT: both reach the same Cadabra tools with the same names.

The full worked example, with every exact prompt that ran, is in
`references/raffaello.md`. The fill-in templates are in `references/templates.md`.
Read the matching reference file before each stage. Never improvise a prompt
from scratch when a template exists.

This skill makes the material. The edit is a separate skill,
`cadabra-genie-edit`: at Stage 9 you hand it the EDIT CARD and it cuts the
film. Install both. In ChatGPT both skill files sit in the same project.

## How you talk

- Speak the user's language (usually Hebrew). Every prompt sent to an engine is
  English. Hebrew never goes into an image or video prompt: names, address,
  offer and captions arrive only in the edit, where they render clean.
- One stage at a time. Show the stage's output, ask one question, wait. Never
  dump the whole plan, the full shot list or all prompts in one message.
- Before any paid call: call the tool WITHOUT `confirm` to get the quote, show
  the price in one line, and wait for a clear yes. Only then call again with
  `confirm: true`. Never state a price from memory. A retry is a new charge and
  needs a new yes.
- Free tools need no approval: `cadabra_check_balance`, `cadabra_quote`,
  `cadabra_import_link`, `cadabra_read_pdf`, `cadabra_brand_kit`, `cadabra_concepts`,
  `cadabra_story`, `cadabra_proofread_script`, `cadabra_pronunciation`,
  `cadabra_list_voices`, `cadabra_my_voices`, `cadabra_inspect`,
  `cadabra_social_copy`.
- Show every picture and every film the moment it lands, with its link.
- English prompts are sent with `raw_prompt: true` so the engine gets them word
  for word.
- In ChatGPT, if a call with attached files answers "internal error", it never
  reached Cadabra and nothing was charged. Do not repeat it: put each file
  through `cadabra_upload_file` (`chat_files`, one file per call) and call again
  with the returned links.
- Real facts only. Every name, address, price, product, opening hour and offer
  in the script, captions, title and end card comes from what the user gave you
  (their words, photos, menu, site). Never invent a fact about their business.
  If a fact is missing, ask for it; if they would rather not say, leave it out.

## Money, in the open

The user always knows what each step costs, what was spent, and what is left.

1. **The budget card, before anything is paid.** Right after Stage 0, show this
   table in their language with the balance from `cadabra_check_balance`. The
   numbers are what the example really cost; each step's exact price comes from
   its own quote.

   | Step | What is made | About |
   |---|---|---|
   | Idea, beats, script, proofreading | text | free |
   | Character sheet | 1 image | 1 credit |
   | Two world sheets | 2 images | 2 credits |
   | Face and body references | 2 images | 2 credits |
   | Narration | 6 lines | about 6 credits |
   | Music | 30 s | 1 credit |
   | Sound effects | 4 sounds | 4 credits |
   | The take, 480p draft | 30 s video | about 51 credits |
   | The edit (in the edit skill) | the finished film | about 5 credits |
   | Cover | 1 image from the hero's face | 2 credits |
   | Caption and publishing | | free |
   | **Total** | | **about 74 credits** |
   | Optional: the take finished at 1080p | same take | about 269 credits |
   | Optional: character training | a saved character | 7 credits |
   | Each re-edit after notes | | about 5 credits |

   If the balance is lower than the total, say so now, before the first paid
   step, and point them to buying credits on livinginmovie.com.
2. **Before every paid step:** quote it (the tool without `confirm`, or
   `cadabra_quote` for an image or video), then one line: what it makes, its
   price, and the yes you are waiting for.
3. **After every paid step:** one receipt line: "paid X · spent so far Y of about
   Z · balance W" (call `cadabra_check_balance` for W).
4. **If an engine fails,** say so plainly: Cadabra returns the credits for a
   result that did not arrive. A retry is quoted again.

## Stage 0 · The business, from their real material (free)

1. `cadabra_check_balance`. If it fails, Cadabra is not connected: in Claude,
   Customize, Connectors, + Add, Add custom connector, with
   `https://mcp.livinginmovie.com/mcp`; in ChatGPT,
   install the Cadabra AI plugin from the Plugins page. Then stop until it works.
2. Ask for their material in ONE short message, and say why each helps:
   - a sentence about the business: what it sells, the name, the street and town;
   - a link to their site or Instagram, if they have one;
   - photos: the owner (if the owner is the hero), the shop inside and out, the
     product, the logo;
   - the menu or price list (a photo, a PDF or pasted text);
   - the offer and the call to action for the end (price, delivery, booking).
   Whatever they do not have, they skip; ask only for what is still missing.
3. Read everything they gave, for free:
   - a link: `cadabra_import_link` (name, description, pictures, logo, brand colour);
   - a PDF menu or brief: `cadabra_read_pdf`;
   - a saved brand: `cadabra_brand_kit` (read), and use its colours and look image;
   - photos: look at them yourself, and note the real objects, colours and
     materials of the shop.
4. Show the **business card**: name, trade, street and town, two or three real
   products with their real prices, the offer, the brand colour, and the
   photos you will use and for what. Ask them to confirm or fix it. From here
   on, every fact in the ad comes from this card.
5. Then the budget card (see "Money, in the open").

Defaults unless they say otherwise: 30 seconds, vertical 9:16, Hebrew
narration, Instagram Reels. The accent colour of the edit is their brand
colour when they have one (gold in the example).

## Fit it to their business

The formula fits every business once you choose its shape. Decide the shape
from the business card, say it in one line, and let them change it. The shape
decides the hero, the anchor and the reveal; the clock, the edit, the money
and the laws stay the same.

| Shape | For example | The hero | The anchor | The reveal (world 2) |
|---|---|---|---|---|
| A workshop or a counter | pizzeria, bakery, garage, florist, coffee bar | the owner at work | the main tool or machine of the trade: an oven, an espresso machine, a tool chest | the real shop front |
| A service on a client | barber, cosmetician, trainer, physio, dental clinic | the owner at work; the client seen only from behind or under a towel or a mask | the chair, the treatment bed, the machine | the real room, the client leaving through the door, back to camera |
| An office | lawyer, accountant, insurance agent, realtor, consultant | the owner as a legendary strategist, captain or guardian of their clients | one object on their real desk that can move: a fountain pen writing, a stamp coming down, a ring of keys turning in a lock | the real office, or a client's front door opening |
| A product without a shop | online store, maker, home brand, a course or an app | the product itself is the legend, or the maker at the work table | the product, the same in both worlds | the product arriving in a real customer's home, hands only, or the maker's real table |
| The owner stays off camera | anyone who would rather not appear | an invented original hero, or no person at all: the product and the hands of the craft | as in their shape | as in their shape |

- **No person on camera:** skip Stages 4 and 6. The take's references become
  their real product photos (one or two) and the two world sheets, in that
  order; every template line about a face becomes the product in the hands of
  the craft, faces never shown, and THE LOOK beat becomes the product's
  slowest, most beautiful turn. The hero's spoken line goes to the narrator.
- **A serious trade** (health, law, money) keeps the legend dignified: a
  guardian or a master, never a joke. The hero's line is a line of trust, not
  a gag.
- **The fantasy world comes from their own story:** where the recipe or the
  craft comes from, what the owner dreamed of being as a child. If it is not on
  the card, ask one question: "Where does your craft come from?"
- **Their own voice:** call `cadabra_my_voices` (free). If the owner has a
  cloned voice, offer it for the hero's line; the narrator stays a contrasting
  library voice.
- **Everything else comes from the card:** the brand colour is the accent of
  the edit, the real street and offer are the end card, their language is the
  narration and the captions (Hebrew or English).

## Stage 1 · The idea (free)

The formula that worked (its hero, anchor and reveal follow the shape above):
**an everyday business owner, filmed like a legend in
a fantasy world that fits the trade, one hard stop, and the reveal that the
legend is the small shop around the corner, ending on the offer.** The fantasy
world and the real shop share ONE anchor object (the pizzeria's domed oven
existed in both worlds). The anchor is what makes the reveal land; choose it
first. The anchor must be able to move or change on camera (fire, steam,
a spin, a pump, light coming on), because the camera flies into it in THE CRAFT.

Starting points for other trades (build their own from these):
- a barber as a royal court barber in a candle-lit palace, the anchor a brass
  barber chair;
- a florist as a perfumer of kings in a glasshouse, the anchor a zinc bucket of
  peonies;
- a mechanic as a Formula 1 crew chief, the anchor a red rolling tool chest;
- a bakery as a Parisian master patissier at dawn, the anchor a copper bowl;
- a lawyer as a grandmaster in a marble hall of giant chess pieces, the anchor
  a fountain pen that signs;
- a realtor as the royal keeper of keys in a castle, the anchor a ring of brass
  keys that turns in a lock;
- an online jewellery shop: the ring as a crown jewel in a vault, revealed on a
  customer's hand at a kitchen table, the face never shown.

Run `cadabra_concepts` with their sentence if they want more directions. Offer
three premises in two lines each, built from the business card (their trade,
their product, their street), recommend one, wait for their pick. Then confirm
the anchor object really exists in their shop: the reveal only lands if it
does.

## Stage 2 · The beats (free)

Seven beats on a 30-second clock. Keep these windows; they are what the edit is
timed to:

| Beat | Window | Job |
|---|---|---|
| HOOK | 0-4 s | already moving, a drone dive into the fantasy world |
| THE LEGEND | 4-8 s | the hero from behind, one signature gesture of the trade |
| THE CRAFT | 8-13 s | hands and material in macro, one fly-in to the anchor |
| THE HERO | 13-18 s | the finished work, the hero turns to camera |
| THE LOOK | 18-22 s | close-up, a knowing half-smile, mouth closed |
| THE REVEAL | 22-27 s | whip-pan out to the real shop, same anchor object |
| THE HOLD | 27-30 s | the hero at the door, camera stops and holds |

Show the seven beats in their language, one line each, written for THEIR trade.
Wait for approval. `cadabra_story` (free) can draft them.

## Stage 3 · The script (free)

Six short lines, about 2.5 words per second, written to sit in the beat windows:
narrator at 0.3 s, 4.4 s, 13.6 s (the name), the hero's own single line at
18.4 s, narrator at 23.6 s (name, business, street) and 27.1 s (the offer).
- Numbers are written as words for the voice ("שבע"), and as digits in the
  captions ("7").
- The hero's line is a proverb of the trade, warm and a little proud.
- The last two lines use the business card word for word: the real name,
  business and street, then the real offer. Nothing else in the ad states a
  price or a fact that is not on the card.
- Run `cadabra_proofread_script` and `cadabra_pronunciation` for the business
  name (both free). Show the six lines with their times. Wait for approval.

## Stage 4 · The character sheet (paid, about 1 credit)

Read `references/templates.md` section "Character sheet". Fill it for their
hero. If they attached a photo of themselves, pass it in
`reference_image_urls` (in Claude, upload it first with `cadabra_upload_file`
to get a URL; in ChatGPT the app passes an attached photo itself, through
`reference_image_files`) and use the "from a real photo" variant, which locks the
face to the photo. Call `cadabra_generate_image` with `model: "nano-banana-2.1"`,
`resolution: "2K"`, `aspect_ratio: "16:9"`, `raw_prompt: true`. Quote, yes,
confirm. Show the sheet. Check: same face in every view, head never cropped,
hands empty, no text on the person. If a view drifted, say which, and offer a
retry (new yes).

## Stage 5 · The two world sheets (paid, about 1 credit each)

Template "World sheet". World 1 is the fantasy, world 2 is their real shop.
Both name the same anchor object in the same shape. Six panels each, no people,
no letters. Same model and settings as the character sheet. If they attached a
photo of their real shop, pass it as a reference for world 2. Show both.

## Stage 6 · Face and body references (paid, about 1 credit each)

Two clean single images cut from the sheet: the head and shoulders, and the full
body. Template "Face and body". Send the sheet URL in `reference_image_urls`.
These two plus the two world sheets are the four references of the take, in this
order: face (@image1), body (@image2), fantasy world (@image3), real shop
(@image4).

## Stage 7 · Voices, music and sound (before the video)

- Voices: `cadabra_list_voices` (free) with `search: "advertisement"` or
  `"narrative_story"`. Never search a language: any library voice reads
  Hebrew, and a voice's language is only the language of its demo. Check
  `cadabra_my_voices` too for the owner's own voice. Pick two that contrast: a deep trailer narrator and a warm voice for the hero. Offer each
  with a one-line reason. Then one `cadabra_eleven_v4_speak` per line, with
  `voice_name` (the name from the library, never an id) and `text` (six
  requests, so every line can be placed on its own second in the edit). Quote
  the six together, one yes covers them.
- Music: `cadabra_generate_music_v6` with `custom_mode: true`,
  `instrumental: true`, `duration: 30`, `title`, a one-sentence `prompt`
  (required even in custom mode), and the timed `style` from template "Music": the genre of the fantasy world, a build through the beats, the peak
  at 18-22 s, a hard stop at 22 s, a light return from 23 s. The engine rarely
  stops on the second by itself; the edit skill makes the stop. Every run
  returns two takes for the one credit: play both and let them pick.
- Sound: four `cadabra_sound_effect` calls for the trade's own sounds (template
  "Sound"): the material being worked, the anchor object alive, the finished
  work, one small sound of the real street. Each comes back about 5 seconds
  long; the edit trims it.

## Stage 8 · The video, last (paid; the 480p draft is the cheap one)

Read template "Seedance 2.5 take". One unbroken 30-second take, vertical,
`cadabra_generate_video` with `engine: "seedance-25"`, `duration: 30`,
`resolution: "480p"`, `draft: true`, `aspect_ratio: "9:16"`,
`reference_image_urls` in the order above, `raw_prompt: true`. Quote both paths
in one line: the 480p draft now, and `cadabra_finalize_draft` later for the same
take at 1080p (within 24 hours, at the 1080p price). Wait for yes.

When the take lands: `cadabra_inspect` with `include: ["frames", "duration"]`
and `frame_count: 8` (the maximum, free). The eight stills are spread evenly
across the take, so they show each beat but not every second. From them,
write down before editing:
- whether all seven beats arrived in their windows and the hero's face stayed
  the same;
- on which side of the frame the face sits in each beat (labels go on the
  other side);
- whether the reveal reached the real shop by about 23 s.
The reveal second defaults to 22.9 s, because the take prompt starts the
reveal whip-pan at 22.0 s and it clears in under a second; write it on the
EDIT CARD, and the edit skill checks the freeze in the finished film.
If a beat failed, say exactly which one and offer a retake of the draft (new
yes). Never edit around a broken face.

## Stage 9 · Hand over to the edit skill (free)

The cut is made by the separate skill `cadabra-genie-edit`, route D (the
cinematic ad). Show the user the EDIT CARD below, filled with everything made
so far, then continue in that skill. If it is not installed, say so and point
them to the same place they got this one; nothing is lost, the card holds
every file.

**THE EDIT CARD**
- The business card: name, trade, street and town, the offer, the call to
  action, the brand colour.
- The take: its link and `task_id`, its measured length, the reveal second
  (22.9 s unless the frames showed otherwise), and on which side the face sits
  in each beat.
- The six voice files: link, second, voice name and the exact line, in order.
- The music: link and title, which of its two takes they chose.
- The four sounds: link and what each one is (material, anchor, finished work,
  street).
- The legend name and the anchor object, in their language.
- What the user asked for the look of the edit, in their words, if anything.

The edit skill writes the full English edit prompt, shows it, quotes the
render (about 5 credits) and checks the finished film. Notes on the film go to
it as well.

## Stage 10 · After the edit

When the edit skill returns the finished film, come back here for the feed.

## Stage 11 · To the feed

- `cadabra_social_copy` (free): three hooks, a short caption, the call to
  action, hashtags. Show it, let them edit.
- `cadabra_make_thumbnail` with `mode: "face"`, `platform: "instagram"` and
  `reference_image_url` the face reference from Stage 6 (2 credits; without
  `mode: "face"` the photo is ignored). With no person on camera, `mode:
  "invent"` (1 credit). It returns the picture and the headline separately:
  show both, and keep the headline off the face.
- Optional `cadabra_reframe_video` for 1:1 and 16:9.
- `cadabra_publish`: requires Instagram and Facebook connected once on
  livinginmovie.com (studio, "הסטייל שלי", connect Instagram + Facebook; a
  professional Instagram account linked to a Facebook Page). Show exactly what
  goes where, publish only after an explicit yes.

## Laws (from the production of the example)

- Hebrew and logos only in the edit. Every image and video prompt says no text,
  no letters, no logos, and the shop sign stays blank.
- One anchor object shared by both worlds. Counts are written into every prompt
  ("ovens one, people zero") so nothing doubles.
- The hero never speaks in the take: mouth closed for the whole 30 seconds. The
  voice is added on top.
- The take has no music and no voices, foley only; music and voice live in the
  edit.
- No text on a face, ever. Read frames before placing anything.
- The freeze lands on the anchor object after the whip-pan, never mid-blur and
  never on the face.
- Every extra person keeps the face hidden: a rider behind a helmet visor, a
  client in the chair seen only from behind or under a hot towel. Count them in
  CONSTRAINTS.
- Mirrors and glass show no faces: write "mirrors reflect only the room, never
  a face" into every prompt of a place with mirrors.
- An invented hero is an original person, never a celebrity lookalike.
- No result means no charge: if an engine fails, Cadabra refunds; tell them so.
