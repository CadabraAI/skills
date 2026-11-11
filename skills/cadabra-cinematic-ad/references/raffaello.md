# Raffaello: every prompt exactly as it ran

A 30-second ad, all invented: Raffi, a neighbourhood pizza maker, filmed as a legendary Italian chef; the opera stops and his tiny pizzeria is revealed. The anchor object is the domed oven, present in both worlds. The edit is `../assets/raffaello-editplan.json`.

## 1. Character sheet (nano-banana-2.1, 2K, 16:9)

A film character sheet for "Raffi": photographs of the same real man laid out as ONE image on a plain, flat, seamless light-grey backdrop that fills the whole frame.
Photographed like a premium food-and-lifestyle campaign: soft flattering daylight, real skin with fine natural texture and a healthy glow, never plastic, never waxy, never an airbrushed CGI face. Charismatic and magnetic, the man everyone in the neighbourhood wants to talk to, yet clearly a real person.

THE VIEWS, in a clean grid, all the SAME man, identical face, identical wardrobe, identical hair in every frame:
1. Full body, front, standing straight, relaxed confident pose.
2. Full body, exact side profile.
3. Full body, from behind.
4. Head-and-shoulders close-up, front, calm expression, eyes to camera.
5. Head-and-shoulders close-up, three-quarter angle.
6. Head-and-shoulders close-up, three-quarter angle, a proud closed-mouth half-smile with one eyebrow slightly raised.
Hands open and empty in every view. The head is fully visible and uncropped in every view.

Small clean detail panels along one edge: the eyes close, the skin texture close, the stubble and hair close, and a palette strip of five swatches from the wardrobe and skin.
Even soft light on every view, no hard shadows. Neutral white balance, true-to-life colour, no film look and no grain. Any text is minimal, small, clean English lettering.

WHO THIS IS, honour every detail exactly: Raffi, 48, Israeli man, strikingly handsome in a rugged way. Thick dark hair swept back with silver at the temples, a short groomed salt-and-pepper beard, a strong jaw, warm dark-brown eyes with laugh lines, thick dark brows, a small pale scar through his left eyebrow, warm olive skin with real texture. Height 180 cm, broad shoulders, strong forearms. Wardrobe: a crisp white double-breasted chef jacket with black buttons, sleeves rolled to the elbow, a faded red cloth tucked into the waist of a long black apron, dark trousers, black leather work shoes.

An original person invented for this film, not a celebrity. Keep the face exactly the same across every view.

## 2. World sheet 1: the trattoria

A film location reference sheet for "the trattoria": photographs of the same real place laid out as ONE image, six panels in a clean grid, no people in any panel.
The place: a small stone trattoria kitchen at the edge of a cliff village above the sea, at dawn. One anchor object: a domed wood-fired oven of rough white plaster with a blackened arch, burning, centre-back. One light logic: the oven's orange firelight inside the room, and cool blue dawn light through one arched window on the right wall, mist outside over a pale sea. A long scrubbed oak counter along the left wall with a white marble slab for dough, one sack of flour, one tin of olive oil, one bunch of basil in a glass, three copper pans hanging on the wall behind. Terracotta floor, lime-washed walls with fine hairline cracks.
THE PANELS: 1. three-quarter wide from the doorway; 2. the reverse angle from the oven toward the arched window; 3. eye level along the counter; 4. materials close-up: plaster, oak grain, marble, copper; 5. the light: firelight against the dawn window; 6. a flat top-down plan of the room.
The place keeps its own light, true-to-life colour, real textures with weight. No text, no letters, no logos anywhere. Counts: ovens one, arched windows one, copper pans three, people zero.

## 3. World sheet 2: the neighbourhood pizzeria

A film location reference sheet for "the neighbourhood pizzeria": photographs of the same real place laid out as ONE image, six panels in a clean grid, no people in any panel.
The place: a tiny neighbourhood pizzeria on a street corner in an Israeli town, early evening. One anchor object: a domed wood-fired oven faced with small white square tiles, burning, centre-back, the same dome shape and arch as an old Italian trattoria oven. One light logic: warm firelight from the oven mixed with one cool fluorescent tube over the counter, and the blue hour outside the glass storefront on the right. A narrow steel counter on the left with one stack of white pizza boxes and a paper-ticket rail, two red plastic stools against the wall, a blank dark menu board above the counter with nothing written on it. Outside the glass, on the pavement, one red delivery scooter with a square black thermal box, parked under a warm street lamp. A plain storefront sign above the glass, blank.
THE PANELS: 1. three-quarter wide from the street door; 2. the reverse angle from the oven to the storefront and the street; 3. eye level along the counter; 4. materials close-up: white tile, brushed steel, cardboard, glass; 5. the light: oven fire against the blue hour; 6. a flat top-down plan of the shop and the pavement.
The place keeps its own light, true-to-life colour, real textures. No text, no letters, no logos anywhere, the sign and the menu board stay blank. Counts: ovens one, scooters one, stools two, words zero, people zero.

