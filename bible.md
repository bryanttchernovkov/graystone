# Graystone — bible

## Premise

**Graystone** is a fictional Midwest county seat of about thirty thousand people: a limestone
courthouse square, grain elevators by the rail spur, a river with one good bridge, a quarry
that gave the town its name and most of its buildings their color. Strip malls on the bypass,
bars on Front Street, a diner that opens at five. Present day. Nobody here is famous and
everybody knows everybody's truck.

For a decade the town slid: meth on the county roads, break-ins on Main, bar fights that ended
in the river. Then **the Mayor** — a woman who grew up here and came back to run it — took
office on one promise: *it ends*. With the county board behind her she **suspended the
traditional court docket** for misdemeanors and handed enforcement to a rebuilt **Graystone
County Sheriff's Department, staffed entirely by women**. The department doesn't file charges.
It **corrects**: on the spot, on the shoulder of the county road, behind the bar at closing —
or, for anyone who needs longer, with **a short stay in the department's own lockup**, rarely
more than a few days, from which men come out straighter than they went in. Crime is down.
Nobody in Graystone pretends to wonder why.

The department works out of **the old First Church**, a deconsecrated limestone Gothic Revival
church on the square that the county bought for a dollar. The nave is the bullpen; the
lockup is **the Undercroft**, the vaulted crypt beneath it.

**The player is always a man**, and always a newcomer to the department's attention. The first
hero is new in town; more heroes come later, each with his own reasons and his own slots and
dice. A run is the stretch of days in which Graystone decides what to make of him.

## Tone

Grounded small-town texture with R-rated heat written with craft. Think *Justified* or *Mare
of Easttown*: real people, real jobs, real weather, gossip at the diner, a radio that's always
on — and underneath, a department that has made correction personal. The kink lands because
of who is doing it and why: each deputy's methods are her character. Never parody, never
grimdark.

### Voice (rules for every line of prose)

- **Plain and physical.** Say what happens, in the order it happens, with concrete nouns and
  verbs. Sex is written explicitly, in plain words, never in metaphor-fog.
- **One comparison per paragraph, at most**, and only a concrete, in-world one.
- **The wit lives in the women's mouths.** Dry, specific, Midwestern lines — understatement,
  politeness with an edge. Narration stays lean around them.
- **Banned tics:** *unhurried*, *economy*, *exactly* (as emphasis), *which tells you*,
  sentences that comment on the sentence before.
- **No history.** Results are fixed: never assume what he did, holds or knows.
- **The prompt promises the result.** If it turns sexual or punitive, the prompt says so.
- **He is careful, not cringing.** He notices and says yes; the women carry the scene.

## The department

All deputies are women. Corrections are **per deputy**: there is no single doctrine, and a
deputy's preferred methods are part of her cast block and her storylines. What they share is
the frame — no courtroom, no paperwork a man can hide behind, a correction delivered by the
woman who caught him, and the Undercroft for anyone who needs a few days.

**Uniform** (canonical, CHP-inspired, wording locked in `cast.md`): tan long-sleeved uniform
shirt with azure blue details, gold star badge, azure blue necktie, tan riding breeches,
black leather duty belt, polished black thigh-high riding boots. Outdoors: a tan campaign hat
with an azure blue band and a dark green uniform jacket. Formal, distinct, authoritative —
and the boots are the department's signature. The uniform is a fetish object in this universe,
not just a costume.

## The women of Graystone

All adult, all human, **between twenty-one and fifty, all attractive**, and never one body
type: variety of build, skin, bearing and style. Older women are handsome, fit and current —
never styled old. Men may appear in the background at any age; **police are always women**.

Characters are added **storyline by storyline**, each with her own character LoRA and a full
cast block in `cast.md`. Depth over breadth: a named woman has a history in town, a job, a
voice and a reason she does what she does.

The dynamic is **femdom by default**. The department doesn't ask; it expects, and a man in its
orbit understands that the moment he's pulled over. By playing Graystone the player has already
said yes: the drama is never whether he yields, but what yielding costs him and what it earns.

## The kink palette

Delivered by whoever has him in hand — a deputy most of all, but the town has its own women
with their own appetites.

- **Control:** sex; chastity; edging and denial; anal and strap-on sex; imprisonment — the
  Undercroft, a night kept, a few days that were always part of the sentence.
