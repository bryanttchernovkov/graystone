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
3. **Eye contact and one emotion, with the face that shows it**, taken from the prose.
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
- **Props in an appearance block land on her body.** "Steel handcuffs in black leather cases"
  put a cuff on her own wrist; write "a black leather handcuff case on her belt", and put loose
  cuffs in her hands only when the scene uses them.
- **Boots:** "stiff, structured, mirror-polished … with rigid straight shafts fitted tight to the
  leg" stops the slouch. A shot cropped above the knee won't show them; when they matter, frame
  her to the knee or go to a detail shot.
- **The character LoRA holds her face** across every look tested; the appearance block keeps
  hair, build and kit consistent around it.

## The heroes

**POV block** (per hero, verbatim when his hands are in frame).

**Eli Novak** (first hero, *proposal*) — new in town: the county's contract IT man, moved into
a rented half-house a week before the department notices him. A white man of 32, lean, short
dark blond hair, a few days of stubble; flannel over a T-shirt, work jeans, scuffed boots.
POV block: *a pale man's bare hands and forearms with short unpolished nails, entering from
the bottom edge of the frame.*

## Graystone County Sheriff's Department

### Uniform (canonical, verbatim in every police-art subject)

**Indoors:**

She wears the Graystone County Sheriff's uniform: a crisp, pressed tan long-sleeved uniform shirt of heavy cotton twill with a pointed collar, a full button-front placket, two buttoned flap chest pockets piped in vivid azure blue, shoulder epaulets edged in vivid azure blue, an embroidered vivid azure blue and gold patch on each upper sleeve and a polished gold six-point star badge pinned over the left pocket; a vivid, saturated azure blue necktie with a small gold tie bar; tan riding breeches with an vivid azure blue stripe down the outer seam; a black leather duty belt with a polished brass buckle; and stiff, structured, mirror-polished black leather thigh-high riding boots with rigid straight shafts fitted tight to the leg, pulled up over the breeches to mid-thigh; her head is bare.

**Outdoors** (replace "her head is bare" with):

a tan felt campaign hat with a wide flat brim, a pinched four-dent crown and an vivid azure blue hatband, worn level over her eyes; and over the shirt a short dark forest-green uniform jacket with a gold star on the chest, hanging open.

**Rank** goes after the uniform sentence: sergeant — three vivid azure blue chevrons on each upper
sleeve beneath the patch. (Sheriff and other ranks: to be set with their characters.)

### The Undercroft

**Sergeant Monique "Ash" Ashby** (*name is a proposal*) — keeper of the Undercroft.
LoRA: `KreaEbonyBabe1` (trigger `EllieKEB`, added by the loader).

Appearance block: *a Black American woman in her early thirties, tall and athletic with a full, heavy bust, broad straight shoulders and a soldier's posture, smooth dark brown skin, long black dreadlocks gathered at the nape and falling to the middle of her back, a level, unimpressed stare under straight dark brows, black leather duty gloves, a black leather handcuff case on her belt and a ring of heavy iron keys on a steel chain at her hip.*

Character: ex-Army military police, eight years, two of them running a detention facility.
Controlling, clipped, borderline mean, never sadistic. Her whole method is *permission*: a man
in her block doesn't stand, sit, speak, drink or piss without asking, and she decides how he
asks. Cuffs and chains are how she says no without saying it. She loves the uniform — hers is
the sharpest in the department — and she inspects it on others as hard as on herself.
