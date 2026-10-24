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

**Establishing shots with her in them: to the side, like the Sergeant at the café window.** The
room is the subject and she is recognizable in it. The left two-thirds of the frame look along the
room's depth (a counter, a table, a wharf, a row of warehouses running away from the lens); she
sits or leans in the **right third, three or four paces away**, anchored to something (a table, a
desk, a car door, a wall), turned half toward the lens, with her LoRA and full appearance block as
always. Don't make her "small" or put her "at the far end": with the LoRA, a distant woman came
forward to full size and often left a copy of herself at the far spot (library stacks and
computers, both docks views, the station lobby). Stripping the LoRA for those shots was tried and
rejected: it loses her.

Only one character LoRA per image: two named LoRA women in one frame blend into each other.
When a scene needs a second woman, she is an unnamed extra described in full, without a LoRA.

## Kink LoRAs (hard rule: only these)

The author's library holds many more; most aren't POV and pull the camera into third person.
In Graystone, use **only** these, at weight 1, and only when the image shows that thing:

| LoRA | When |
|---|---|
| `SA86RN444WSD83T4QX4PYS3P80:1` | detailed handcuffs (German handcuffs; trigger added by the loader). Name them **"clejuso handcuffs"** in the subject: the brand keyword cues the LoRA and keeps them apart from generic cuffs or bracelets. Keep the pose simple ("chrome clejuso handcuffs dangling from her grip"); open, swung cuffs render as a tangle. |
| `HandgagPOV_Krea2_v1:1` | her gloved or bare hand over the viewer's mouth |
| `pnkcg_krea2_000000750:1` | a chastity cage in frame. Graystone has **one cage: a small pink plastic chastity cage**, the county's standard issue and Juno's alike, in prose and art. The LoRA was trained on a woman holding it, empty, as a threat or a tease: write "a small pink plastic chastity cage, empty and unlocked, its curved pink bars open and hollow", held up in her hand by her face or chest. Worn or lying on a table is untested. |
| `"Krea2_BDSM Latex-Leather Megapack_V2E09:1"` | optional, for heavier BDSM gear |
| `"Krea 2 - Strapon Dildo:1"` | strap-on, POV |
| `"R2Y1DH5FQY41BT1Y6W67QWP730.nizLuQb9:1"` | facesitting, from under her looking up: she faces the lens and looks down at it |
| `femdom_handjob_krea2_epoch_20:1` | her hand on him: a handjob or hand teasing she gives the player, POV from his eyes (the one exception to framing rule 1) |

Not for this universe: the old facesitting LoRA (not POV) and the other metal-cuffs LoRA.

