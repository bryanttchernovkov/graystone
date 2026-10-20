# Graystone — cast and signature looks

Authoring doc (the engine never reads it). Every named character is unambiguously an adult.
Every woman — named or in a crowd — is between twenty-one and fifty and attractive; see the
bible. Never write "elderly", "grandmother" or ages over fifty into a prompt. **Styling sets
the age more than the number does:** white or gray hair, a perm, pearls, a cardigan with a
glasses chain or "retired" on a woman over forty renders her at seventy.

## Character LoRAs (hard rule)

Every named woman has **one character LoRA**, chosen by the author, recorded in her entry
below. **Every image she appears in** — her location's establishing shot, every result that
shows her, her card — lists that LoRA in `art.loras`, and its subject carries her **verbatim
appearance block**. The LoRA carries her face and body; the block keeps hair, build, skin and
signature props consistent with it and tells the model which woman in the frame is her. Never
write "the same woman as before", and never use a name alone. Trigger words are added by the
LoRA Manager node; don't repeat them in the subject.

Only one character LoRA per image: two named LoRA women in one frame blend into each other.
When a scene needs a second woman, she is an unnamed extra described in full, without a LoRA.

## Kink LoRAs (hard rule: only these)

The author's library holds many more; most aren't POV and pull the camera into third person.
In Graystone, use **only** these, at weight 1, and only when the image shows that thing:

| LoRA | When |
|---|---|
| `SA86RN444WSD83T4QX4PYS3P80:1` | detailed handcuffs (German handcuffs; trigger added by the loader). Name them **"clejuso handcuffs"** in the subject: the brand keyword cues the LoRA and keeps them apart from generic cuffs or bracelets. Keep the pose simple ("chrome clejuso handcuffs dangling from her grip"); open, swung cuffs render as a tangle. |
| `HandgagPOV_Krea2_v1:1` | her gloved or bare hand over the viewer's mouth |
| `chastity_000005800:1` | a chastity cage in frame |
| `"Krea2_BDSM Latex-Leather Megapack_V2E09:1"` | optional, for heavier BDSM gear |
| `"Krea 2 - Strapon Dildo:1"` | strap-on, POV |

Not for this universe: the facesitting LoRA (not POV) and the other metal-cuffs LoRA.
Facesitting is shot from the POV recipe alone.

## The camera is the player

The player is always a man; the camera is his eyes.

- **Results with him in them are first-person point-of-view shots.** The prompt opens with
  "First-person point-of-view photograph" and says where the camera is ("from kneeling height
  on the flagstone floor", "from the cot at sitting eye height") — never who is holding it.
- **At most his bare hands and forearms are in frame**, always with the hero's POV block.
  Never his face, his body or his name.
- **Establishing shots (location art) never contain him.** Eye-level photographs from a
  visitor's position; whoever lives there may look into the lens.
- The woman in the scene looks at, speaks to, reaches toward or acts on **the camera**.

### Framing rules (inherited from Precinct 69's renders; revise as Graystone's renders teach us)

The model is trained on a lot of POV pornography. Left to itself it adds the viewer's erect
penis to any first-person shot with a lap, a kneel or bare thighs in it, and builds a whole
stranger around any garment or body part of the viewer's that the prompt names.

1. **His genitals are never in frame.** When an act involves them, crop at his waist and show
   her: her face, her gloved hand at his belt, her other hand on his chest.
2. **He is not in the picture.** By default nothing of his body is in frame, and the bottom
   edge is described as the place (the flagstones between her boots, the desk edge, the cot
   rail). Never mention his knees, lap, legs, jeans, belt or crotch. His hands appear only
   when they do the act at the center of the frame (holding her boot, presenting his wrists).
3. **Show the act when a kink LoRA supports it** (cuffs, chains, chastity, facesitting,
   strap-on, rope…), named precisely: where each hand, foot and mouth is. When no LoRA
   supports it and the model can't see it from his eyes (impact on his back, oral on him),
   shoot the moment before: she faces the lens with the implement, or opens her breeches.
4. **Never write "looking back over his shoulder."** The model answers with a third-person shot.
5. **Never pair "the viewer's hands" with "her bare thighs"** outside a scene about exactly that.
6. **The camera sentence never names the viewer.** No "man", "him" or "his" anywhere in the
   prompt except the POV block's "a man's bare hands". Give the camera's height and direction.
7. **No viewer garments at all.** A sleeve, a cuff of a jacket, an orange jumpsuit: each grows
   a whole man. Cuffs and chains on his wrists sit at the bottom center, on bare wrists.
8. **Every person in a prompt is named as a woman (or a man).** "Deputy", "guard", "officer"
   alone come out male. Write "a woman deputy", "two women deputies".
9. **His arms come from the bottom edge toward the center**, the way your own arms extend from
   your eyes. Never lay his arm sideways along a bench or rail at the frame's side.

### Shot types (vary them)

- **Gaze** — medium shot at arm's length, eye contact, the moment before or the act at the
  bottom of the frame.
- **Detail** — one part of her or one prop fills the frame, no face: a boot an inch from the
  lens, a gloved hand closing a cuff. Say what fills the frame and that nothing else does.
- **Towering** — the camera on the floor tilted steeply up; she stands over it, whole.
- **Intimate** — her face and shoulders inches from the lens, eyes in focus, the room a blur.

**Uniform in partial shots:** describe every visible uniform piece in full and nothing above
the frame. A boot gets the full thigh-high boot; a leg gets the breeches and the boot; when her
upper body is in frame, use the full uniform sentence.

**A standing woman near the camera never fits whole.** Closer than about three paces, 16:9
can't hold her boots-to-head — and in thigh-high boots she is taller still. Make her lean,
crouch or sit into the frame, or crop her deliberately along a diagonal: the contact point in
one lower corner, her face in the opposite upper corner.

**One plane per widescreen frame.** Anything closer than arm's length is a close-up of one
part of her and cannot also show her face and the room.

### The POV recipe

1. **Camera geometry.** "First-person point-of-view widescreen photograph from [standing eye
   height / kneeling height / seated eye height / flat on the floor] in [place], the camera
   [level / tilted down / tilted up]."