- **Restraint:** cuffs, chains, shackles, bondage; permission rules — nothing without asking.
- **Impact and pain:** spanking; trampling; CBT; ballbusting; **wrestling and painful holds**.
- **Below the knee and the uniform:** foot, shoe and **boot worship**; **uniform worship**;
  **gloves**; the campaign hat as a mark of rank.
- **Breath and weight:** **facesitting**; **gloved hand over the mouth** — smothering kept
  short and controlled.
- **Humiliation:** being made to ask, recite, thank, display; public correction on the square.
- **Finish:** cum eating — when and how she decides.
- **Who holds the leash:** dominant femboys and trans women belong here too.

Suggestion is foreplay, never the whole scene: wherever prose sets a kink on the table, an
action pays it off at full length. Nothing outside this menu is written without amending this
bible first.

## The world's shape

Graystone grows **iteratively, storyline by storyline**: a deputy, a gang, a bar, a case — each
added with its locations, cards and art, not generated in one pass. The first anchor is the
**First Church station** and the **Undercroft** beneath it.

Like Precinct 69, **event scenes are locations**: the shoulder of the county road with a
cruiser behind you, a cell, the back of a patrol car — entered because something moved you
there, always with a way back into the world. **People live at their places**; a rare few may
follow the player as companion cards.

## Rules configuration

**Pending redesign** (agreed: rethink, not a copy of Precinct 69). The current `universe.yaml`
is a provisional scaffold so the trial content validates and renders; nothing in it is final.
Open points: a run spanning several days (the Undercroft holds a man for days), the trackers,
currency, categories and words, and per-hero slots and dice.

## Art direction (canonical for `style.yaml`)

Photorealistic, present-day, shot on film. **Explicit is allowed and kink is shown**: when a
result is sexual or punitive, its art names the act and shows it, using the matching kink LoRA
where one exists (cuffs, chastity, facesitting, strap-on, rope, chains…), with the framing
rules in `cast.md` still guarding the viewer's body. Real bodies, real light, real rooms.
Small-town light: limestone gray, prairie gold, sodium amber, cruiser blue and red.

**The look is locked: the `retro-80s` LoRA at weight 1** (`style.loras`), on the checkpoint plus
each character's LoRA. Chosen over canon_krea2, lumen_blockbuster, cheap-realism and no style
LoRA for its warm color and the way it makes the department's azure pop; the lessons from that
comparison are in `cast.md` ("Prompt lessons").

**Character consistency is a hard rule:** every named woman has a character LoRA, and **every
image she appears in carries it** (`art.loras`), together with her full cast block.

### The camera is the player (hard rule)

- **Every result with the player in it is a first-person point-of-view shot.** Say where the
  camera is: kneeling on flagstone, on a cell cot, standing at a counter.
- **The player is barely in the picture:** at most his bare hands and forearms, described with
  the POV block in `cast.md`. Never his face, his body or his name.
- **Establishing shots never contain the player.** Eye-level photographs from a visitor's
  position; the woman who owns the place may look into the lens.
- **The women act toward the lens.** Her gaze, her hand, her boot come at the camera.
- The framing rules in `cast.md` are hard rules too.

### Writing the subject

Every art subject is written per [workflows/KREA2_PROMPT_GUIDE.md](workflows/KREA2_PROMPT_GUIDE.md):
one dense standalone paragraph, 250–450 words, in the guide's sentence plan — medium and shot
type, subject, pose, wardrobe with materials, hands and props, mid-ground and background,
composition, one lighting sentence naming source and direction, a restrained palette, finish
cues. Only visible things; no story, no metaphors, no lore names, no keyword soup, no quality
tags, no absence phrasing. Light is chosen per image.

## What is off-limits (hard rules)

- Every character is unambiguously an adult. No minors, ever, in any context.
- Consent is settled at the door: entering this universe is the standing yes. The fiction never
  depicts the player as sexually unwilling or violated; his struggles are pride, nerve and cost.
- No rape, no sexual violence, nothing sexual written as forced or unwanted — authority is the
  charge, not violation. Pain and breath play stay controlled and short; nothing lasting.
  No bestiality. No real, identifiable people, no real towns' scandals or real agencies'
  personnel.
- Engine non-negotiables apply: fixed results, no map-speak in prose, consequences are cards.