**Facesitting and handjobs always use their LoRA.** Every result, card or ending image that
shows facesitting carries `"R2Y1DH5FQY41BT1Y6W67QWP730.nizLuQb9:1"`, shot from under her
looking up (Ashby's OFFER at Cell Three is the reference). Every image of her hand on him, a
handjob or hand teasing, carries `femdom_handjob_krea2_epoch_20:1`, POV looking down (the
Signora's FINISH in the back room and Ashby's ASK at Cell Three). Neither act is shot without its LoRA.

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
   **Exception: her hand on him.** When she gives him a handjob or teases him with her hand,
   the shot uses `femdom_handjob_krea2_epoch_20:1` and shows it: the camera tilted down, his
   erect penis rising from the bottom center of the frame in her hand, her face beyond it
   looking into the lens. Name it plainly ("an erect penis that rises from the bottom center
   of the frame") and nothing else of him. Every other act still crops at his waist.
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

- **Detailed, but phrased simply (the lesson behind the others).** Write the subject as one
  consistent picture in plain sentences, in priority order — the shot and place, the focal
  subject, her expression, her face, what she wears, props, then the background last (the
  encoder weighs early words more; see the Krea guide §8). Long is fine; complicated isn't. Many
  failures below were made worse by fixes that stacked camera geometry, frame-edge instructions
  and "being tried" clauses into one prompt until the model had to guess the intent (Seo's
  TRAMPLE and RIGHTS took five renders until rewritten plainly). When a fix needs a new clause,
  rewrite the paragraph instead of appending. And only describe what is in frame: the full
  uniform sentence names the boots, and naming the boots makes the model show them, by seating
  her if it must.

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
- **Through the mesh** (Anderson's holding cage): the same recipe for chain-link. "Running
  unbroken across the whole frame from edge to edge", "the lens pressed close behind it", and
  her "four paces away … small in the center", face in one clear diamond. "Soft in the near
  foreground" alone gave two strips of fence at the frame's edges, read as an open gate, with
  her at the viewer's elbow (first render).
- **Cuff words put cuffs on her.** Any "handcuff" or "cuffs" in a subject with her in it
  (even "a handcuff case on her belt") renders as a cuff or a steel bangle on her own wrist, or
  cuffs in her hand instead of the prop you asked for. Her appearance block carries no cuffs.
  Mention cuffs **only when they're the centerpiece** (TERMS, PROMISE, the Prison Chains card),
  with the detailed-handcuffs LoRA. In general, props in her block land on her body.
- **Viewer leaks.** Shots from the cot or the floor with her legs spread above or across the lens
  (boot on the cot rail with her leg raised, a woman lowering herself onto the lens) make the
  model add the viewer's penis, or draw intercourse. So:
  - **Facesitting** uses the facesitting LoRA and is shot **from under her, looking up**: she
    sits on the lens facing it, fully in uniform, her breeches' crotch and thighs filling the
    bottom of the frame, her bust above, looking down into the camera. (Before that LoRA it was
    shot from behind, the moment before.)
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
- **The old chastity LoRA filled an empty cage** (`chastity_000005800:1`, retired for the pink
  cage). When she held the cage it rendered with anatomy inside unless written as "empty,
  unlocked … its curved bars open and hollow", and hooked on a finger at chest height it still
  filled (Juno's cage photo); hanging it by her face, "dangling by a small open padlock … the
  light shining straight through it", worked. Keep that wording with the pink LoRA until its
  renders say otherwise.
- **A jacket "hanging open" is worn half.** Say both arms are in its sleeves and both
  shoulders are covered, and put the patch and chevrons on the jacket's sleeves.
- **The outdoor jacket and hat fight each other** (Anderson's first arrest render, Ashby's
  church-steps render): the forest green spreads into the hat (a dark olive fedora instead of a
  tan campaign hat), the open jacket is worn on one arm, and its chest star doubles the shirt
  badge. Being tried on Anderson: no hat, the jacket **zipped to mid-chest** with the only star
  on it, each hand named as coming "out of the green jacket sleeve". "Pocket flaps piped in
  azure" renders solid blue flaps: write "tan flap pockets edged with thin vivid azure blue
  piping".
- **Draw focus.** A result frame is about one thing: the act. ADMIRE (framed lips to belt, the
  tie and star filling the frame, his hand on the tie) and KNEEL (the boot alone, toe to knee)
  are the models. Frame on what the act touches, say where the bottom edge cuts, and describe
  only what is in frame; leave out the rest of the uniform, the car, the room. Prompts that
  asked for her whole kit plus the whole car came out busy and broken: Anderson clipping
  through her door (INTRODUCE), a leg through the steering wheel (Paypig SEND), a boot on the
  dash from the passenger seat (FLATTER-WARM). Establishing shots and portraits show her whole;
  results mostly don't.
- **If her waist is in frame, name the trousers.** A waist-up subject that left the breeches
  out got green trousers under the bomber (Anderson's Attention card) and azure trousers under
  the tie (her Paypig card): the model fills a missing garment from the nearest color. Whenever
  the frame reaches her waist, name the duty belt and "tan riding breeches, the same khaki tan
  as her shirt". A chest-up or face shot says where the frame stops instead.
- **Thighs filling the frame turn azure.** In Ashby's facesitting shot (OFFER) "a vivid azure
  blue stripe down each outer seam" on breeches that filled the frame rendered as broad azure
  panels over half of each thigh, and "a thin piping line" still left azure blotches. When the
  breeches fill the frame, leave the stripe out altogether.
- **Describe what you want, never what you don't** (prompt guide §2). Whatever a prompt names, it
  draws, negated or not. "No post, no gate, no gap" grew posts and a gate around the holding cage
  four times; "no fences, cages or partitions" fenced her desk in; "nobody standing anywhere" kept
  a standing second Ashby at the café window. Name the positive picture ("a single sheet of wire
  mesh over the whole picture like a screen door", "an open bullpen", "the window beside her
  fills the background") and leave the unwanted thing unmentioned. The same goes for "nothing of
  the viewer is in frame": say what the bottom edge is instead.
- **An empty room gets filled with her.** "One woman, alone" isn't enough in a room with depth
  behind her: the café window drew two Ashbys, the counter and the back room each a second
  Francine, STAY a second pair of heels. Keep the shot close on her, give the background a
  concrete subject of its own (the window and the square beyond it, the stacked sacks), and leave
  unnamed extras out unless the scene needs them.
- **To the side still drew a second her at the docks.** Standing or leaning in the right third
  (Seo at her car door, Red against the wall) brought a full-size copy into the empty middle of the
  wharf or lot, with the original left at the named spot. Being tried: seat her (Seo sideways in
  the driver's seat, boots on the concrete; Red on a stack of pallets), and give the middle of the
  frame a concrete subject (the ship's hull, a puddle), with a prop in the near left foreground.
  Worked for Red; Seo still came forward to crouch in the middle with a copy in the car. Being
  tried for Seo: give the LoRA its big foreground at the side — two paces away at the right edge,
  hips up, leaning on a lamp post — and park the cruiser small down the wharf, tinted and shut.
- **A copy behind her in a small room.** The kitchenette GREET drew a second Anderson at the
  counter behind her. Being tried: two paces, and a background that's flat and close (the
  refrigerator door crowded with papers), not the room's depth.
- **Nothing in the phone's photo may run off its edge.** "Striped socks run up out of the top of
  the photograph" (DM boots) continued the socks outside the phone, as legs in front of the
  viewer's lap, and the photo read as Juno holding her own phone. A mirror selfie "glasses to
  knees" put her penis outside the phone (DM bulge). Say where the photograph's edge cuts her,
  "inside the screen", keep a mirror's frame whole inside the photo, and name the bottom edge of
  the frame as the gray wall between the wrists. That still leaked (second render of both): the
  space behind a held phone is where a lap goes. Only chest-up photos survive the held-phone shot
  (DM selfie, video). Being tried for anything lower: the phone lying flat on a walnut table,
  shot from directly above, wood grain to every edge, his one hand resting beside it. Worked
  (boots, socks). The held phone leaked even a chest-up bubble-tea selfie (her body under the
  phone, her nails on his hands), so use the table for every new DM.
- **Chastity cage LoRAs, settled:** the pink plastic cage (`pnkcg_krea2_000000750:1`) replaced
  every metal cage. Tried and dropped before it: `0EK4J7JPM6F67BN8VC86C3DFG0:1` (a flat metal
  cap cage) and `30QCFXF2SWVGFPBY9SE3M51VK0` (it put a filled cage on the viewer, below the
  phone).
- **"Flat on the back, looking up" came out eye level.** Seo's TRAMPLE and RIGHTS renders sat her
  down on the floor beside the camera, legs out, with ordinary pews, windows or horizon behind.
  Being tried (the author's tip): open with "Extreme low-angle worm's-eye … pointing straight up
  at the ceiling / sky", say the ceiling or sky **fills the whole background**, and build her from
  the corners: one boot rising enormous from a bottom corner, her body tapering up, her face small
  at the top center. Second render: still sitting, legs toward the lens. A sole or boot near the
  lens means a foot at floor level by the camera, which the model can only draw as her sitting.
  Being tried: no sole, no props, no room — "the camera lies on the floor between a standing
  woman's feet", her legs rising "like pillars" from the bottom left and right, meeting high in the
  frame, her face small at the top center, "behind her, only the ceiling / sky".
- **Boots in the description sit her down.** Naming her boots in a widescreen shot (Seo in the
  holding-cage door) makes the model fit them in, and the only way it can is to seat her. When she
  must stand, frame her from the waist up and leave the breeches below the frame and the boots out
  of the prompt.
- **Write the picture in order, plainly.** The author's model for a towering shot: "Extreme low
  angle shot photograph, taken outdoors on a wharf, looking up at the sky and at Deputy Seo. Her
  boot is extended down, the focus on her sole. Beyond the boot, she towers over the camera,
  wearing [uniform], with [expression]." One consistent picture, nearest thing first, then what's
  beyond it, then the background. Earlier words weigh more: angle and the focal subject first,
  then her expression, face and uniform, small props after, the background (sky, ceiling) last. Clauses that make the model guess at intentions (camera
  geometry in three ways, what's *not* in frame) confuse it. `soles pov` was tried at 1 and 0.5
  and dropped: it shifted the colors, half-bared the boot and moved the wharf indoors.
- **A braid alone becomes a wig.** A braid "lying on the concrete" without her (Seo's arrest) or
  "a single violet hair" on a car roof (Snitch card) rendered as a cut-off hank of hair. Leave
  her hair out of frames she isn't in.
- **A low camera under a bending woman sees his legs.** SERVICE from kneeling height showed bare
  thighs at the bottom edge and a short tie. Uniform close-ups follow ADMIRE: "the camera level
  and close to her chest", framed from her lips to her waistband, which crosses the bottom edge.
- **A boot that comes off must leave the frame of her legs.** Holding the boot while her legs
  are in frame drew it back on her (cruiser INHALE), a boot on one leg and a bare foot on the
  other (holding BEG), and boots under the socks (WORSHIP). Frame her from the waist up, write
  "her legs are below the frame", and name the boot as "a single empty … boot, off her foot".
  Don't stand spare boots beside her: they get put on. Boot worship on a worn boot is a detail
  shot from the toe to just above the knee, nothing higher (SHINE drew a loose boot on the tile).
- **"Boot top toward the lens" drew a bucket.** Keep the whole boot readable: "visible from its
  open top to its rounded toe", dangling from her hand by the shaft.
- **Viewer hands appear unasked** when she holds something toward the lens (ANSWER's clipboard,
  SHOW's saucer). Keep the prop against her own body ("flat against her own chest in her bare
  left hand") rather than pushed at the lens.
- **Naming her breeches stands her up.** In a car-window shot the full uniform pulled Anderson
  out of the car. Frame her chest-up inside the window opening, "like a picture frame: the roof
  edge above, the door pillars on either side, the white door below the sill", and leave the
  lower uniform out.
- **Anchor her in the car with her arm.** "Sits behind the wheel" alone, with a full uniform,
  put Anderson half out of the door three times. "Her left elbow on the window sill and her chin
  propped on her hand" (FLATTER-COLD) kept her inside every time: the canonical cruiser pose.
  A hand on the steering wheel next to a hand holding a prop grew a third arm (INTRODUCE).
- **A low camera sees her legs.** From kneeling height looking up, "her legs are below the frame"
  didn't hold and the boot went back on her foot (cruiser INHALE, three times). For a boot she's
  holding, use standing eye height and frame her from the chest up, "the bottom edge at her tie
  bar", and hold the whole boot up beside her face.
- **Chain-link builds cages around her.** With the mesh in front, the model also fenced her desk
  in. Being tried: the wire as "a screen door" over the whole picture, the room beyond described
  as an open bullpen, and her "seen full length and small" in the middle distance.
- **Gestures at the lens become fists.** "Fingertips under the viewer's chin" rendered a fist
  coming at the camera twice (STAND). Keep corrective gestures near her own face.
- **Name sleeve length when you crop the shirt.** A face close-up with only "the collar of a tan
  uniform shirt" got short sleeves (TEASE): write "long-sleeved … buttoned at the wrists".
- **Gags render as props badly.** With no gag LoRA, "a black rubber bit gag" came out as a
  black bulb on a strap (Gag card). Show the moment instead: her hand over the mouth from POV
  with `HandgagPOV_Krea2_v1:1` (NOISE, TEASE), and keep gag objects out of frame.
- **Phone in hand: standing, landscape, filling the frame.** "Seated eye height, camera tilted
  down" with a phone in his hands put his bare lap round the phone in every SIMP photo, often his
  cock at the bottom edge, and once her striped socks and skirt on his own legs. Standing at arm's
  length fixed the lap, but the room behind the phone then grew a second her (or her boots, or a
  filled cage) out of the photo's subject. What works: "standing eye height, the camera level", the
  phone **turned sideways in landscape**, held close in both hands from the bottom corners, filling
  most of the frame with "only a thin margin of plain charcoal-gray wall" around it. Her content
  is shot **in her bedroom at home** (pastel posters, a pink LED strip, black and pink sheets, a
  gaming desk), never the library.
- **Her nails go on his hands.** With her black and pink nails in the photo on the phone, the
  hands holding it got long painted nails. Leave her nail color out of anything his hands are in,
  and give his hand "broad knuckles, short, bare, unpainted nails cut straight across".
- **Juno's LoRA undresses her.** Even with the hoodie and crop top written in, her own photos came
  out topless or nude; in public places that's why her framing rule exists (see her entry). On
  her page, a two-column layout grew a big topless cover photo: write "a single centered column",
  a small round avatar, and the hoodie "zipped up to a black velvet choker".
- **A distant woman gets a close copy.** In the reading room a second, full-size Miss Carrow stood
  in the right foreground; in the computer corner Juno came forward and a copy sat at her corner
  table; the same at the docks and the station lobby. A concrete foreground and "the only person
  in the room" didn't stop it. Use the café-window composition instead (see "Establishing shots
  with her in them" under Character LoRAs).
- **Green furniture turns tan wool green.** The Sheriff's first desk shot, with a green leather
  desktop, rendered a "khaki tan" dress jacket dark olive green. Here that became canon (see the
  dress uniform); elsewhere, keep green out of frames with tan wool you want to stay tan.
- **A cruiser half in frame needs the whole car sentence.** "The white door and tan flank of the
  cruiser" behind Seo drew an old white-and-blue sedan. Even out of focus, write the canonical
  patrol car sentence.
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
vivid azure blue chevrons beneath the patch on each sleeve". **Never drop the breeches**, however
tight the frame: write "tan riding breeches, the same khaki tan as her shirt, with a vivid azure
blue stripe down the outer seam". Drop only the boots when the frame doesn't reach them. Name each hand "out of the green bomber sleeve" when it acts. The
hat is a separate sentence, in shirt-tan, never next to the green; a deputy may go bareheaded
as her personal look (Anderson).

**Rank** goes after the uniform sentence: sergeant — three vivid azure blue chevrons on each upper
sleeve beneath the patch. Deputy — no chevrons: leave the rank sentence out, and outdoors drop
"above three vivid azure blue chevrons" from the jacket sentence (the patch alone stays).
Sheriff — the dress uniform below, with three small gold six-point stars on each epaulet.
(Other ranks: to be set with their characters.)

### Dress uniform (the Sheriff, canonical)

The patrol uniform's shirt, tie, breeches and boots under a closed **dark olive-green** dress
jacket instead of the bomber, indoors and out. Never the bomber, never open. (The first desk
render came out green from a "tan" subject, the author loved it, and green is canon now.)

She wears the Graystone County Sheriff's dress uniform: a tailored, fitted single-breasted dress jacket of fine dark olive-green wool, closed at the front with four polished gold buttons from the waist to below the breastbone, its notched lapels piped and its cuffs banded in vivid azure blue, shoulder epaulets edged in vivid azure blue with three small gold six-point stars on each, an embroidered vivid azure blue and gold patch on each upper sleeve and a polished gold six-point star badge pinned on its left breast; in the V of the lapels, only the pointed collar of a crisp, pressed tan uniform shirt and the knot of a vivid, saturated azure blue necktie with a small gold tie bar; a black leather belt with a polished brass buckle; tan riding breeches, the same khaki tan as her shirt, with a vivid azure blue stripe down the outer seam; and stiff, structured, mirror-polished black leather thigh-high riding boots with rigid straight shafts and low, flat stacked-leather riding heels, fitted tight to the leg, pulled up over the breeches to mid-thigh; her head is bare.

Drop the boots when the frame doesn't reach them; keep the breeches whenever her waist is in
frame. Her desk is green leather; it suits the jacket.

### Patrol car (canonical, verbatim in every subject with a cruiser)

Lead with "a Graystone County Sheriff's patrol car" (or "N identical Graystone County Sheriff's
patrol cars …, each"), then:

a present-day Ford Police Interceptor Utility SUV painted two-tone, with a white roof, hood and front doors over a tan body, a broad vivid azure blue stripe running the full length of each flank below the windows, a gold six-point star decal on each front door, a low black roof light bar with red and blue lenses, a black steel push bumper bolted across the front grille and black steel wheels

A parked, unattended cruiser adds "its windows are tinted dark and its light bar is unlit".
"Bolted across the front grille" keeps the push bumper on the car: without it, a car seen
side-on grows a loose black railing in the street (Anderson's arrest, second render).
Every `patrol` location shows one somewhere in frame.

### The Sheriff

**Sheriff Laura Brandt** (*name is a proposal*) — runs the department from her office upstairs
in the First Church, an executive office with a window over the bullpen.
LoRA: `DMilfModel3:1`. Rank: sheriff (the dress uniform: a dark olive-green jacket).

Appearance block: *a white American woman of forty, slim and shapely with a full bust, fair
skin, long curly auburn hair styled in loose, soft waves falling past her shoulders, striking
bright blue eyes, softly arched brows, and natural rose lipstick.*

Character: forty, Graystone born, twelve years with the state police before the Mayor asked her
home to rebuild the department from nothing. She hired every woman in it. Warm, easy, the
pleasant, inviting smile of someone who has never needed to raise her voice, because everyone
in the building raises theirs for her. Remembers everybody's name, mother and middle name. The
smile doesn't change when the news does; that's how people learn to be afraid of it. Calls men
"hon".

Off duty doesn't exist; she wears the dress jacket at her desk, closed, all day.

Methods: *to be decided*.

### The front desk

**Niamh Doyle** (*name is a proposal*) — the department's office manager, at the reception
desk inside the church doors. Civilian staff: she doesn't patrol, doesn't carry, and runs the
building. She's the one who sends the emails with the smiley faces.
LoRA: `DGirlsModel8:1`.

Appearance block: *a white woman of twenty-seven, Irish-Australian, drop-dead gorgeous, with
delicate, beautiful features, a toned build with a medium-large bust and wide hips, fair skin,
long wavy ginger hair swept all over to one side and falling over her left shoulder, dark smoky
eye makeup with long dark eyelashes, neatly trimmed brows, striking bright green eyes, and
glossy dark red lipstick.*

Outfit (always, verbatim): *She wears a crisp, pressed tan long-sleeved uniform shirt of heavy
cotton twill with a pointed collar, shoulder epaulets edged in vivid azure blue and an embroidered
vivid azure blue and gold patch on each upper sleeve, tucked into a tight, high-waisted tan pencil
skirt, the same khaki tan as the shirt, ending just above the knee; a vivid, saturated azure blue
necktie with a small gold tie bar; sheer black stockings; and glossy black patent leather pumps
with very high, thin stiletto heels.* No badge, no duty belt: she's civilian. Formal, and more
sexy for it.

Character: twenty-seven, from Melbourne by way of a Cork grandmother, and nobody in Graystone has
worked out how she ended up here. She has an accent people drive across the county to hear and
uses it like a key. Bright, quick, flirts like breathing and means about half of it. Nothing
gets past her desk she hasn't decided to let past: visitors sign in, contractors show a badge,
and everybody else waits on the bench until she's finished her tea. Calls men "love".

Methods: **warmth, praise and permission.** She rewards a man in public: a running commentary
on how good he is, to whoever's listening. Her uniform is her vanity; a man who notices it gets
to touch it, with his hands and his words, never his mouth, and only because she said so. She
escorts contractors in and out herself. Standing with her is the card *Niamh's Good Side*.

Distinguishing her from Miss Carrow, the other ginger: Niamh's hair is swept over one shoulder,
her lipstick dark red, the uniform shirt and tie; Carrow's hair is loose on both shoulders, her
lipstick wine, the charcoal suit.

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

### Patrol: the docks

**Deputy Seo Min-ji** ("Deputy Seo"; *name is a proposal*) — patrols the river docks, mostly on
foot beside her parked cruiser.
LoRA: `DGirlsModel9:1`. Rank: deputy (no chevrons).

Patrol look (her outdoor uniform, instead of the canonical outdoor one): **the green bomber, no
campaign hat, ever, and gold aviator sunglasses.** As Anderson's: "a dark forest-green bomber
jacket of smooth nylon twill with ribbed knit cuffs, collar band and waistband", zipped to
mid-chest with the one star badge pinned on it, the shirt collar and tie knot above the zipper,
each hand "out of the green bomber sleeve", tan riding breeches and the thigh-high boots when
the frame reaches them. Then: "her head is bare, her violet braid rising high above it" and
"gold-framed aviator sunglasses with mirrored lenses". When the scene needs her eyes, she pulls
the aviators down her nose and looks over them.

Appearance block: *a Korean woman of twenty-nine, a classic Korean beauty with an elegant oval
face, a softly tapered jaw, large almond-shaped dark brown eyes, sharp black winged eyeliner,
delicate straight brows, a refined small nose, softly defined cheekbones, berry-pink gradient
lips and luminous, smooth pale skin, her extremely long, glossy, vivid neon violet-purple hair
woven into one enormous high French braid that rises from the crown of her head and falls down
her back past her waist.*

Character: twenty-nine, born in Incheon, a harbor town, and the only deputy who asked for the
docks. Eccentric, and attractive in a way she doesn't seem to notice. She watches everything
and comments on the wrong part of it: the gulls (she has named them), the barge numbers (she
keeps a list), the way a man stands (she'll tell him which foot he's lying on). Talks to the
river. Hums. Polite, cheerful, impossible to read, and never once surprised. Gives men a
nickname for whatever she noticed first, and uses it until she learns their name.

Indoors (her holding cage) she wears the canonical indoor uniform, head bare, the braid, and the
aviators hooked by one arm into her shirt's placket.

Methods: **protocol, the floor and the glove.** She sees a wanted man before he sees her, puts
him face down by the book, every instruction said once in that small soft voice, and reads him
the Graystone advisement word for word while she stands on him. Her heat is **CFNM**: he is
stripped at booking and stays naked until she hands his clothes back on the church steps, one
piece at a time, in front of the square; she stays buttoned to the collar and writes everything
down. With her body: **trampling** (her whole weight, walked up him, the sole over his face)
and **light anal play** — the gloved cavity search that turns into milking him, logged in the
notebook. She never raises her voice and never once looks surprised. A man who gives her
evidence gets a page in that notebook instead: her snitch, later her informant.

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

## The GrayBloods

Graystone's gang, what's left of it after the department rebuilt: a few crews working out of the
warehouses at the docks. Red is their color.

**Red** (Shanice "Red" Dupree; *name is a proposal*) — a GrayBlood, holding up the wall of a
dockside warehouse.
LoRA: `DGirlsModel5:1`.

Appearance block: *an African American woman of twenty-one with an oval face, smooth dark brown
skin, long straight glossy black hair worn loose down her back with one thin braid running from
her temple, striking pale blue eyes, full lips with glossy nude-brown lipstick, small gold hoop
earrings.*

Outfit (always, verbatim): *She wears an oversized glossy red puffer down jacket hanging open over a
fitted black top, low-slung light-wash jeans and white high-top sneakers.*

Character: twenty-one (the bible's floor; the author said twenty), born on the river side of
town, a GrayBlood since she was old enough to carry. Loud, smug, in your face: the kind of
confidence that has never once been told no and made it stick. She talks over people, laughs at
her own jokes because they're good, and stands closer than she has to. Thinks the department is
a joke that hasn't been told to her yet. Calls men "lil bro".

Methods: **mockery, pat-downs and the hustle.** Every man is a narc until he proves otherwise,
and the proof is money he hustled himself and hands her (*Red's Errand*, then *GrayBlood Rep*).
She frisks men against the warehouse wall, reads their IDs out loud, and makes them say things
back until they say them right. Long white nails (prose and close-ups only; not in her block).

## The library

**Miss Imogen Carrow** (*name is a proposal*) — head librarian of the Carnegie library, behind
the circulation desk in the reading room. One of the town's disciplinarians, not police.
LoRA: `DMilfModel4:1`.

Appearance block: *a white British woman of thirty-eight, tall with an hourglass figure and a
large, full bust, fair skin with a few faint freckles, long wavy ginger hair falling loose past
her shoulders, dark smoky eye makeup with black eyeliner, striking bright green eyes, defined
auburn brows, and deep wine-red lipstick.*

Outfit (always, verbatim): *She wears a tailored charcoal-gray wool skirt suit: a fitted
single-breasted jacket with sharp notched lapels, buttoned once at the waist, over a cream silk
blouse open at the collar to the top of her cleavage; a knee-length charcoal pencil skirt; sheer
black stockings; and glossy black patent leather pumps with thin, high stiletto heels. A slim
gold watch sits on her left wrist.* The heels are her signature: in prose you hear her before
you see her, a sharp click on the oak boards as she comes toward you, or as she walks round
behind you. The cleavage is the blouse's open collar inside a closed jacket: never an
unbuttoned jacket, a lace edge or a bare chest. Her hair stays loose and long; a bun, a cardigan,
pearls or glasses on a chain would age her twenty years (see the top of this file).

Character: thirty-eight, from somewhere outside Bath, a governess's training and a librarian's
degree, here eleven years. Nobody in Graystone knows why she came and nobody has asked twice.
Strict in the old way: silence in the reading room, books handled with clean hands, fines paid
in full, and "young man" for any man under sixty. Polite to the point of cruelty. She keeps the
library the way the Sergeant keeps the Undercroft, and they have tea. She knows who
reshelves her true crime into gardening, and has decided to let it run, for now.

Methods: *to be decided* (a disciplinarian; her storyline comes later).

**Juno Vance** (`@rootkitty`) — at the corner table of the Carnegie library's computer corner,
on her own laptop. Not police, not anybody's employee.
LoRA: `KreaTransBabe:1`.

Appearance block (*proposal: check skin, hair and build against the LoRA's renders*): *a trans
woman of twenty-three, slim and petite with narrow shoulders, a small bust and long thin legs,
pale skin with a light dusting of freckles across her nose, long straight hair dyed half jet black
and half pastel pink, split sharply down a center part, the left half jet black and the right half
pastel pink, worn in two low pigtails, blunt straight-cut
bangs, thick black rectangular rimmed glasses, sharp black winged eyeliner, glossy pale pink
lips, a small silver ring in her septum, and short nails painted black and pastel pink in turn.*

Outfit (always, verbatim): *She wears an oversized black cotton hoodie slipping off her left
shoulder, a fitted white ribbed crop top under it, a short black pleated skirt, black and pastel
pink horizontally striped thigh-high socks, and chunky black platform boots with thick
rubber soles and silver buckles; a black velvet choker with a small silver O-ring sits at her
throat, and pastel pink over-ear headphones with small cat ears hang around her neck.*

Her laptop (when it's in frame): *a plain black laptop, the back of its lid covered edge to edge
in small, colorful vinyl stickers of cartoon cats, stars, hearts and lightning bolts, none of them
with any lettering*. "Edge to edge" matters: with a few stickers the model put an Apple logo on
the lid.

**In public she is dressed (hard rule).** Her LoRA was trained on explicit material and undresses
her whenever her lap, legs or skirt are in frame: the first table render had her skirt open and
her cock out in the middle of the library. Her nudity belongs to her own photos (the SIMP beats)
and to private scenes later. So in a public place:

- Frame her **from the waist up, behind something**: a table edge or the laptop lid crossing the
  frame at her waist ("the warm oak tabletop runs across the whole bottom of the frame and crosses
  her at the waist").
- Use the **top half of her outfit only**, with the hoodie **zipped halfway up**: *She wears an
  oversized black cotton hoodie, zipped halfway up and slipping off her left shoulder, over a
  fitted white ribbed crop top; a black velvet choker with a small silver O-ring sits at her
  throat, and pastel pink over-ear headphones with small cat ears rest around her neck, below her
  chin.* Leave the skirt, socks, boots and "long thin legs" out of the subject.
- Sit her **upright or leaning forward** on the table, never leaning back, legs up or crossed in
  view.

Character: twenty-three, Graystone born, two years of a computer science degree before she got
bored and came home. Lives online. The library has free wifi, quiet, and a steady supply of men
using the public computers for things they shouldn't, and she has read every one of their
browser histories. Runs **@rootkitty**, a subscription page: chastity tasks for men who pay for
them, and her cock, which is the point. Confident, mean and tomboyish: a gamer's trash talk, not
a sorority girl's (that's Anderson). Calls men "dude", "loser", and, when they've earned it,
"good little faggot", cheerfully. Texts in lowercase, with "lol".

Methods: **the hook.** She doesn't take men; she lets them come to her. A photo, a price, a dare.
She gets straight men curious about her dick and then makes them say it out loud, and every time
they pay for another look she reminds them what that makes them. Chastity is how she keeps a man
thinking about her between messages. Standing with her is the card *Subscribed: @rootkitty*;
full, it becomes *Rootkitty's Simp*.

Art: her photos come to the player's phone (the phone held sideways in his POV hands, the photo
filling its landscape screen), shot in her bedroom at home; or she's shot across the library
table. Her bulge is shown through the skirt; when she
shows more, the frame is on her and her hand, per the framing rules (his body never).

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
- **The First Church station** — walkable as far as the front desk: up the church steps from
  Main Street into the narthex, where Niamh Doyle's reception desk faces the doors. Through the
  inner arch the nave is the bullpen, steel desks under the stained glass, with the chain-link
  holding cages in the side aisle. Past the desk only with a contractor badge: the bullpen; the
  old sacristy, now a kitchenette with a restroom; a small annex built onto the back of the church,
  through a short covered walkway, as the department gym (mats, a heavy bag, lockers); and up the stair, the Sheriff's office, built into
  the old choir loft but fitted out as a proper executive office (walnut paneling, a green
  Chesterfield, law books, a big walnut desk with a green leather top), with nothing of the church
  left but one round stained-glass window behind her desk and a glass window over the bullpen. Down from the nave is the Undercroft (events only).
- **The docks** — down Front Street from Main, where the river runs wide and brown past the
  grain elevators: a concrete wharf with iron bollards, a rusting river cargo ship tied up, and
  across the lot a row of corrugated steel warehouses with roll-up doors, one of them always half
  open. The department parks a cruiser at the end of the wharf; the GrayBloods hold the
  warehouse wall.
- **The Carnegie library** — one round reading room under the copper dome: a skylight in the
  dome's eye, dark oak shelves around the curved walls, long oak reading tables with
  green-shaded brass lamps, a cast-iron spiral stair to a gallery. On one side, by a tall arched
  window, the computer corner: four beige public computers on a long laminate table, and a
  small round table in the corner where Juno sits. Across the room from it, the circulation
  desk: a curved dark oak counter with a brass bell, a date stamp and a card catalogue behind
  it, where Miss Carrow sits.