## 4. Face and body references

בצ'אט: שתי בקשות ל-`cadabra_generate_image`, `nano-banana-2.1`, `2K`, עם דף הדמות כתמונת רפרנס. קרדיט אחד לכל אחת. במחשב אפשר פשוט לחתוך מהדף, בחינם.

**פנים (@image1):** From the attached character sheet, one single photograph only: Raffi's head and shoulders, front view, calm expression, eyes to camera, on the same plain light-grey backdrop. Keep his face, hair, beard, the scar through his left eyebrow and the white chef jacket exactly as on the sheet. One person, no other panels, no text.

**גוף (@image2):** From the attached character sheet, one single photograph only: Raffi full body, front view, standing relaxed, on the same plain light-grey backdrop. Keep his face, hair, beard, wardrobe, the red cloth at the apron waist and his build exactly as on the sheet. One person, no other panels, no text.

**עולמות (@image3, @image4):** דפי העולם עצמם.

---

## 5. The take (seedance-25, 30 s, 9:16, 480p draft)

`cadabra_generate_video` · engine `seedance-25` · duration 30 · resolution 480p · draft true · aspect_ratio 9:16 · reference_image_urls בסדר: פנים, גוף, טרטוריה, פיצרייה.

SUBJECT: Raffi (@image1 face, @image2 body: thick dark hair swept back with silver at the temples, short salt-and-pepper beard, a small scar through his left eyebrow, crisp white double-breasted chef jacket with rolled sleeves, long black apron with a faded red cloth at the waist), a magnetic Israeli pizza maker presented like a legendary Italian chef, in a stone trattoria on a cliff above the sea at dawn (@image3), and the reveal that his real kitchen is a tiny neighbourhood pizzeria on an Israeli street (@image4). 30 seconds, vertical 9:16, one unbroken take with no cuts, carried by a drone descent, a gimbal that stays close to his hands and face, and whip-pans as the only transitions.

[0:00-0:04] HOOK: already diving, an FPV drone threads between two lines of white laundry snapping in the sea wind above a cliff village at dawn, skims one terracotta roof and drops toward the single arched doorway glowing orange on the wet stone lane.
[0:04-0:08] THE LEGEND: through the doorway without slowing, Raffi stands with his back to the camera at the oak counter and tosses a disc of pizza dough high above his head; it spins up toward the lens in slow motion, flour spraying off its edge through the oven's backlight, until the spinning disc fills the whole frame.
[0:08-0:13] THE CRAFT: the disc drops away from the lens onto the marble, where his hands stretch it wide until the edge glows translucent against the fire; a whip-pan swings to the oven and the camera flies straight into its mouth, a tongue of flame rolling across the white dome overhead, one basil leaf curling on bright red sauce.
[0:13-0:18] THE HERO: the camera flies back out through the flames to find Raffi sliding the finished pizza out on a long wooden peel; he turns to the lens, his chin lifting a fraction; one slice lifts away and the mozzarella stretches into long glowing strands, steam curling through the firelight.
[0:18-0:22] THE LOOK: medium close-up, Raffi looks straight into the lens with a quiet, knowing half-smile and raises his scarred left eyebrow, mouth closed, one slow blink, holding the moment.
[0:22-0:27] THE REVEAL: a whip-pan tears out through the doorway and lands on a street in an Israeli town at blue hour: the trattoria was a tiny pizzeria all along, white-tiled oven glowing behind the glass, a steel counter with a stack of white pizza boxes, two red stools; Raffi steps out of the door holding one pizza box and hands it to a delivery rider whose face stays hidden behind a dark helmet visor, on a red scooter with a black thermal box under a warm street lamp.
[0:27-0:30] THE HOLD: the rider rides out of frame; Raffi leans on the doorframe, arms crossed, and grins at the camera; the camera stops and holds on him to the last frame.

