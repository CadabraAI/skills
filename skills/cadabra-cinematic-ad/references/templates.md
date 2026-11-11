# Templates

Each template is the Raffaello prompt with its business-specific parts turned
into {SLOTS}. Fill every slot with concrete, visible detail for THEIR business.
Keep every other sentence as written: those sentences are what kept the face,
the counts and the light stable. The filled Raffaello version of each template
is in `raffaello.md` for comparison.

---

## Character sheet

`cadabra_generate_image` · model `nano-banana-2.1` · `2K` · `16:9` · `raw_prompt: true`

```
A film character sheet for "{HERO_NAME}": photographs of the same real {man/woman} laid out as ONE image on a plain, flat, seamless light-grey backdrop that fills the whole frame.
Photographed like a premium {TRADE}-campaign: soft flattering daylight, real skin with fine natural texture and a healthy glow, never plastic, never waxy, never an airbrushed CGI face. Charismatic and magnetic, the {person} everyone in the neighbourhood wants to talk to, yet clearly a real person.

THE VIEWS, in a clean grid, all the SAME {person}, identical face, identical wardrobe, identical hair in every frame:
1. Full body, front, standing straight, relaxed confident pose.
2. Full body, exact side profile.
3. Full body, from behind.
4. Head-and-shoulders close-up, front, calm expression, eyes to camera.
5. Head-and-shoulders close-up, three-quarter angle.
6. Head-and-shoulders close-up, three-quarter angle, {THE SIGNATURE EXPRESSION, e.g. a proud closed-mouth half-smile with one eyebrow slightly raised}.
Hands open and empty in every view. The head is fully visible and uncropped in every view.

Small clean detail panels along one edge: the eyes close, the skin texture close, {ONE DETAIL OF THE LOOK, e.g. the stubble and hair close}, and a palette strip of five swatches from the wardrobe and skin.
Even soft light on every view, no hard shadows. Neutral white balance, true-to-life colour, no film look and no grain. Any text is minimal, small, clean English lettering.

WHO THIS IS, honour every detail exactly: {HERO_NAME}, {AGE}, {NATIONALITY} {man/woman}, {ONE LINE OF PRESENCE}. {HAIR}. {FACE: eyes, brows, ONE distinctive mark such as a small scar or a beauty spot}. {SKIN}. Height {CM} cm, {BUILD}. Wardrobe: {THE TRADE UNIFORM, every piece with colour and material, plus ONE signature accent object worn on the body}.

An original person invented for this film, not a celebrity. Keep the face exactly the same across every view.
```

**From a real photo** (the owner as the hero): replace the "WHO THIS IS" paragraph
and the last line with:

```
WHO THIS IS: the person in the attached photograph. Keep their face, features, skin, hair and build exactly as in the photo, every view; do not beautify, slim, age or change them. Wardrobe for this film: {THE TRADE UNIFORM}.
```

Rules: one distinctive mark (a scar, a spot, a streak of grey) is what lets the
video keep the identity; write it again in the video SUBJECT. Hands empty, so no
tool fuses into a hand.

---

## World sheet

Same settings. Write two: world 1 = the fantasy, world 2 = their real shop.

```
A film location reference sheet for "{PLACE_NAME}": photographs of the same real place laid out as ONE image, six panels in a clean grid, no people in any panel.
The place: {WHAT AND WHERE, time of day}. One anchor object: {THE ANCHOR, material, shape, state, position in the room}. One light logic: {THE ONE WARM SOURCE inside} and {THE ONE COOL SOURCE, from where}. {THE FURNITURE AND PROPS, each with a count: one sack, three pans, two stools}. {FLOOR AND WALLS}.
THE PANELS: 1. three-quarter wide from the doorway; 2. the reverse angle from the {anchor} toward the {window/door}; 3. eye level along the {main surface}; 4. materials close-up: {FOUR MATERIALS}; 5. the light: {warm source} against the {cool source}; 6. a flat top-down plan of the {room / shop and the pavement}.
The place keeps its own light, true-to-life colour, real textures with weight. No text, no letters, no logos anywhere{, the sign and the menu board stay blank}. Counts: {anchor} one, {each repeated prop with its count}, people zero.
```

Rules: world 2 describes the anchor as "{the same shape} as {world 1's anchor}".
Every sign, menu and screen is written as blank. The counts line closes every
sheet.

---

## Face and body

Two calls, model `nano-banana-2.1`, `2K`, `raw_prompt: true`, `reference_image_urls: [CHARACTER_SHEET_URL]`; the face at `aspect_ratio: "1:1"`, the body at `"9:16"`.