2. **Where she is in the 16:9 frame and how far away.**
3. **Eye contact and one emotion, with the face that shows it**, taken from the prose. Put it here,
   before her appearance block, as its own sentence: "She looks directly into the camera, making
   eye contact with the viewer, with [emotion]: [eyes], [brows], [mouth]." Then "She is a …".
4. **The gesture that makes the act legible**, props in her hands near her face or chest.
5. Her appearance block and the uniform sentence.
6. **What of the viewer is in frame** — usually nothing, or the POV block at the bottom center.
7. Background, one lighting sentence, palette, finish.

## Prompt lessons (from the Graystone renders, retro-80s:1)

One image takes about seven minutes; test one image per change, never a batch.

- **Azure is "vivid azure blue".** The tie is "a vivid, saturated azure blue necktie"; piping,
  epaulets, patch, stripe and chevrons are "vivid azure blue". Never "sky blue" or "light"
  (renders a dull powder blue). Muted looks (canon, no LoRA) turn the tie navy or black; the
  retro-80s LoRA is what makes it pop.
- **Stone is named as masonry.** "Limestone crypt" alone renders raw cave rock under retro-80s.
  Every subject in the church says "smooth dressed limestone ashlar blocks laid in straight
  courses with thin mortar joints" and "a whitewashed pointed vault".
- **The Undercroft is underground.** The model adds tall daylight windows to any arched
  corridor; write "windowless, underground, lit only by caged bulbs". The one exception is the
  small grated window at street level in the guard post.
- **Through the bars.** To put her outside a cell, write "photographed through the bars": the
  bars in the extreme foreground, her face in the gap between two of them. If the cell's props
  (cot, wall ring) are in the near foreground, the model puts her inside the cell with them.
- **Cuff words put cuffs on her.** Any "handcuff" or "cuffs" in a subject with her in it
  (even "a handcuff case on her belt") renders as a cuff or a steel bangle on her own wrist, or
  cuffs in her hand instead of the prop you asked for. Her appearance block carries no cuffs.
  Mention cuffs **only when they're the centerpiece** (TERMS, PROMISE, the Prison Chains card),
  with the detailed-handcuffs LoRA. In general, props in her block land on her body.
- **Viewer leaks.** Shots from the cot or the floor with her legs spread above or across the lens
  (boot on the cot rail with her leg raised, a woman lowering herself onto the lens) make the
  model add the viewer's penis, or draw intercourse. So:
  - **Facesitting** is shot from behind her, **clothed, the moment before**: her uniformed ass
    in the breeches lowering toward the lens, boots either side, her face over her shoulder.
  - **Boot worship** at the cot is a **detail shot**, from the toe to just above the knee, with
    no hip or crotch in frame.
