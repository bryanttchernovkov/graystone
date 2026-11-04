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
write "the same woman as before", and never use a name alone. For downloaded LoRAs the trigger
words are added by the LoRA Manager node; don't repeat them in the subject. **The author's own
LoRAs** (from `~/code/prive/loras`: `ashby7`, `hngcf5`, `mtlcg7`, `pvcg5`) have no trigger
metadata: write the trigger into the subject, phrased as their captions taught it.

**Prefer the author's own LoRAs.** Since 2026-10-26 Graystone has no style LoRA (`retro-80s`
was dropped from `style.yaml`); the look comes from the prefix and the character and object
LoRAs. A woman with her own trained LoRA (Ashby) gets a short block instead of the long one:
her LoRA was trained on her face, build and kit, so the subject names only her trigger phrase,
her hair and the kit that is in frame.

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
| `hngcf5_krea2_000001500:0.9` | handcuffs, any image with cuffs in it, **except the Undercroft's** (see `pvprsn7`). **Graystone's road cuffs are hinged** (county issue, every deputy's): two cuffs joined by a solid steel block, no chain, in prose and art. Write "closed polished stainless steel hngcf5 hinged handcuffs" plus a size phrase ("about the length of her hand and wrist", "each cuff a little wider than the wrist"); don't name their parts. Closed only: open cuffs are unreliable. Trained on cuffs held in a hand; lying flat works in the LoRA's showcase. |
| `pvprsn7v3_krea2_000001250:1` | **the Undercroft, from the inmate's own eyes** (`~/code/prive/loras/pov-prison-life`, v3 step 1250; read its README). A first-person view looking down at his own body in a bright orange jumpsuit (baked in: never name it), bare hairy forearms and bare feet, in **Ashby's own kit**, which is the Undercroft's in prose and art: polished steel chain handcuffs, the chain padlocked with a brass padlock to a worn brown leather waist belt, steel leg irons on bare ankles, and, after CLIMB, black leather mitts with the cuff and a brass padlock locked over each. Like `pvarst7`, it is the exception to framing rules 2, 6 and 7: write it in the LoRA's caption order, `pvprsn7 POV prisoner photo, a first-person view looking down at his own body, <pose>, his bare pale hairy forearms in the foreground. <restraints, in the caption phrases>. <her and what she does>. <what the view shows around them>, <light>.` **Four poses only**, as trained: standing with her standing close ("her tan uniform shirt … fills the top of the frame … her boots stand on the flagstones just in front of his bare toes"; never "the top of her head" on a standing woman, it shrinks her), standing or on the cot edge with her kneeling at his ankles ("the top of her head, the shoulders of her uniform shirt, and her hands …"), seated at her desk with her across it (the only pose that shows her face), and lying back on the cot with what lies past his feet. Prose has to match: he is barefoot in county orange from TERMS on, and her cuffs have a chain. Used in TERMS, APPEAL, PROMISE, CLIMB, WAIT and the Prison Chains and Mitts cards. Not with `hngcf5` (it draws its own cuffs) or the cage LoRAs. |
| `pvarst7_krea2_000002250:0.8` | the arrest itself: POV from the arrested man's own shoulder, looking at his arm cuffed behind his back while she grips his forearm and holds the second cuff (the three `*-arrest` images). Write it in the LoRA's caption order: `pvarst7 POV arrest photo, a first-person view from the arrested man's own shoulder, looking down past his right shoulder at his right arm…`, his plain heather gray T-shirt, blue jeans and bare forearm (fixed by the LoRA), her on the side of his cuffed arm, "no jewelry" or each accessory named, bare-handed or her gloves, "grips his forearm just above the polished steel hinged handcuff locked on his wrist and holds the empty second cuff, closed, in her other hand", then her expression, the place and the light. It draws the hinged cuffs itself: no `hngcf5` with it. Lying face down (Seo) says "looking back past his right shoulder along his back" instead of looking down. Seo's two arrests load `sorenji` 0.9 and it together in one image. Redoing them with it alone in the base and `sorenji` in a short pass above the cuffs wasn't worth it, so they were restored (2026-11-02): the pass only kept her hair pink at `sorenji` 1 and denoise 0.5 with the bob named, her brows stayed pinched, she still knelt despite "legs straight", and the base's wharf cuff came out as a loose chain. Weights: `pvarst7` at 0.8 and the character LoRA a notch down (`tfny7` 0.9, `ashby7` 0.8, `sorenji` 0.9); at 1 + 1 the renders looked over-sharpened. Keep the prompt close to the caption order: spelling out his shoulder and a twisted arm, or saying his head is out of frame, made it worse (2026-10-28). Vary the T-shirt colour, side, lens and her expression between images. **Stay inside what the LoRA was trained on**: him standing (or face down, for Seo), her beside his cuffed arm, the place only as background. **Every one of its 30 training captions is the same pose**: he stands upright, the camera looks down past his shoulder, his shirt fills the near side, his head is never in frame, and the place is only background ("Set in …", one sentence; dataset in `~/code/prive/loras/pov-getting-arrested/dataset`). Bent over a counter or table is out of domain: the model falls back to a two-shot, a reseed doesn't change it, and the woman's LoRA fills the second person (Ashby's station arrest drew "him" as a second Ashby, locs and all, 2026-10-31; the café arrest only got away with it, his face is in frame). Put tables and counters behind her, and the bending in the prose. Write new arrests as a training caption with her block swapped in. **Ashby: use the left-side pose** (her on the left, his left arm). On the right, even in the caption pose, `ashby7` put her locs and build on his near shoulder; mirrored it came out clean (2026-10-31). Her own LoRA has POV cuffing shots (dataset 33, 34) with the viewer as a forearm from the bottom edge only, so it has no man's body to draw near the lens. Show the counter or the table in the prose, not the image. |
| `HandgagPOV_Krea2_v1:1` | her gloved or bare hand over the viewer's mouth |
| `mtlcg7d_krea2_000001250:1` | a chastity cage in frame. Graystone has **one cage: a small stainless steel chastity cage**, the county's standard issue and Juno's alike, in prose and art. The LoRA suits a POV shot of a woman holding it, empty, as a threat or a tease: write the LoRA's own phrase, "an empty stainless steel mtlcg7 chastity cage fitting in her palm", held up in her hand beside her face. Not "dangling by its padlock" (a lattice ball on a chain at the Undercroft desk), and keep chains and other steel out of the shot. **Not for the viewer wearing one** (those come later, with their own LoRA). Lying on a table is untested. |
| `undrft_krea2_000001500:1` | **Seo's trampling**, from flat on the floor (`~/code/prive/loras/pov-stepped-on`, step 1500; read its README). Trigger `undrft underfoot POV`. Write it in the caption order: `An undrft underfoot POV photo taken lying flat on <floor> with the camera pointing straight up at <ceiling or sky>, as <the sole, its material and colour> stomps straight down toward the camera`, then her in words, the standing-stomp sentence from the README, and only the ceiling or sky "directly overhead". No walls or furniture: they sit her down. Close her clothes at the hips (the breeches do). Goes in the base, with her own LoRA as a pass on her top half only. Used in TRAMPLE and RIGHTS. Trained on portrait strips: widescreen is untested (2026-11-02). |
| `pvotk7_krea2_000002000:0.9` | **spanking, from across something**, POV (`~/code/prive/loras/pov-otk-get-spanked`, step 2000; read its README). Trigger `pvotk7 POV over-the-knee`. Write it in the caption order. Trained only on a lap (the Sheriff's couch), but a hood in place of the seat and a standing woman hold up (Voss's hood; her art lessons have the details). In the base, with her LoRA as a pass. Watch for his head coming into frame. An exception to framing rules 2, 6 and 7, like `pvarst7`. |
| `"Krea2_BDSM Latex-Leather Megapack_V2E09:1"` | optional, for heavier BDSM gear |
| `"Krea 2 - Strapon Dildo:1"` | strap-on, POV |
| `"R2Y1DH5FQY41BT1Y6W67QWP730.nizLuQb9:0.5"` | facesitting, from under her looking up: she faces the lens and looks down at it |
| `femdom_handjob_krea2_epoch_20:1` | her hand on him: a handjob or hand teasing she gives the player, POV from his eyes (the one exception to framing rule 1) |