```
From the attached character sheet, one single photograph only: {HERO_NAME}'s head and shoulders, front view, calm expression, eyes to camera, on the same plain light-grey backdrop. Keep {his/her} face, hair, {the distinctive mark} and {the top of the uniform} exactly as on the sheet. One person, no other panels, no text.
```
```
From the attached character sheet, one single photograph only: {HERO_NAME} full body, front view, standing relaxed, on the same plain light-grey backdrop. Keep {his/her} face, hair, wardrobe, {the signature accent} and {his/her} build exactly as on the sheet. One person, no other panels, no text.
```

---

## Voices

Six requests to `cadabra_eleven_v4_speak` (`voice_name` = the name from `cadabra_list_voices`, `text` = the line).

The legend name: the real first name as it would sound in the fantasy world
(Raffi to Raffaello in Italy, Shlomi to Salomon in a French palace, Dana to
Danielle in Paris, Moshe to Moises in Seville). Offer two, let them pick.
Pattern of the six lines (write them fresh for the trade, in Hebrew):

| At | Voice | Pattern | Raffaello |
|---|---|---|---|
| 0.3 s | narrator | "Some X are born in {fantasy place}." | יש שפים שנולדים באיטליה. |
| 4.4 s | narrator | "And there is one {fantasy place} was born for." | ויש אחד, שאיטליה נולדה בשבילו. |
| 13.6 s | narrator | "They call him... {legend name}." | הם קוראים לו... רפאלו. |
| 18.4 s | hero | a proverb of the trade | בפיצה, כמו בחיים, הכל עניין של בצק. |
| 23.6 s | narrator | "{Real name}. {Business}, {street + number in words}." | רפי. פיצה רפאלו, רחוב הדקל שבע. |
| 27.1 s | narrator | the offer in five words | עכשיו גם במשלוחים. |

---

## Music

`cadabra_generate_music_v6` · `custom_mode: true` · `instrumental: true` · `duration: 30` · `title: "{LEGEND} Overture"` · `prompt: "An instrumental trailer overture for a 30-second ad, with a hard stop at 22 seconds."` (required) · `style:` the text below

```
{GENRE OF THE FANTASY WORLD} for a film trailer, {SOLO INSTRUMENT} opening alone, {ENSEMBLE} joining, {PEAK INSTRUMENT} on the peak, warm and grand, instrumental, no vocals. 0 to 4 seconds a lone {solo instrument} over {soft texture}; 4 to 18 seconds {ensemble} build in a steady crescendo; 18 to 22 seconds the full {ensemble} peaks on one held chord; at 22 seconds a hard stop into silence; 23 to 30 seconds a light solo {solo instrument} returns, playful, and ends on a single plucked note.
```

Genre ideas: Italian opera overture (pizzeria), French accordion waltz (bakery),
royal baroque harpsichord (barber), Formula 1 synth score (garage), Japanese
koto and taiko (sushi), flamenco guitar and palmas (tapas).

---

## Sound

Four `cadabra_sound_effect` calls, one sentence each, close and dry:

```
1. {THE MATERIAL BEING WORKED, e.g. A ball of pizza dough slapped and pressed onto a cold marble slab}, close and dry.
2. {THE ANCHOR ALIVE, e.g. A wood-fired oven burning steadily, a soft low roar with small crackles}, close.
3. {THE FINISHED WORK, e.g. The crisp crack of a blistered pizza crust being torn}, close.
4. {ONE SMALL SOUND OF THE REAL STREET, e.g. One short horn beep of a small delivery scooter on a quiet street}.
```

---

## Seedance 2.5 take

`cadabra_generate_video` · `engine: "seedance-25"` · `duration: 30` · `resolution: "480p"` · `draft: true` · `aspect_ratio: "9:16"` · `raw_prompt: true` · `reference_image_urls: [FACE, BODY, WORLD1, WORLD2]`

Block order is fixed: SUBJECT, the seven timed beats, CAMERA, LIGHTING, AUDIO, STYLE, CONSTRAINTS, REFERENCES.