- **Heels:** say "low, flat stacked-leather riding heels", or talk of a "heel" turns the riding
  boot into a stiletto.
- **One of her per frame:** in wide shots a doorway or background behind her can grow a second
  copy of her; write "one woman, alone" and say what the space behind her holds.
- **Boots:** "stiff, structured, mirror-polished … with rigid straight shafts fitted tight to the
  leg" stops the slouch. A shot cropped above the knee won't show them; when they matter, frame
  her to the knee or go to a detail shot.
- **Eye contact goes before her appearance.** Written after the 150-word appearance and
  uniform block, "looks straight into the lens" lost to the pose: she looked past the camera
  or down. State it as step 3 with "making eye contact with the viewer", and spell out the
  emotion as eyes, brows and mouth. A gesture that has her glance elsewhere ("she has just
  glanced down at her sleeve") wins over the gaze; leave the glance out.
- **No expression in her appearance block.** "A level, unimpressed stare" in the block flattened
  every face; the scene's eye-contact sentence carries the expression.
- **Every hand gets a job near her face.** "Her other arm reaches out of the frame" grows a
  third arm. Give each of her hands a visible task (cage in one, key in the other) and keep
  both raised close to her face or chest.
- **The chastity LoRA fills an empty cage.** When she holds the cage, write it as "empty,
  unlocked … its curved bars open and hollow", or it renders with anatomy inside.
- **A jacket "hanging open" is worn half.** Say both arms are in its sleeves and both
  shoulders are covered, and put the patch and chevrons on the jacket's sleeves.
- **The outdoor jacket and hat fight each other** (Anderson's first arrest render, Ashby's
  church-steps render): the forest green spreads into the hat (a dark olive fedora instead of a
  tan campaign hat), the open jacket is worn on one arm, and its chest star doubles the shirt
  badge. Being tried on Anderson: no hat, the jacket **zipped to mid-chest** with the only star
  on it, each hand named as coming "out of the green jacket sleeve". "Pocket flaps piped in
  azure" renders solid blue flaps: write "tan flap pockets edged with thin vivid azure blue
  piping".
- **The character LoRA holds her face** across every look tested; the appearance block keeps
  hair, build and kit consistent around it.

## The heroes

**POV block** (per hero, verbatim when his hands are in frame).

**Eli Novak** (first hero, *proposal*) — new in town: the county's contract IT man, moved into
55 Graystone Heights a week before the department notices him. Generic and slightly nerdy: a
white man of 32, lean and a little narrow-shouldered, pale skin, short dark blond hair slightly
messy on top, a few days of light stubble, round thin wire-rimmed glasses; a faded red and gray
plaid flannel over a charcoal T-shirt, worn work jeans, scuffed brown work boots, a black canvas
laptop bag.
POV block: *a pale man's bare hands and forearms with short unpolished nails, entering from
the bottom edge of the frame.*

## Graystone County Sheriff's Department

### Uniform (canonical, verbatim in every police-art subject)

**Indoors:**

She wears the Graystone County Sheriff's uniform: a crisp, pressed tan long-sleeved uniform shirt of heavy cotton twill with a pointed collar, a full button-front placket, two buttoned flap chest pockets piped in vivid azure blue, shoulder epaulets edged in vivid azure blue, an embroidered vivid azure blue and gold patch on each upper sleeve and a polished gold six-point star badge pinned over the left pocket; a vivid, saturated azure blue necktie with a small gold tie bar; tan riding breeches with an vivid azure blue stripe down the outer seam; a black leather duty belt with a polished brass buckle; and stiff, structured, mirror-polished black leather thigh-high riding boots with rigid straight shafts and low, flat stacked-leather riding heels, fitted tight to the leg, pulled up over the breeches to mid-thigh; her head is bare.

**Outdoors** (a different sentence: the bomber covers the shirt, so only its collar and tie show):

She wears the Graystone County Sheriff's patrol uniform: a dark forest-green bomber jacket of smooth nylon twill with ribbed knit cuffs, collar band and waistband, zipped up to the middle of her chest, worn with both arms in its sleeves and both shoulders covered, a single polished gold six-point star badge pinned on its left chest and an embroidered vivid azure blue and gold patch on each upper sleeve[, rank]; above the zipper, the pointed collar of a crisp, pressed tan uniform shirt and the knot of a vivid, saturated azure blue necktie with a small gold tie bar; a black leather duty belt with a polished brass buckle at her waist below the jacket's hem; tan riding breeches with a vivid azure blue stripe down the outer seam; and stiff, structured, mirror-polished black leather thigh-high riding boots with rigid straight shafts and low, flat stacked-leather riding heels, fitted tight to the leg, pulled up over the breeches to mid-thigh. On her head, worn level over her eyes, sits a stiff campaign hat of the kind state troopers and drill instructors wear, in light khaki tan felt the same color as her shirt, with a wide flat brim, a pinched four-dent crown and a vivid azure blue hatband.

Outdoors the rank goes on the bomber sleeves, in place of "[, rank]": sergeant — ", with three
vivid azure blue chevrons beneath the patch on each sleeve". Drop the breeches and boots when
the frame doesn't reach them. Name each hand "out of the green bomber sleeve" when it acts. The
hat is a separate sentence, in shirt-tan, never next to the green; a deputy may go bareheaded
as her personal look (Anderson).

**Rank** goes after the uniform sentence: sergeant — three vivid azure blue chevrons on each upper
sleeve beneath the patch. Deputy — no chevrons: leave the rank sentence out, and outdoors drop
"above three vivid azure blue chevrons" from the jacket sentence (the patch alone stays).
(Sheriff and other ranks: to be set with their characters.)

### Patrol car (canonical, verbatim in every subject with a cruiser)

Lead with "a Graystone County Sheriff's patrol car" (or "N identical Graystone County Sheriff's
patrol cars …, each"), then:

a present-day Ford Police Interceptor Utility SUV painted two-tone, with a white roof, hood and front doors over a tan body, a broad vivid azure blue stripe running the full length of each flank below the windows, a gold six-point star decal on each front door, a low black roof light bar with red and blue lenses, a black steel push bumper bolted across the front grille and black steel wheels

A parked, unattended cruiser adds "its windows are tinted dark and its light bar is unlit".
"Bolted across the front grille" keeps the push bumper on the car: without it, a car seen
side-on grows a loose black railing in the street (Anderson's arrest, second render).
Every `patrol` location shows one somewhere in frame.

### The Undercroft

**Sergeant Monique "Ash" Ashby** (*name is a proposal*) — keeper of the Undercroft.
LoRA: `KreaEbonyBabe1` (trigger `EllieKEB`, added by the loader).

Appearance block: *a Black American woman in her early thirties, tall and athletic with a full, heavy bust, broad straight shoulders and a soldier's posture, smooth dark brown skin, long black dreadlocks gathered at the nape and falling to the middle of her back, straight dark brows, black leather duty gloves and a ring of heavy iron keys on a steel chain at her hip.*

Character: ex-Army military police, eight years, two of them running a detention facility.
Controlling, clipped, borderline mean, never sadistic. Her whole method is *permission*: a man
in her block doesn't stand, sit, speak, drink or piss without asking, and she decides how he
asks. Cuffs and chains are how she says no without saying it. She loves the uniform — hers is
the sharpest in the department — and she inspects it on others as hard as on herself.

Off the clock, at her window table in Café Linde: the indoor uniform with her sergeant
chevrons, no jacket, no hat, gloves still on, a cappuccino. Her arrest is **hands-on**, where
Anderson's is mouth: an arm bar, a man's cheek on the table, a knee in his back, cuffs on the
floor, and a walk across the square with his arm held up behind him.

### Patrol: the Heights

**Deputy Tiffany Anderson** — patrols Graystone Heights from her cruiser.
LoRA: `DGirlsModel14:1`. Rank: deputy (no chevrons).

Patrol look (her outdoor uniform, instead of the canonical outdoor one): **a green bomber
jacket, no campaign hat, bare hands** (no gloves: her black nails are her distinction from
Ashby). In prompts: "a dark forest-green bomber jacket of smooth nylon twill with ribbed knit
cuffs, collar band and waistband", zipped to mid-chest with the one star badge pinned on it, the shirt collar
and tie knot above the zipper, each bare hand "out of the green bomber sleeve", tan riding
breeches and the thigh-high boots when the frame reaches them, "her head is bare, her long hair
loose over the jacket's shoulders".

Appearance block: *a white American woman of twenty-four, slim and toned with a full bust and long legs, fair skin, long wavy platinum-blonde hair with bold jet-black streak highlights falling past her shoulders, dark elegant makeup with smoky black eyeliner, long dark lashes and deep berry lipstick, striking bright green eyes, arched dark brows, and long almond-shaped nails painted glossy black.*

Character: twenty-four, the youngest deputy on the road and the best turned out, and she knows
both. Bratty, snarky, a bit mean: the dominant girl who ran her sorority, in an immaculate
uniform. She corrects with her mouth (orders, commentary, making a man repeat things back) and
rarely needs her hands; when she does, it's brisk, not rough. Bored is her default face; amused
contempt is the warm version. Calls men "babe" the way other people say "sir".

Methods: **money, mouth and scent.** She takes cash off men because it's funny to her that they
let her, and makes them thank her for it; she narrates what's wrong with a man to his face and
to whoever's in earshot; she spits, as contempt or as a treat, and makes him say thank you
either way. Her one kink with her body is **scent**: the inside of a riding boot at the end of a
shift, and the **thin black cotton knee socks** under them, damp. She doesn't want her boots
licked ("Gross. They're polished.") — she wants a man's face in them, breathing. Standing with
her is the card *Anderson's Attention*; full, it becomes *Anderson's Paypig*.

Barefoot or in socks (art): "her bare legs" never — the breeches stay on; the boot comes off
over them. Socks: "thin black cotton knee-high socks, damp and clinging, worn under the boots".

### Café Linde

**Francine Giardano** ("Signora Giardano") — owner of Café Linde, behind her own counter.
LoRA: `DMilfModel7:1`.

Appearance block: *a white American woman of forty with an hourglass figure, a large, full bust and a narrow waist, fair skin, glossy shoulder-length dark brunette hair with soft waves, black rectangular thick-rimmed glasses, bright green eyes, defined dark brows, and glossy red lipstick.*

Outfit (always, verbatim): *She wears a red silk blouse with long sleeves and a soft collar, the top two buttons open, tucked into tailored black trousers, and a crisp black bib apron tied snugly at the waist, its straps smooth over her shoulders; black patent high-heeled pumps show under the trouser hems.* The blouse's red matches her lipstick.

Character: forty, Italian-American, a barista before she was an owner, and still the best one
in the county. Calm, exact, warm in public and precise in private. Her whole method is
**instruction**: she teaches a man the way she'd teach a new hire to pull a shot — pressure,
timing, stop when I say — and she means every number. In the back room she watches a man touch
himself on her orders, or takes over with her own hand, and she decides how it ends: ruined at
the edge by default; properly, if he's earned it. Either way he cleans up after himself, with
his mouth, while she watches ("Nothing goes to waste in my kitchen."). She calls men "caro".
Her standing: the card *Café Linde Punch Card*; full, it becomes *Signora's Favorite*.

Art: the back room scenes are shot on her (framing rule 1): her face, her glasses, her hand at
his belt or holding a white espresso saucer; crop at his waist.

## Places in town

Named in prose, never in art (no lettering): describe the place, not its sign.

- **55 Graystone Heights** — the player's home, whoever he is: a pale gray clapboard two-story
  with a full-width porch, a porch swing, a maple in the yard. Living room with the laptop;
  a small clean bedroom under the eaves.
- **The Quarryman** — the pub on Main Street: dark green wooden shopfront, small-paned amber
  windows, an iron bracket sign with a crossed pick and hammer.
- **Café Linde** — the European coffee house across from it: cream and black striped awning,
  brass-framed windows, pastry case, marble bistro tables and bentwood chairs outside. Inside:
  a dark walnut counter with a brass rail, a polished chrome lever espresso machine, a short
  glass case of pastries (a few trays, not a bakery), black-and-white hexagon tile floor, cream
  walls, small marble tables and bentwood chairs along the front window. A door behind the
  counter to the back room: sacks of green coffee, a roaster, a steel prep table, a single
  bentwood chair. Francine Giardano bought it and kept the name: "You don't rename a good café." 
- **The doctor's office** — a converted red-brick Victorian at the south end of Main Street.
- **Mill Street** — the side street off Main: the Carnegie library at its end, the mayor's
  office (red-brick Italianate city hall, flag out front) on it.