CAMERA: one unbroken move: an FPV drone dive through the laundry and straight through the doorway, then a gimbal close on Raffi's back, hands and face on a 47-degree lens; the spinning dough disc is a foreground wipe that fills the lens and falls away; an 18-degree macro feel on the dough and inside the oven; a whip-pan with motion blur to the oven, a fly-in through its mouth and back out, and a second whip-pan out through the door, ending on an 84-degree wide of the storefront where it stops and holds. No hard cuts, no shake.

LIGHTING: cool blue dawn and sea mist outside the trattoria; inside, the oven is the key light, hard orange from behind and frame-left, with a cool edge from the arched window on the right, exposure protecting his face; on the street, blue hour sky, warm firelight through the glass, one cool fluorescent tube over the counter and the warm sodium street lamp over the scooter.

AUDIO: no dialogue, no voices, no singing, no music, never a whoosh or any transition sound. Foley only: gulls and soft surf, a soft puff of flour, dough slapping on marble, the oven's low roar, the crackle of the crust, a shop door bell, quiet street ambience, a scooter engine idling and pulling away.

STYLE: a real food commercial shot on a drone and a gimbal: natural light, true-to-life colour, real skin with fine texture, flour, steam, cheese and fabric moving with weight, subtle film grain.

CONSTRAINTS: Raffi keeps the exact face, hair, beard, scar and wardrobe of @image1 and @image2 every second, including through both whip-pans. Raffi never speaks: his mouth stays closed for the whole take. The trattoria follows @image3 and the pizzeria follows @image4, and they share the same domed oven shape. The only other person is the delivery rider in the reveal, face always hidden by the helmet visor. One dough disc in the air, one pizza, the same pizza from the peel to the box; laundry lines: two; arched doorways: one. No text, no letters, no numbers, no logos anywhere in the picture, the shop sign stays blank. Faces never melt or swap during a transition.

REFERENCES: @image1 is Raffi's identity, highest weight, keep his face exactly. @image2 locks body, height and wardrobe (180 cm, broad shoulders). @image3 sets the trattoria's geometry, materials, light and atmosphere, not the framing. @image4 sets the pizzeria's geometry, materials, light and atmosphere, not the framing.

**גמר:** אוהבים את הטיוטה? `cadabra_finalize_draft` מייצר את אותו טייק בדיוק ב-1080p, תוך 24 שעות מהטיוטה.

---

## 6. Voices as recorded

```
narrator: Amit · voice_id uwHajH4FhtzVp6X17pr7 · model eleven_v4 · language he
Raffi: Omer · voice_id k77ZRVqAFg9Hd0ltAuON · model eleven_v4 · language he

each line is its own request:
- Amit: יש שפים שנולדים באיטליה.
- Amit: ויש אחד, שאיטליה נולדה בשבילו.
- Amit: הם קוראים לו... רפאלו.
- Omer: בפיצה, כמו בחיים, הכל עניין של בצק.
- Amit: רפי. פיצה רפאלו, רחוב הדקל שבע.
- Amit: עכשיו גם במשלוחים.
```

לפני ההקלטה: `cadabra_proofread_script` ו-`cadabra_pronunciation` (רפאלו = ra-fa-EL-lo), חינם. מספרים כותבים במילים בשביל הקול (שבע), ובכתוביות בספרות (7).

## 7. Music as sent to Suno V6

```
Suno V6 · custom_mode: true · instrumental: true · duration: 30 · title: Raffaello Overture

style:
Italian opera overture for a film trailer, solo mandolin and pizzicato strings opening alone, full string section and timpani joining, brass on the peak, warm and grand, instrumental, no vocals. 0 to 4 seconds a lone mandolin over soft pizzicato; 4 to 18 seconds strings and timpani build in a steady crescendo; 18 to 22 seconds the full orchestra peaks on one held chord; at 22 seconds a hard stop into silence; 23 to 30 seconds a light solo mandolin returns, playful, and ends on a single plucked note.
```

Suno בנה את השיא, אבל לא עצר בעצמו בשנייה 22. את העצירה עושים בעריכה עם שני רמזי מוזיקה (`musicCues`).

## 8. Sound effects
1. A ball of pizza dough slapped and pressed onto a cold marble slab, close and dry.
2. A wood-fired oven burning steadily, a soft low roar with small crackles, close.
3. The crisp crack of a blistered pizza crust being torn, close.
4. One short horn beep of a small delivery scooter on a quiet street.

---