Not for this universe: the old facesitting LoRA (not POV), both chain-cuff LoRAs
(`SA86RN444WSD83T4QX4PYS3P80`, the "clejuso" cuffs, retired 2026-10-26 for the hinged ones, and
`Krea2_Metal Cuffs_V6E8`).

The author's LoRAs are used at their recommended 0.9 (`ashby7`, `hngcf5`, `pvcg5`); the others
at 1.

**One steel LoRA per image.** The cuffs (`hngcf5`), the held cage (`mtlcg7d`) and the worn cage
(`pvcg5`) are all polished steel and blur into each other when combined; pick the one the image
is about. Use each the way it was trained: the cuffs gripped closed in her fist ("one rigid
piece of steel about the length of her hand and wrist"), not pinned, clipped on or worked, and
not "dangling", which hung them from a chain (Ashby's arrest, 2026-10-26); the held cage up in
her palm with her arm extended toward the lens, as in the LoRA's showcase prompts.

**LoRA mix: with `ashby7`, the prop LoRA goes up, not Ashby down.** `ashby7` was trained twice
as hard as the prop LoRAs (lr 3e-4 over 1200 steps against 1.5e-4 for `mtlcg7d` and `hngcf5`,
all rank 32), and it knows props of its own: chain cuffs (source 33). Stacked at similar weights,
she wins and the prop comes out wrong. Lowering her to 0.7 didn't fix the cage; the author's
retest did: `ashby7` at 1 with `mtlcg7d` at **2** gave a hand-sized cage (DEAL TERMS, 2026-10-26).

| Mix | Weights | Status |
|---|---|---|
| `ashby7` + `mtlcg7d` (held cage) | 1 + 2 | confirmed (DEAL TERMS) |
| `ashby7` + `hngcf5` (cuffs) | 0.8 + 0.9 (arrest), 0.9 + 0.9 (PROMISE) | arrest drew a chain at 0.9 + 0.9; try 1 + 1.5–2 if it persists |
| `ashby7` + `pvcg5` (worn cage) | 0.9 + 0.9 | no complaints yet |
| `ashby7` + `pvprsn7` (Undercroft POV) | 0.8 + 1 | confirmed (TERMS, APPEAL, PROMISE, CLIMB, 2026-10-31): no cuffs on her wrists, no locs on him. All four poses held; "seated on the cot edge" tends to come out leaning back with legs out, which still reads |
| `ashby7` + `HandgagPOV` / `femdom_handjob` | 0.9 + 1 | fine |
| `ashby7` + facesitting `R2Y1…` | 0.9 + **0.5** | the act LoRA goes *down*: at 0.7 and 1 it undresses her |
| `tfny7` (Anderson) + `hngcf5` | 1 + 1.5 | untested; same training recipe as `ashby7`, so boosted |
| `ferrina` (Giardano) + `pvcg5` / `femdom_handjob` | 0.9 + 0.9 / 0.9 + 1 | untested with `ferrina` (it replaced `DMilfModel7`, which was fine at 1 + 0.9) |
| prop LoRA alone (cards) | 0.9–1 | as the README says |

A steel prop LoRA fights the character LoRA; an act LoRA trained on nude bodies fights her
clothes. So a prop LoRA goes up next to `ashby7`, and an act LoRA comes down.

**Hold the cage level with her face, never toward the lens**: her arm extended at the camera made
it head-sized by perspective (DEAL TERMS). Use the caption wording "held upright beside her
shoulder", with the camera two paces back.

**Facesitting and handjobs always use their LoRA.** Every result, card or ending image that
shows facesitting carries `"R2Y1DH5FQY41BT1Y6W67QWP730.nizLuQb9:0.5"`, shot from under her
looking up (Ashby's OFFER at Cell Three is the reference). Every image of her hand on him, a
handjob or hand teasing, carries `femdom_handjob_krea2_epoch_20:1`, POV looking down (the
Signora's FINISH in the back room and Ashby's ASK at Cell Three). Neither act is shot without its LoRA. One exception: Voss's
`voss-track-face`, where the facesitting LoRA kept drawing her bare, so the frame stops at her belt and the prose carries the act.

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
- **The one exception: achievement art** (`achievements/*.yaml`) is third person, as the engine
  requires. Eli is in frame, seen from a distance, with the scene in the right two-thirds and
  the left third quiet. Every subject writes him out in full where he enters (a broad-shouldered,
  athletic white man of thirty-two with lightly tanned skin, tousled wavy brown hair, a strong
  square jaw, light stubble and round thin wire-rimmed glasses) plus his outfit: the flannel
  look, or "a loose, bright orange county inmate jumpsuit with the sleeves pushed up, barefoot"
  in the Undercroft. He then gets his own pass with `jack:1` before the woman's (ADR 0052), so
  her LoRA never touches him. Make each image a reward:
  the peak of the storyline, with expression and humiliation, not a polite two-shot.
- **In those two-person shots the woman's kit is written out too**: the canonical uniform
  sentence (indoor or patrol), her hands, nails, hair and hat. A second person in frame, or a
  second LoRA, dilutes what the trigger alone would draw, so don't rely on the LoRA's default
  uniform there.

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

These were learned under the retro-80s style LoRA, which is gone now; recheck each against the
new renders before relying on it.

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
  (renders a dull powder blue). Muted looks (canon, no LoRA) turned the tie navy or black; the
  retro-80s LoRA made it pop. Without it, watch the azure on women without their own LoRA;
  Ashby's LoRA was trained on the vivid azure.
- **Stone is named as masonry.** "Limestone crypt" alone renders raw cave rock under retro-80s.
  Every subject in the church says "smooth dressed limestone ashlar blocks laid in straight
  courses with thin mortar joints" and "a whitewashed pointed vault".
- **The Undercroft is underground.** The model adds tall daylight windows to any arched
  corridor; write "windowless, underground, lit only by caged bulbs". The one exception is the
  small grated window at street level in the guard post.
- **Ashby's desk is dark oak.** A gray steel desk on gray flagstones read as part of the floor,
  and the yellow line painted across the floor ran over its top (2026-10-26). Write "an old
  dark-stained oak desk on four turned legs", keep the yellow line on the floor "a few paces from
  the camera", and leave the line out when the desk is close.
- **A POV hand-over-mouth needs nothing under the camera.** From "sitting height on a steel cot"
  the mattress filled the foreground and the viewer's head seemed to lie on it (NOISE). Put the
  back of the viewer's head against the wall and her free hand on the wall beside the lens.
- **Through the bars.** To put her outside a cell, write "photographed through the bars": the
  bars in the extreme foreground, her face in the gap between two of them. If the cell's props
  (cot, wall ring) are in the near foreground, the model puts her inside the cell with them.
- **The holding cage: shoot through the open door, not the mesh** (Anderson). Through-the-mesh
  shots failed five times (2026-10-26/27): strips of fence read as an open gate; a mesh screen
  with no frame floated like a "magic fence"; at an angle it covered half the frame; her fingers
  in the mesh pulled the fence beside her; and at one or four paces she split into two copies,
  one in front of the mesh and one behind it. Chain-link isn't bars. What works (ANSWER, the
  location image): "looking out through its open door: the door's galvanized steel pipe frame and
  chain-link mesh stand soft and out of focus at the left and right edges of the frame", her in
  or just beyond the doorway, one or two paces away.
- **Folded arms hold nothing.** "Arms folded, a manila arrest form in her left hand" gave her a
  third hand for the papers. Folded arms get "both bare hands tucked against her sides, nothing
  in them".
- **The hand-over-mouth in the holding cage** sits the viewer's head against the chain-link
  wall, as at NOISE: from "on a steel bench" the bench filled the foreground under her arm.
- **A raised hand near the lens becomes the viewer's arm.** Her pointing hand at the cruiser
  window rendered as an arm reaching in from the bottom edge. Keep her hands on herself or the
  car, and write "Nothing of the viewer is in frame: no hands, no arms."
- **"Cap" means a hat.** "The black cap of a marker" put a blue baseball cap on Anderson. Say
  "lid", and "bare-headed".
- **Inside the boot, not the sole.** Never write "sole" or "heel" in a shot of the boot's inside:
  "held by the heel" and even "the sole points away, out of sight" drew a big sole at the lens.
  Name only "the open top… the dark hollow inside lined with worn tan leather", and name her
  breeches, or the boot she took off leaves her bare-legged.
- **Close-ups lose tfny7.** Leaning in at arm's length washed out her two-tone hair, eye color
  and lipstick. Keep her a pace back, chest up.
- **Name tfny7's long sleeves** when her arms are bare of the bomber: she rendered short sleeves
  in the bullpen. Leave background staff out: women in tan shirts became copies of her, and
  male officers don't fit Graystone. Write "the empty nave… rows of unoccupied desks".
- **Cuff words put cuffs on her.** Any "handcuff" or "cuffs" in a subject with her in it
  (even "a handcuff case on her belt") renders as a cuff or a steel bangle on her own wrist, or
  cuffs in her hand instead of the prop you asked for. Her appearance block carries no cuffs.
  Mention cuffs **only when they're the centerpiece** (her arrests, PROMISE, the Handcuffs and
  Prison Chains cards), with the hinged-handcuffs LoRA, or on his wrists with `pvprsn7` in the
  Undercroft. The Undercroft pegboard holds leg irons and chains, no cuffs. In general, props in her block land on her body.
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
- **The old chastity LoRA filled an empty cage** (`chastity_000005800:1`, retired for the steel
  `mtlcg7` cage). When she held the cage it rendered with anatomy inside unless written as "empty,
  unlocked … its curved bars open and hollow", and hooked on a finger at chest height it still
  filled (Juno's cage photo); hanging it by her face, "dangling by a small open padlock … the
  light shining straight through it", worked. Keep that wording with the `mtlcg7` LoRA until its
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
- **The facesitting LoRA undresses her.** "The crotch … of her tight tan riding breeches" with
  the facesitting LoRA drew bare genitals through the breeches (OFFER, 2026-10-26), and so did
  "fully clothed … opaque twill" with the fly and seam named. With the LoRA at 0.7 and "one smooth
  unbroken expanse of khaki cloth from her belt to her knees" (no fly or seam), a hint remained.
  Being tried: the same wording at 0.5.
- **Gestures through the bars clip.** A pen pointed at the lens from behind the cell door went
  through a bar (CALL). Keep her a few paces back, "standing clear of the bars", hands on her own
  body or a prop held against her chest.
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
- **Nothing in the phone's photo may run off its edge.** "Socks run up out of the top of the
  photograph" (DM boots) continued her legs outside the phone, as legs in front of the
  viewer's lap, and the photo read as Juno holding her own phone. A mirror selfie "glasses to
  knees" put her penis outside the phone (DM bulge). Say where the photograph's edge cuts her,
  "inside the screen", keep a mirror's frame whole inside the photo, and name the bottom edge of
  the frame as the gray wall between the wrists. That still leaked (second render of both): the
  space behind a held phone is where a lap goes. Only chest-up photos survive the held-phone shot
  (DM selfie, video). Being tried for anything lower: the phone lying flat on a walnut table,
  shot from directly above, wood grain to every edge, his one hand resting beside it. Worked
  (boots, socks). The held phone leaked even a chest-up bubble-tea selfie (her body under the
  phone, her nails on his hands), so use the table for every new DM.
- **Chastity cage LoRAs:** the stainless steel cage (`mtlcg7d_krea2_000001250:1`, trigger
  "mtlcg7", the `d` variant) replaced the pink plastic one (`pnkcg_krea2_000000750:1`, retired). It is for a woman
  holding the empty cage, POV; not for a cage on the viewer. Tried and dropped before:
  `0EK4J7JPM6F67BN8VC86C3DFG0:1` (a flat metal cap cage) and `30QCFXF2SWVGFPBY9SE3M51VK0` (it put
  a filled cage on the viewer, below the phone).
- **"Flat on the back, looking up" came out eye level** (without a LoRA; `undrft` is the answer now, see
  its row). Seo's TRAMPLE and RIGHTS renders sat her
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
  cock at the bottom edge, and once her socks and clothes on his own legs. Standing at arm's
  length fixed the lap, but the room behind the phone then grew a second her (or her shoes, or a
  filled cage) out of the photo's subject. What works: "standing eye height, the camera level", the
  phone **turned sideways in landscape**, held close in both hands from the bottom corners, filling
  most of the frame with "only a thin margin of plain charcoal-gray wall" around it. Her content
  is shot **in her bedroom at home** (pastel posters, a teal LED strip, black and teal sheets, a
  gaming desk), never the library.
- **Her nails go on his hands.** With her painted nails in the photo on the phone, the hands
  holding it got long painted nails. Leave her nail color out of anything his hands are in,
  and give his hand "broad knuckles, short, bare, unpainted nails cut straight across".
- **An explicit LoRA undresses her.** Juno's first LoRA (`KreaTransBabe`, retired for `jovessa`)
  was trained on explicit material: even with her top written in, her own photos came out
  topless or nude, and her page's two-column layout grew a big topless cover photo. `jovessa` was
  trained on clothed photos only, so this is untested with it; her page still uses "a single
  centered column" and a small round avatar.
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
55 Graystone Heights a week before the department notices him. A white man of 32,
broad-shouldered and athletic, lightly tanned skin, tousled wavy brown hair, a strong square
jaw, light stubble, round thin wire-rimmed glasses; a faded red and gray plaid flannel over a
charcoal T-shirt, worn work jeans, scuffed brown work boots, a black canvas laptop bag.
LoRA: `jack:1` ("Jack" from the Civitai collection *Original Characters*, no trigger word), since
2026-11-01: his face, hair and build come from it; his outfits and glasses stay his. Wherever he
is in frame in third person he gets his own pass with it, before the woman's; alone in frame
(his hero card), it goes in the base. Write his look out in the base as above all the same.
POV block: *a man's bare hands and forearms with short unpolished nails, entering from the
bottom edge of the frame.*

## Graystone County Sheriff's Department

### Uniform (canonical, verbatim in every police-art subject)

**Indoors:**

She wears the Graystone County Sheriff's uniform: a crisp, pressed tan long-sleeved uniform shirt of heavy cotton twill with a pointed collar, a full button-front placket, two buttoned flap chest pockets piped in vivid azure blue, shoulder epaulets edged in vivid azure blue, an embroidered vivid azure blue and gold patch on each upper sleeve and a polished gold six-point star badge pinned over the left pocket; a vivid, saturated azure blue necktie with a small gold tie bar; tan riding breeches with an vivid azure blue stripe down the outer seam; a black leather duty belt with a polished brass buckle; and stiff, structured, mirror-polished black leather thigh-high riding boots with rigid straight shafts and low, flat stacked-leather riding heels, fitted tight to the leg, pulled up over the breeches to mid-thigh; her head is bare.

**Outdoors** (a different sentence: the bomber covers the shirt, so only its collar and tie show):

She wears the Graystone County Sheriff's patrol uniform: a dark forest-green bomber jacket of smooth nylon twill with ribbed knit sleeve bands, collar band and waistband, zipped up to the middle of her chest, worn with both arms in its sleeves and both shoulders covered, a single polished gold six-point star badge pinned on its left chest and an embroidered vivid azure blue and gold patch on each upper sleeve[, rank]; above the zipper, the pointed collar of a crisp, pressed tan uniform shirt and the knot of a vivid, saturated azure blue necktie with a small gold tie bar; a black leather duty belt with a polished brass buckle at her waist below the jacket's hem; tan riding breeches with a vivid azure blue stripe down the outer seam; and stiff, structured, mirror-polished black leather thigh-high riding boots with rigid straight shafts and low, flat stacked-leather riding heels, fitted tight to the leg, pulled up over the breeches to mid-thigh. On her head, worn level over her eyes, sits a stiff campaign hat of the kind state troopers and drill instructors wear, in light khaki tan felt the same color as her shirt, with a wide flat brim, a pinched four-dent crown and a vivid azure blue hatband.

Outdoors the rank goes on the bomber sleeves, in place of "[, rank]": sergeant — ", with three
vivid azure blue chevrons beneath the patch on each sleeve". **Never drop the breeches**, however
tight the frame: write "tan riding breeches, the same khaki tan as her shirt, with a vivid azure
blue stripe down the outer seam". Drop only the boots when the frame doesn't reach them. Name each hand "out of the green bomber sleeve" when it acts. The
hat is a separate sentence, in shirt-tan, never next to the green; a deputy may go bareheaded
as her personal look (Anderson).

**"Cuffs" means handcuffs only.** The bomber's sleeve ends are "ribbed knit sleeve bands": "ribbed
knit cuffs" put a steel cuff on the deputy's own wrist in a handcuffing shot (Mara's arrest of
Britt, 2026-11-01). In any cuffing prompt, name whose wrist each cuff is on ("locked on the blonde
woman's wrist"), never "her" for either woman.

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
LoRA: `lorbrandt_krea2_000001200:1`, the author's own (`~/code/prive/loras/char-laura-brandt`),
step 1200 (fallback 800). Rank: sheriff (the dress uniform: a dark olive-green jacket). Her look
with it: about fifty, long copper-auburn waves with a few silver strands at the temples, bright
blue eyes, fair freckled skin.

Appearance block, in her LoRA's caption words: *lorbrandt woman in her uniform* (jacket buttoned,
the way she wears it at her desk), or *lorbrandt woman in her uniform with the jacket worn open
over the tan shirt*. No face, hair, age or uniform sentence: the LoRA carries all of it. Keep
prompts as short as her captions: trigger, pose, framing, expression, setting, light. The
trigger prints "BRANDT" on signs, car doors and jackets: give every sign its own text or call it
unlabeled. Outdoors, name the olive jacket, tan shirt and blue tie.

When she catches you (`sheriff-caught`) she is strict and scolding, and the look alone tells you you're in trouble.
She brings up your mother in Dayton there: the player's mother lives in Dayton.

Character: fifty, Graystone born, twelve years with the state police before the Mayor asked her
home to rebuild the department from nothing. She hired every woman in it. Warm, easy, the
pleasant, inviting smile of someone who has never needed to raise her voice, because everyone
in the building raises theirs for her. Remembers everybody's name, mother and middle name. The
smile doesn't change when the news does; that's how people learn to be afraid of it. Calls men
"hon".

Off duty doesn't exist; she wears the dress jacket at her desk, closed, all day.

Methods: **old-fashioned correction, delivered warmly.** Anyone caught where he shouldn't be in her
building comes to her, whoever caught him. She bends him over her knees on the Chesterfield with the oval
hairbrush from the second drawer on the left (hard; she doesn't believe in the other kind), stands him naked
in the corner while she works, or sets him a hundred lines and grades them in red pencil (C-plus; she keeps
them). She talks all through it, about him, in the same voice.

### The front desk

**Niamh Doyle** (*name is a proposal*) — the department's office manager, at the reception
desk inside the church doors. Civilian staff: she doesn't patrol, doesn't carry, and runs the
building. She's the one who sends the emails with the smiley faces.
LoRA: `nivdoyle_krea2_000001200:1`, the author's own (`~/code/prive/loras/char-niamh-doyle`),
step 1200 (at 1400 she loses the glasses). Her look with it: copper-ginger waves over her left
shoulder, green eyes, freckles, dark red lips, and **black rectangular glasses**, now part of
her look.

Appearance block, in her LoRA's caption words: *nivdoyle woman in her uniform*. No face, hair,
glasses, makeup or uniform sentence: the LoRA carries all of it, including the civilian uniform
(tan shirt with azure trim, azure tie with gold tie bar, tan pencil skirt, sheer black stockings,
black patent stilettos; no badge, no duty belt). Describe only what the shot is about, the way
her tie is the subject of the bullpen detail shot. Keep prompts as short as her captions:
trigger, pose, framing, expression, setting, light. Her dataset is all indoors (counters,
offices, cells, stone walls): if she ever goes outside, write "her tan uniform shirt with a blue
tie", because outside a police building "her uniform" drifts to a blue police shirt. Like the
others, "a woman in glasses at a police reception desk" alone draws her.

Character: twenty-seven, from Melbourne by way of a Cork grandmother, and nobody in Graystone has
worked out how she ended up here. She has an accent people drive across the county to hear and
uses it like a key. Bright, quick, flirts like breathing and means about half of it. Nothing
gets past her desk she hasn't decided to let past: visitors sign in, contractors show a badge,
and everybody else waits on the bench until she's finished her tea. Calls men "love".

Methods: **warmth, praise and permission.** She rewards a man in public: a running commentary
on how good he is, to whoever's listening. Her uniform is her vanity; a man who notices it gets
to touch it, with his hands and his words, never his mouth, and only because she said so. She
escorts contractors in and out herself. Standing with her is the card *Niamh's Good Side*.

Distinguishing her from Miss Carrow, the other ginger: Niamh's hair is swept over one shoulder, her black glasses,
her lipstick dark red, the uniform shirt and tie; Carrow's hair is loose on both shoulders, her
lipstick wine, the charcoal suit.

### The Undercroft

**Sergeant Monique "Ash" Ashby** (*name is a proposal*) — keeper of the Undercroft.
LoRA: `ashby7_krea2_000001200:0.9`, the author's own (`~/code/prive/loras/char-monique-ashby`),
since 2026-10-26; it replaced `KreaEbonyBabe1`. It carries her face, build and both uniforms.

Appearance block (short, because her LoRA carries the rest), written where she enters the
picture: *ashby7 woman in her sheriff's uniform, tan with an azure tie, her long black locs
gathered at the nape,* — outdoors, *ashby7 woman in her sheriff's uniform with a green bomber
jacket and campaign hat, …*. "Locs", not "dreadlocks": the LoRA's word. **No kit sentence**: the
LoRA draws the uniform. The long kit sentence (trim, chevrons, star, black gloves, black belt,
breeches) turned her shirt black at the cell door, where black iron and black leather outnumbered
the tan (2026-10-26); "tan with an azure tie" is the one color anchor. Name a piece of kit only
when the shot is about it (the tie in ADMIRE, the boot in KNEEL, the breeches in OFFER).

Detail shots (a boot, her tie) name her as "the boot of ashby7 woman in her sheriff's uniform"
and say where the frame ends. Known leak: with her LoRA loaded, "sheriff's uniform" alone draws
her, so keep it to one woman per frame as always.

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
LoRA: `tfny7_krea2_000000800:1`, the author's own (`~/code/prive/loras/char-tiffany-anderson`),
since 2026-10-26; it replaced `DGirlsModel14`. It carries her face, hair, nails, build and both
uniforms. Rank: deputy (no chevrons).

Patrol look (her outdoor uniform, instead of the canonical outdoor one): **a green bomber
jacket, no campaign hat, bare hands** (no gloves: her black nails are her distinction from
Ashby).

Appearance block, written where she enters the picture, in her LoRA's caption words: *tfny7
woman in her tfny7 uniform* indoors, *tfny7 woman in her tfny7 uniform with a green bomber
jacket* on patrol. No appearance or kit sentence: the LoRA draws both. Keep "out of the green
bomber sleeve" for each bare hand, and name boots, breeches or socks only when the shot is
about them. Detail shots name her as "worn on the legs of tfny7 woman in her tfny7 uniform" or
"the bare hand of tfny7 woman". Known faults from her LoRA's run: `tfny7` can print as text on
a shirt or car (fewest at step 800, the one in use), "sheriff's uniform" alone draws her, and
the LoRA was trained like Ashby's (lr 3e-4), so a steel prop LoRA beside it needs a boost (her
arrest has the cuffs at 1.5, untested).

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
LoRA: `sorenji_krea2_000001400:1`, the author's own (`~/code/prive/loras/char-seo-min-ji`),
step 1400. Rank: deputy (no chevrons). Her look changed with it (approved for the LoRA): a
**dusty-pink bob** to the collar with dark roots, no braid. Never write the braid or "violet".

Appearance block, written where she enters the picture, in her LoRA's caption words: *sorenji
woman in her uniform* indoors, *sorenji woman in her uniform with a green bomber jacket*
outdoors. No face, hair, makeup or uniform sentence: the LoRA carries all of it, and describing
uniform pieces overrides it (as with tfny7). The LoRA brings the long sleeves and her aviators
itself (on the placket indoors, often on her nose outdoors): never name a second pair, or she
holds one and wears another. Outdoors, when the scene needs her eyes, write "lowering her aviator
sunglasses down her nose" (her caption words). Keep prompts as short as her captions: trigger,
pose, framing, expression, setting, light. Long, detailed prompts drew short sleeves, a
floating bag and her clubbing shoulder bag. If the bob comes out red or dark, add "with her
dusty-pink bob" after the trigger. Boots only in boot shots (TRAMPLE, RIGHTS). Expressions keep "dark eyes", "berry-pink lips". The
trigger reads as a name, not text: her run never printed it. Palette word for her hair: "dusty
pink". Like the others, "sheriff's uniform" alone draws her.

Character: twenty-nine, born in Incheon, a harbor town, and the only deputy who asked for the
docks. Eccentric, and attractive in a way she doesn't seem to notice. She watches everything
and comments on the wrong part of it: the gulls (she has named them), the barge numbers (she
keeps a list), the way a man stands (she'll tell him which foot he's lying on). Talks to the
river. Hums. Polite, cheerful, impossible to read, and never once surprised. Gives men a
nickname for whatever she noticed first, and uses it until she learns their name.

Methods: **protocol, the floor and the glove.** She sees a wanted man before he sees her, puts
him face down by the book, every instruction said once in that small soft voice, and reads him
the Graystone advisement word for word while she stands on him. Her heat is **CFNM**: he is
stripped at booking and stays naked until she hands his clothes back on the church steps, one
piece at a time, in front of the square; she stays buttoned to the collar and writes everything
down. With her body: **trampling** (her whole weight, walked up him, the sole over his face)
and **light anal play** — the gloved cavity search that turns into milking him, logged in the
notebook. She never raises her voice and never once looks surprised. A man who gives her
evidence gets a page in that notebook instead: her snitch, later her informant.

### Patrol: the highway

**Deputy Mara Voss** — patrols the highway out of town, from a gravel turnout.
LoRA: `mrvx7_krea2_000001200:0.9`, the author's own (`~/code/prive/loras/char-mara-voss`), step
1200. Rank: deputy (no chevrons). Her head is bare.

Appearance block, in her LoRA's caption words: *mrvx7 woman in her patrol jacket uniform*, plus her
hair, hoops, liner and lips spelled out, and **every piece of kit spelled out**: the uniform phrases
never fully bound (the shirt came out blue or forest green). Her bomber has "ribbed knit sleeve
bands", never "cuffs".

Character: twenty-two, a bit glamour, a bit classic rockabilly: fresh lipstick on the shoulder of a
county highway. Calls men "honey", "sugar", "sweetheart", "sweet pea", and means none of it. The
sweetness is real manners on a surprisingly mean sadist: she hurts men because she likes it, and the
smile doesn't change when she does. Sets the rates and makes up the speed.

Methods: **spanking, ballbusting and punishments like them.** She leaves a man too sore to sit, or on
his knees holding his crotch and begging for mercy, and she makes him say it again. Her face in art is
sweet and delighted at the car window, and cold and strict while she punishes.

Her shade is a discontinued cherry red, ninety dollars a tube. She keeps the empties, in order, in her gym
locker. She's the one woman in the county who doesn't know the GrayBloods are selling it to her.

Art lesson (the road, 2026-11-04): `undrft` 0.7 with `pvotk7` 0.4 does hold the look down his own body at her
boot, but it sat her down on the gravel when her body was named behind the boot (`voss-rights`). `pvotk7` at 0.2 and
only her two boots, both shafts leaving the top of the frame, fixed that. With his boots nearest the lens, the rest of
him drew itself lying beyond them. Being tried: his hips nearest the lens and his feet far off. A license in her teeth
reads badly, so leave it to the prose. Naming the whole patrol car in a shot of its hood draws a second car. On
`voss-track-face`, Ashby's wording and a last no-LoRA box pass still left her bare at the bottom edge. What worked: no
facesitting LoRA, and the frame stops at her belt.

Art lesson (props, 2026-11-04): "blood-red" draws blood. The crown on `grayblood-runner` dripped onto a spattered mat,
and `reds-package` grew blood on the seat, so say "faded brick red" or leave it out. On `sounds-like-a-seventy-one`, the patrol
livery moved onto the sedan beside it: keep the cruiser small and far back, and spell out the sedan's plain paint. On
`second-place`, the steam and raised hood went to the black car: say which hood is up and which is shut. Also on
`sounds-like-a-seventy-one`, her tie and sleeve patches went missing: a pass redraws her clothes too, so spell out the
whole kit in the pass as well as the base.

Art lesson (the hood, 2026-11-03): `pvotk7` holds up with a hood for a lap and her standing, but her
"tan riding breeches" went on his thigh, with a piece of her boot at his knee, and "big, sweet" came
out as a laugh and a wave. To keep a good composition, leave the base's words alone and repair with
passes (her face; his leg, no LoRA, at a high denoise). A face pass at 0.7 with her hair in its box and
words drew curls over her face, so keep it to the face at about 0.5. The segment label "tan trousers and
black boot" gave an empty mask, and the pass silently changed nothing; ComfyUI's mask preview shows this.
A long `find` with "leaving out..." boxed his whole body, and a box-only pass redrew all of it, so ask for
one thing and keep the outline.
After four renders patching that leg, the base was redone: when what's wrong is in the base, change the
base. It frames her from the hips up behind the hood, with no breeches or boots to land on him, and has
her strict from the start.

### Café Linde

**Francine Giardano** ("Signora Giardano") — owner of Café Linde, behind her own counter.
LoRA: `ferrina_krea2_000001200:1`, the author's own (`~/code/prive/loras/char-francine-giardano`),
step 1200 (the strongest likeness; no softer checkpoint was kept). Her look with it: forty,
glossy shoulder-length dark waves, green eyes, red lipstick and red nails, gold hoops, and thick
black rectangular glasses.

Appearance block, in her LoRA's caption words: *ferrina woman in her red work blouse and black
apron, wearing her thick black rectangular glasses*. The outfit phrase covers the red satin
blouse, black bib apron, black trousers and black patent stilettos; in full-length shots add
*black trousers and black patent stiletto pumps*. Name the glasses every time: the bare trigger
never drew them. No face, hair or outfit sentence otherwise: the LoRA carries all of it. The
trigger prints "FERRINA" on blank clothing: say her apron is plain, with no lettering, and give
any other blank top or sign its own text. With a concept LoRA in the same image (the handjob and
`pvcg5` shots), take hers down a notch, to 0.9.

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
warehouses at the docks. Red is their color. **Every GrayBlood is a woman, for good, in prose and in art.**
No men in their warehouses, not even out of focus in the background. Keep backgrounds empty rather than naming
figures: a named crew or card game draws men. Keisha and the card players are the women in the room.

**Red** (Shanice "Red" Dupree; *name is a proposal*) — a GrayBlood, holding up the wall of a
dockside warehouse.
LoRA: `shndr7_krea2_000001200:1`, the author's own (`~/code/prive/loras/char-shanice-dupree`),
step 1200, the only step that gets her whole signature outfit right (fallback 800). Her look
with it: twenty-one, smooth dark brown skin, long straight black hair loose down her back with
one thin braid from her temple, pale blue-gray eyes and small gold hoops.

Appearance block, in her LoRA's caption words: *shndr7 woman in her red puffer jacket, hanging
open over a fitted black top, with light-wash ripped jeans*; when her feet are in frame, add *and
scuffed white high-top sneakers*. Spell out the jeans: earlier steps drew them black. No face or
hair sentence: the LoRA carries all of it. Name her expression in every prompt; her dataset leans
stern, and a smile needs saying. Her other trained looks, written out in full: a red zip track
jacket with white side stripes, olive cargos, a black denim jacket, a cream tee and jeans, a gray
hoodie and joggers. Keep vertical signs out of her shots or call them plain: the trigger may print
itself as "…7" lettering on neon.

Character: twenty-one (the bible's floor; the author said twenty), born on the river side of
town, a GrayBlood since she was old enough to carry. Loud, smug, in your face: the kind of
confidence that has never once been told no and made it stick. She talks over people, laughs at
her own jokes because they're good, and stands closer than she has to. Thinks the department is
a joke that hasn't been told to her yet. Calls men "lil bro".

Inside the warehouse (*GrayBlood Runner*) she takes respect on bare skin, has her sneakers cleaned by tongue,
and gives a handjob the way she does everything, loud and with commentary, until he says "I ain't no cop" right.

Methods: **mockery, pat-downs and the hustle.** Every man is a narc until he proves otherwise,
and the proof is money he hustled himself and hands her (*Red's Errand*, then *GrayBlood Rep*).
She frisks men against the warehouse wall, reads their IDs out loud, and makes them say things
back until they say them right. Long white nails (prose and close-ups only; not in her block).

## Independents

**Britt Dekker** — a streetracer and discreet courier, twenty-three, at the Starlite with her black
muscle car. Takes delivery of discontinued cherry-red lipstick from the GrayBloods, and sells it on to Voss, who
has no idea whose it is. Says very little, and names men after their cars: the player is "Sedan". Flattery
gets nothing; knowing her car gets a nod.
LoRA: `zbltk7_krea2_000001400:0.9`, the author's own (`~/code/prive/loras/char-britt-dekker`), step
1400.

Appearance block, in her LoRA's caption words: *zbltk7 woman in her pink hoodie*, plus "long loose
wavy honey-blonde hair", "subtle and natural" makeup, and when her legs show, "lightly torn straight
blue jeans and off-white low-top sneakers". The car is opt-in: name it as "a gleaming black
late-1960s American muscle car".

## The library

**Miss Imogen Carrow** (*name is a proposal*) — head librarian of the Carnegie library, behind
the circulation desk in the reading room. One of the town's disciplinarians, not police.
LoRA: `imcrw7_krea2_000001200:1`, the author's own (`~/code/prive/loras/char-imogen-carrow`),
step 1200 (fallback 800, which keeps the gray suit right from the short phrase). Her look with
it: thirty-eight, long loose auburn waves with a centre part, bright green eyes, a few freckles,
deep wine-red lipstick and a slim gold watch.

Appearance block, in her LoRA's caption words: *imcrw7 woman in her gray skirt suit, the fitted
charcoal jacket buttoned once at the waist over a cream silk blouse open at the collar, her
throat bare, no tie, a slim gold watch on her left wrist*. The suit phrase covers the jacket,
blouse and pencil skirt; in full-length shots add *sheer black stockings and black patent
stiletto pumps*. Step 1200 mixes the neckties of her other suits into the gray one, so the
open collar and bare throat are always written out. No face, hair or makeup sentence: the LoRA
carries all of it. Keep prompts as short as her captions: trigger, pose, framing, expression,
setting, light. Her hair is loose in every training image; an updo would need spelling out and
may resist. She and Niamh are both green-eyed redheads: in a frame with both, name each one's
trigger and place.

The heels are her signature: in prose you hear her before you see her, a sharp click on the oak
boards as she comes toward you, or as she walks round behind you. The cleavage is the blouse's
open collar inside a closed jacket: never an unbuttoned jacket, a lace edge or a bare chest. Her
hair stays loose and long; a bun, a cardigan, pearls or glasses on a chain would age her twenty
years (see the top of this file).

Character: thirty-eight, from somewhere outside Bath, a governess's training and a librarian's
degree, here eleven years. Nobody in Graystone knows why she came and nobody has asked twice.
Strict in the old way: silence in the reading room, books handled with clean hands, fines paid
in full, and "young man" for any man under sixty. Polite to the point of cruelty. She keeps the
library the way the Sergeant keeps the Undercroft, and they have tea. She knows who
reshelves her true crime into gardening, and has decided to let it run, for now.

Methods: *to be decided* (a disciplinarian; her storyline comes later).

**Juno Vance** (`@rootkitty`) — at the corner table of the Carnegie library's computer corner,
on her own laptop. Not police, not anybody's employee.
LoRA: `jovessa_krea2_000001200:1`, the author's own (`~/code/prive/loras/char-juno-vance`),
step 1200 (800 keeps the glasses and choker more often but leaks her crop top into other
outfits). Her look: a trans woman of twenty-three, petite and slim, pale freckled skin,
brown eyes, dense black and deep teal hair swept to one side, shaved short at one temple and
falling in long thick waves over the other shoulder, black rectangular glasses, a small silver
septum ring, a black choker with a silver O-ring and a small silver ear cuff.

Appearance block, in her LoRA's caption words: *jovessa woman in her usual black outfit* (a
black ribbed crop tank, an open oversized black bomber jacket slipping off her shoulders, black
drawstring joggers and worn black-and-white low-top canvas sneakers), plus *wearing her black
rectangular glasses and a black ring choker*: the bare trigger dropped both once at step 1200.
No face, hair or outfit sentence otherwise: the LoRA carries all of it. Keep prompts as short as
her captions: trigger, pose, framing, expression, setting, light. Outdoors, spell the outfit out
in colors. Her other trained looks: *in her purple cosplay suit*, *in an orange inmate jumpsuit,
barefoot*, and three ordinary outfits written out in full (a faded black graphic T-shirt and
olive cargo shorts; a dark green plaid flannel shirt over a black T-shirt; a sheer black mesh
top and a dark teal pleated midi skirt). The shaved side is on one side only; don't ask for a
mirrored or flipped shot. Her headphones are prose only (none in her dataset).

Her laptop (when it's in frame): *a plain black laptop, the back of its lid covered edge to edge
in small, colorful vinyl stickers of cartoon cats, stars, hearts and lightning bolts, none of them
with any lettering*. "Edge to edge" matters: with a few stickers the model put an Apple logo on
the lid. (Her dataset's laptop is gray; if a render follows it, that's fine.)

**In public she is dressed.** Her nudity belongs to her own photos (the SIMP beats) and to
private scenes later. `jovessa` was trained on 30 clothed photos, full length included, so her
library table shot frames her from the knees up with a sneaker on the other chair. If a render
opens her clothes, frame her from the waist up behind the table edge. Her explicit scenes are
untested with this LoRA.

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
table. Her bulge is shown through her joggers; when she shows more, the frame is on her and
her hand, per the framing rules (his body never).

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
- **The highway** — two lanes through cut corn, driven in the player's own older sedan: the two views
  are POV through his windshield, his bare hands on the wheel. Deputy Voss's cruiser sits in a gravel
  turnout under the cottonwoods.
- **The Starlite** (*name is a proposal*) — a one-story motel of pale painted block beside the highway:
  turquoise doors, orange curtains, a covered walkway, an office at the near end, a gravel lot and a
  dead neon sign of plain red and turquoise tubes.
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