```
SUBJECT: {HERO_NAME} (@image1 face, @image2 body: {hair}, {beard/makeup}, {the distinctive mark}, {the uniform with colours}, {the signature accent}), a magnetic {nationality} {trade person} presented like a legendary {fantasy title}, in {world 1 in one line} (@image3), and the reveal that {his/her} real {workplace} is {world 2 in one line} (@image4). 30 seconds, vertical 9:16, one unbroken take with no cuts, carried by a drone descent, a gimbal that stays close to {his/her} hands and face, and whip-pans as the only transitions.

[0:00-0:04] HOOK: already diving, an FPV drone threads {through something moving in the fantasy place}, skims {one landmark} and drops toward {the single doorway} glowing {warm colour}.
[0:04-0:08] THE LEGEND: through the doorway without slowing, {HERO} stands with {his/her} back to the camera at {the main surface} and {THE SIGNATURE GESTURE, one big readable action}; {an object of the craft} {rises toward the lens / fills the frame}, {particles of the trade} through the backlight.
[0:08-0:13] THE CRAFT: {the object} drops away onto {the surface}, where {his/her} hands {work the material in macro}; a whip-pan swings to {the anchor} and the camera flies straight into it, {the anchor alive in close-up}, {one small vivid detail}.
[0:13-0:18] THE HERO: the camera flies back out to find {HERO} {presenting the finished work}; {he/she} turns to the lens, {his/her} chin lifting a fraction; {the most appetising / satisfying detail of the finished work, in motion}.
[0:18-0:22] THE LOOK: medium close-up, {HERO} looks straight into the lens with a quiet, knowing half-smile {and the signature expression}, mouth closed, one slow blink, holding the moment.
[0:22-0:27] THE REVEAL: a whip-pan tears out through the doorway and lands on {world 2 at its time of day}: the {fantasy place} was {the real shop} all along, {the same anchor} glowing {inside}, {two props of the real shop}; {HERO} steps out of the door {handing over the product} to {a customer or rider whose face stays hidden}.
[0:27-0:30] THE HOLD: {the extra person leaves frame}; {HERO} leans on the doorframe, arms crossed, and grins at the camera; the camera stops and holds on {him/her} to the last frame.

CAMERA: one unbroken move: an FPV drone dive {through ...} and straight through the doorway, then a gimbal close on {HERO}'s back, hands and face on a 47-degree lens; {the object of the craft} is a foreground wipe that fills the lens and falls away; an 18-degree macro feel on {the material} and inside {the anchor}; a whip-pan with motion blur to {the anchor}, a fly-in and back out, and a second whip-pan out through the door, ending on an 84-degree wide of the storefront where it stops and holds. No hard cuts, no shake.

LIGHTING: {world 1 outside light}; inside, {the anchor or main warm source} is the key light, hard {colour} from behind and frame-left, with a cool edge from {the window} on the right, exposure protecting {his/her} face; on the street, {world 2 sky}, warm light through the glass, {one cool practical} and {one warm street practical}.

AUDIO: no dialogue, no voices, no singing, no music, never a whoosh or any transition sound. Foley only: {six foley sounds in story order}.

STYLE: a real {trade} commercial shot on a drone and a gimbal: natural light, true-to-life colour, real skin with fine texture, {three materials} moving with weight, subtle film grain.

CONSTRAINTS: {HERO} keeps the exact face, hair, {mark} and wardrobe of @image1 and @image2 every second, including through both whip-pans. {HERO} never speaks: {his/her} mouth stays closed for the whole take. The {world 1} follows @image3 and the {world 2} follows @image4, and they share the same {anchor} shape. The only other person is {the extra person} in the reveal, face always hidden {how}. {Counts of every object that must stay single: one X in the air, one finished work from start to hand-over, doorways one}. No text, no letters, no numbers, no logos anywhere in the picture, the shop sign stays blank. Faces never melt or swap during a transition.

REFERENCES: @image1 is {HERO}'s identity, highest weight, keep {his/her} face exactly. @image2 locks body, height and wardrobe ({height and build}). @image3 sets the {world 1}'s geometry, materials, light and atmosphere, not the framing. @image4 sets the {world 2}'s geometry, materials, light and atmosphere, not the framing.
```

**A service trade** (barber, cosmetician, trainer, physio): the craft is done
on a client. The client is seen only from behind, or with the face under a hot
towel or a mask, and is counted in CONSTRAINTS ("one client, face never
shown"). In the reveal, the hand-over becomes the client leaving through the
door, back to camera.

Rules: one signature gesture per beat, big and readable. The finished work is
the same object from the craft to the hand-over. Nothing in the picture is
written: every word arrives in the edit.

---

## Edit prompt

Lives in the edit skill: `cadabra-genie-edit`, file `references/edit-prompt.md`,
section "The cinematic ad".

---

## Post

`cadabra_social_copy`: `title` the film's title, `brand_name` the business
name, `about` one sentence of the premise and the offer, `platform:
"instagram"`, `language: "he"` (it takes no film link).

`cadabra_make_thumbnail`: `title` a three-word hook, `platform: "instagram"`,
`mode: "face"`, `reference_image_url` the face reference from Stage 6 (2
credits). No person on camera: `mode: "invent"` and no reference (1 credit).
