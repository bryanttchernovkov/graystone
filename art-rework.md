# Art rework: passes

Every art block checked against art passes (engine ADR 0052; how to write them: the skill's
`art-guide.md#passes`). Generated from the art blocks on 2026-11-01; tick an image off once its
block is rewritten and validated.

**The rewrite, for every image with a character LoRA:**

1. **Base** (`subject` and `loras`): only the scene, pose or POV LoRAs. Every woman written out in
   words: her look and her **full kit** (the canonical uniform sentences in `cast.md`), because a
   pass fixes identity, not colours or clothes.
2. **One pass per character**: `find` ("the woman in …, from the top of her hair down to the bottom
   of the image"), a short `segment` label, her LoRA, and a standalone `subject` with her trigger
   in place of her description. Short prompts for LoRAs that want them (Seo).
3. **Then a prop pass** (`mtlcg7d`, `hngcf5`): `find` the prop with the hand holding it, no
   `segment`. Untested beyond one cage; if it doubles the prop, leave the prop in the base.
4. Pose and interaction LoRAs (`hcstand2`, `pvarst7`, `pvprsn7`, …) stay in the base only.
5. **Eli** (the player) gets his own pass with `jack:1` wherever he is in frame in third person (the
   achievements), before the woman's. His canon words stay in the base. Not in POV shots, where
   only his hands show.
6. A held cage goes in the base **and** in a last prop pass: her pass repaints the hand holding it
   without the cage LoRA. Don't write "caged bulb" in that image, or the prop takes the bulb guard's
   shape (County Property, 2026-11-02).
7. **Contrasting expressions, one per pass.** The two faces never share a word: she is composed, he
   is open (brows up, eyes wide or shut, mouth open, flushed). For her, write one feeling, where
   she looks and one or two features: a full list of features came out blank and robotic (Uniform
   Fetishist, 2026-11-02). The base has both; each pass keeps only its own person's expression and
   drops the other's, so it can't bleed into the mask.
8. **Seo may go in the base.** As a pass in a long prompt her face and hair came out wrong (Code Name:
   Gull). If so, load `sorenji` in a base as short as her captions and give only the man a pass.
   Untested until that image is rendered again.

Throughout: name whose hand and wrist (never "her" for two women), "ribbed knit sleeve bands"
for the bomber, a trigger only in the pass that loads its LoRA. Character passes keep their weight, at most
0.9; the base drops the prop weights that were raised to fight `ashby7` (`mtlcg7d` 2 → 1).

| Rewrite | Images |
|---|---|
| character pass | 93 |
| base LoRA + character pass | 19 |
| character pass + prop pass | 2 |
| **total to rewrite** | **114** |
| keep as is (no character LoRA) | 41 |

Flags found:

- third person with Eli: 16
- cuffs with two people: 11
- a woman in words only: 8
- bomber's "ribbed knit cuffs" → "ribbed knit sleeve bands": 3

## To rewrite

### achievements (15) — done 2026-11-01

Rewritten as base + passes: Eli first with `jack:1` (segment), then the woman with her LoRA. The
cage (`mtlcg7d` 1) and cuffs (`hngcf5` 0.9) went into the base, where no character LoRA competes,
instead of a prop pass. `escape-artist` (below, under keep) got Eli's pass too.

- [x] `achievements/boot-fetishist` (achievements/boot-fetishist.yaml)
  now: `ashby7` 0.9; 470 words
  plan: base: no LoRA → ashby7 0.9 (segment)
  ⚑ third person with Eli: write him out in the base, the woman in a pass
- [x] `achievements/brown-paper-bag` (achievements/brown-paper-bag.yaml)
  now: `sorenji` 1; 586 words
  plan: base: no LoRA → sorenji 0.9 (segment)
  ⚑ third person with Eli: write him out in the base, the woman in a pass
- [x] `achievements/code-name-gull` (achievements/code-name-gull.yaml)
  now: `sorenji` 1; 414 words
  plan: base: no LoRA → sorenji 0.9 (segment)
  ⚑ bomber's "ribbed knit cuffs" → "ribbed knit sleeve bands"
  ⚑ third person with Eli: write him out in the base, the woman in a pass
- [x] `achievements/county-property` (achievements/county-property.yaml)
  now: `ashby7` 1, `mtlcg7d` 2; 478 words
  plan: base: no LoRA → ashby7 0.9 (segment) → mtlcg7d 1 (box)
  ⚑ third person with Eli: write him out in the base, the woman in a pass
- [x] `achievements/doing-your-time` (achievements/doing-your-time.yaml)
  now: `ashby7` 0.9, `hngcf5` 0.9; 461 words
  plan: base: no LoRA → ashby7 0.9 (segment) → hngcf5 1 (box)
  ⚑ cuffs with two people: name whose wrist each cuff is on
  ⚑ third person with Eli: write him out in the base, the woman in a pass
- [x] `achievements/key-in-her-pocket` (achievements/key-in-her-pocket.yaml)
  now: `ashby7` 0.9; 542 words
  plan: base: no LoRA → ashby7 0.9 (segment)
  ⚑ third person with Eli: write him out in the base, the woman in a pass
- [x] `achievements/model-prisoner` (achievements/model-prisoner.yaml)
  now: `ashby7` 0.9; 417 words
  plan: base: no LoRA → ashby7 0.9 (segment)
  ⚑ third person with Eli: write him out in the base, the woman in a pass
- [x] `achievements/not-raymond-reddington` (achievements/not-raymond-reddington.yaml)
  now: `nivdoyle` 1; 255 words
  plan: base: no LoRA → nivdoyle 0.9 (segment)
  ⚑ third person with Eli: write him out in the base, the woman in a pass
- [x] `achievements/owner` (achievements/owner.yaml)
  now: `jovessa` 0.65; 374 words
  plan: base: no LoRA → jovessa 0.65 (segment)
  ⚑ third person with Eli: write him out in the base, the woman in a pass
- [x] `achievements/paypig` (achievements/paypig.yaml)
  now: `tfny7` 1; 496 words
  plan: base: no LoRA → tfny7 0.9 (segment)
  ⚑ bomber's "ribbed knit cuffs" → "ribbed knit sleeve bands"
  ⚑ third person with Eli: write him out in the base, the woman in a pass
- [x] `achievements/permanent-marker` (achievements/permanent-marker.yaml)
  now: `tfny7` 1; 366 words
  plan: base: no LoRA → tfny7 0.9 (segment)
  ⚑ third person with Eli: write him out in the base, the woman in a pass
- [x] `achievements/signoras-favorite` (achievements/signoras-favorite.yaml)
  now: `ferrina` 1; 346 words
  plan: base: no LoRA → ferrina 0.9 (segment)
  ⚑ third person with Eli: write him out in the base, the woman in a pass
- [x] `achievements/sock-fetishist` (achievements/sock-fetishist.yaml)
  now: `tfny7` 1; 413 words
  plan: base: no LoRA → tfny7 0.9 (segment)
  ⚑ third person with Eli: write him out in the base, the woman in a pass
- [x] `achievements/under-arrest` (achievements/under-arrest.yaml)
  now: `tfny7` 1, `hcstand2` 0.8; 566 words
  plan: base: `hcstand2` 0.8 → tfny7 0.9 (segment)
  ⚑ bomber's "ribbed knit cuffs" → "ribbed knit sleeve bands"
  ⚑ cuffs with two people: name whose wrist each cuff is on
  ⚑ third person with Eli: write him out in the base, the woman in a pass
- [x] `achievements/uniform-fetishist` (achievements/uniform-fetishist.yaml)
  now: `ashby7` 0.9; 453 words
  plan: base: no LoRA → ashby7 0.9 (segment)
  ⚑ third person with Eli: write him out in the base, the woman in a pass

### cards (8)

- [ ] `cards/favor/andersons-attention` (cards/favor/andersons-attention.yaml)
  now: `tfny7` 1; 203 words
  plan: base: no LoRA → tfny7 0.9 (segment)
- [ ] `cards/favor/andersons-paypig` (cards/favor/andersons-paypig.yaml)
  now: `tfny7` 1; 196 words
  plan: base: no LoRA → tfny7 0.9 (segment)
- [ ] `results/andersons-paypig.0` (cards/favor/andersons-paypig.yaml, actions[0])
  now: `tfny7` 1; 207 words
  plan: base: no LoRA → tfny7 0.9 (segment)
- [ ] `cards/favor/ashbys-good-side` (cards/favor/ashbys-good-side.yaml)
  now: `ashby7` 0.9; 240 words
  plan: base: no LoRA → ashby7 0.9 (segment)
- [ ] `cards/favor/ashbys-trust` (cards/favor/ashbys-trust.yaml)
  now: `ashby7` 0.9; 252 words
  plan: base: no LoRA → ashby7 0.9 (segment)
- [ ] `cards/favor/niamhs-good-side` (cards/favor/niamhs-good-side.yaml)
  now: `nivdoyle` 1; 123 words
  plan: base: no LoRA → nivdoyle 0.9 (segment)
- [ ] `cards/favor/rootkittys-simp` (cards/favor/rootkittys-simp.yaml)
  now: `jovessa` 1; 198 words
  plan: base: no LoRA → jovessa 0.9 (segment)
- [ ] `cards/favor/signoras-favorite` (cards/favor/signoras-favorite.yaml)
  now: `ferrina` 1; 181 words
  plan: base: no LoRA → ferrina 0.9 (segment)

### locations/people/anderson (21)

- [ ] `locations/anderson-arrest` (locations/people/anderson/anderson-arrest.yaml)
  now: `tfny7` 0.9, `pvarst7` 0.8; 196 words
  plan: base: `pvarst7` 0.8 → tfny7 0.9 (segment)
  ⚑ cuffs with two people: name whose wrist each cuff is on
- [ ] `locations/anderson-flatter-cold` (locations/people/anderson/anderson-flatter-cold.yaml)
  now: `tfny7` 1; 212 words
  plan: base: no LoRA → tfny7 0.9 (segment)
- [ ] `locations/anderson-flatter-warm` (locations/people/anderson/anderson-flatter-warm.yaml)
  now: `tfny7` 1; 235 words
  plan: base: no LoRA → tfny7 0.9 (segment)
- [ ] `locations/anderson-holding` (locations/people/anderson/anderson-holding.yaml)
  now: `tfny7` 1; 248 words
  plan: base: no LoRA → tfny7 0.9 (segment)
- [ ] `results/anderson-holding.deal.beg` (locations/people/anderson/anderson-holding.yaml, DEAL BEG)
  now: `tfny7` 1; 241 words
  plan: base: no LoRA → tfny7 0.9 (segment)
- [ ] `results/anderson-holding.deal.inhale` (locations/people/anderson/anderson-holding.yaml, DEAL INHALE)
  now: `tfny7` 1; 244 words
  plan: base: no LoRA → tfny7 0.9 (segment)
- [ ] `results/anderson-holding.deal.inventory` (locations/people/anderson/anderson-holding.yaml, DEAL INVENTORY)
  now: `tfny7` 1; 252 words
  plan: base: no LoRA → tfny7 0.9 (segment)
- [ ] `results/anderson-holding.deal.worship` (locations/people/anderson/anderson-holding.yaml, DEAL WORSHIP)
  now: `tfny7` 1; 242 words
  plan: base: no LoRA → tfny7 0.9 (segment)
- [ ] `results/anderson-holding.risk.tease` (locations/people/anderson/anderson-holding.yaml, RISK TEASE)
  now: `tfny7` 1, `HandgagPOV` 1; 261 words
  plan: base: `HandgagPOV` 1 → tfny7 0.9 (segment)
- [ ] `results/anderson-holding.talk.answer` (locations/people/anderson/anderson-holding.yaml, TALK ANSWER)
  now: `tfny7` 1; 256 words
  plan: base: no LoRA → tfny7 0.9 (segment)
- [ ] `results/anderson-holding.talk.name` (locations/people/anderson/anderson-holding.yaml, TALK NAME)
  now: `tfny7` 1; 264 words
  plan: base: no LoRA → tfny7 0.9 (segment)
- [ ] `locations/anderson-kitchen-boot` (locations/people/anderson/anderson-kitchen-boot.yaml)
  now: `tfny7` 1; 155 words
  plan: base: no LoRA → tfny7 0.9 (segment)
- [ ] `locations/anderson-kitchen-sharpie` (locations/people/anderson/anderson-kitchen-sharpie.yaml)
  now: `tfny7` 1; 161 words
  plan: base: no LoRA → tfny7 0.9 (segment)
- [ ] `locations/anderson-kitchen-spit` (locations/people/anderson/anderson-kitchen-spit.yaml)
  now: `tfny7` 1; 155 words
  plan: base: no LoRA → tfny7 0.9 (segment)
- [ ] `locations/anderson-patrol-car` (locations/people/anderson/anderson-patrol-car.yaml)
  now: `tfny7` 1; 254 words
  plan: base: no LoRA → tfny7 0.9 (segment)
- [ ] `results/anderson-patrol-car.deal.beg` (locations/people/anderson/anderson-patrol-car.yaml, DEAL BEG)
  now: `tfny7` 1; 284 words
  plan: base: no LoRA → tfny7 0.9 (segment)
- [ ] `results/anderson-patrol-car.deal.coffee` (locations/people/anderson/anderson-patrol-car.yaml, DEAL COFFEE)
  now: `tfny7` 1; 231 words
  plan: base: no LoRA → tfny7 0.9 (segment)
- [ ] `results/anderson-patrol-car.deal.inhale` (locations/people/anderson/anderson-patrol-car.yaml, DEAL INHALE)
  now: `tfny7` 1; 257 words
  plan: base: no LoRA → tfny7 0.9 (segment)
- [ ] `results/anderson-patrol-car.talk.introduce` (locations/people/anderson/anderson-patrol-car.yaml, TALK INTRODUCE)
  now: `tfny7` 1; 224 words
  plan: base: no LoRA → tfny7 0.9 (segment)
- [ ] `results/anderson-patrol-car.talk.thank` (locations/people/anderson/anderson-patrol-car.yaml, TALK THANK)
  now: `tfny7` 1; 209 words
  plan: base: no LoRA → tfny7 0.9 (segment)
- [ ] `locations/anderson-station-arrest` (locations/people/anderson/anderson-station-arrest.yaml)
  now: `tfny7` 0.9, `pvarst7` 0.8; 207 words
  plan: base: `pvarst7` 0.8 → tfny7 0.9 (segment)
  ⚑ cuffs with two people: name whose wrist each cuff is on

### locations/people/ashby (7)

- [ ] `locations/ashby-arrest` (locations/people/ashby/ashby-arrest.yaml)
  now: `ashby7` 0.8, `pvarst7` 0.8; 215 words
  plan: base: `pvarst7` 0.8 → ashby7 0.8 (segment)
  ⚑ cuffs with two people: name whose wrist each cuff is on
- [ ] `locations/ashby-cafe-table` (locations/people/ashby/ashby-cafe-table.yaml)
  now: `ashby7` 0.9; 338 words
  plan: base: no LoRA → ashby7 0.9 (segment)
- [ ] `results/ashby-cafe-table.deal.fetch` (locations/people/ashby/ashby-cafe-table.yaml, DEAL FETCH)
  now: `ashby7` 0.9; 300 words
  plan: base: no LoRA → ashby7 0.9 (segment)
- [ ] `results/ashby-cafe-table.talk.ask` (locations/people/ashby/ashby-cafe-table.yaml, TALK ASK)
  now: `ashby7` 0.9; 304 words
  plan: base: no LoRA → ashby7 0.9 (segment)
- [ ] `results/ashby-cafe-table.work.shine` (locations/people/ashby/ashby-cafe-table.yaml, WORK SHINE)
  now: `ashby7` 0.9; 253 words
  plan: base: no LoRA → ashby7 0.9 (segment)
- [ ] `results/ashby-cafe-table.work.stand` (locations/people/ashby/ashby-cafe-table.yaml, WORK STAND)
  now: `ashby7` 0.9; 219 words
  plan: base: no LoRA → ashby7 0.9 (segment)
- [ ] `locations/ashby-station-arrest` (locations/people/ashby/ashby-station-arrest.yaml)
  now: `ashby7` 0.8, `pvarst7` 0.8; 161 words
  plan: base: `pvarst7` 0.8 → ashby7 0.8 (segment)
  ⚑ cuffs with two people: name whose wrist each cuff is on

### locations/people/brandt (1)

- [ ] `locations/sheriff-desk` (locations/people/brandt/sheriff-desk.yaml)
  now: `lorbrandt` 1; 153 words
  plan: base: no LoRA → lorbrandt 0.9 (segment)

### locations/people/carrow (1)

- [ ] `locations/library-desk` (locations/people/carrow/library-desk.yaml)
  now: `imcrw7` 1; 194 words
  plan: base: no LoRA → imcrw7 0.9 (segment)

### locations/people/doyle (2)

- [ ] `locations/station-arrest` (locations/people/doyle/station-arrest.yaml)
  now: `nivdoyle` 1; 175 words
  plan: base: no LoRA → nivdoyle 0.9 (segment)
- [ ] `locations/station-desk` (locations/people/doyle/station-desk.yaml)
  now: `nivdoyle` 1; 146 words
  plan: base: no LoRA → nivdoyle 0.9 (segment)

### locations/people/giardano (4)

- [ ] `locations/giardano-backroom` (locations/people/giardano/giardano-backroom.yaml)
  now: `ferrina` 1; 226 words
  plan: base: no LoRA → ferrina 0.9 (segment)
- [ ] `results/giardano-backroom.deal.show` (locations/people/giardano/giardano-backroom.yaml, DEAL SHOW)
  now: `ferrina` 0.9, `pvcg5` 0.9; 288 words
  plan: base: `pvcg5` 0.9 → ferrina 0.9 (segment)
- [ ] `results/giardano-backroom.work.finish` (locations/people/giardano/giardano-backroom.yaml, WORK FINISH)
  now: `ferrina` 0.9, `femdom_handj` 1; 225 words
  plan: base: `femdom_handj` 1 → ferrina 0.9 (segment)
- [ ] `results/giardano-backroom.work.perform` (locations/people/giardano/giardano-backroom.yaml, WORK PERFORM)
  now: `ferrina` 1; 219 words
  plan: base: no LoRA → ferrina 0.9 (segment)

### locations/people/juno (7)

- [ ] `locations/juno-dm-boots` (locations/people/juno/juno-dm-boots.yaml)
  now: `jovessa` 1; 274 words
  plan: base: no LoRA → jovessa 0.9 (segment)
- [ ] `locations/juno-dm-selfie` (locations/people/juno/juno-dm-selfie.yaml)
  now: `jovessa` 1; 240 words
  plan: base: no LoRA → jovessa 0.9 (segment)
- [ ] `locations/juno-dm-socks` (locations/people/juno/juno-dm-socks.yaml)
  now: `jovessa` 1; 311 words
  plan: base: no LoRA → jovessa 0.9 (segment)
- [ ] `locations/juno-dm-tea` (locations/people/juno/juno-dm-tea.yaml)
  now: `jovessa` 1; 324 words
  plan: base: no LoRA → jovessa 0.9 (segment)
- [ ] `locations/juno-dm-video` (locations/people/juno/juno-dm-video.yaml)
  now: `jovessa` 1; 258 words
  plan: base: no LoRA → jovessa 0.9 (segment)
- [ ] `locations/juno-page` (locations/people/juno/juno-page.yaml)
  now: `jovessa` 1; 239 words
  plan: base: no LoRA → jovessa 0.9 (segment)
- [ ] `locations/library-juno-table` (locations/people/juno/library-juno-table.yaml)
  now: `jovessa` 1; 241 words
  plan: base: no LoRA → jovessa 0.9 (segment)

### locations/people/red (3)

- [ ] `locations/graybloods-wall` (locations/people/red/graybloods-wall.yaml)
  now: `shndr7` 1; 210 words
  plan: base: no LoRA → shndr7 0.9 (segment)
- [ ] `results/graybloods-wall.deal.report` (locations/people/red/graybloods-wall.yaml, DEAL REPORT)
  now: `shndr7` 1; 233 words
  plan: base: no LoRA → shndr7 0.9 (segment)
- [ ] `results/graybloods-wall.talk.ask` (locations/people/red/graybloods-wall.yaml, TALK ASK)
  now: `shndr7` 1; 215 words
  plan: base: no LoRA → shndr7 0.9 (segment)

### locations/people/seo (10)

- [ ] `locations/seo-arrest` (locations/people/seo/seo-arrest.yaml)
  now: `sorenji` 0.9, `pvarst7` 0.8; 252 words
  plan: base: `pvarst7` 0.8 → sorenji 0.9 (segment)
  ⚑ cuffs with two people: name whose wrist each cuff is on
- [ ] `locations/seo-booking` (locations/people/seo/seo-booking.yaml)
  now: `sorenji` 1; 219 words
  plan: base: no LoRA → sorenji 0.9 (segment)
- [ ] `locations/seo-dockside` (locations/people/seo/seo-dockside.yaml)
  now: `sorenji` 1; 118 words
  plan: base: no LoRA → sorenji 0.9 (segment)
- [ ] `locations/seo-holding` (locations/people/seo/seo-holding.yaml)
  now: `sorenji` 1; 124 words
  plan: base: no LoRA → sorenji 0.9 (segment)
- [ ] `results/seo-holding.deal.search` (locations/people/seo/seo-holding.yaml, DEAL SEARCH)
  now: `sorenji` 1; 107 words
  plan: base: no LoRA → sorenji 0.9 (segment)
- [ ] `results/seo-holding.work.pose` (locations/people/seo/seo-holding.yaml, WORK POSE)
  now: `sorenji` 1; 227 words
  plan: base: no LoRA → sorenji 0.9 (segment)
- [ ] `locations/seo-rights` (locations/people/seo/seo-rights.yaml)
  now: `sorenji` 1; 233 words
  plan: base: no LoRA → sorenji 0.9 (segment)
- [ ] `locations/seo-station-arrest` (locations/people/seo/seo-station-arrest.yaml)
  now: `sorenji` 0.9, `pvarst7` 0.8; 223 words
  plan: base: `pvarst7` 0.8 → sorenji 0.9 (segment)
  ⚑ cuffs with two people: name whose wrist each cuff is on
- [ ] `locations/seo-steps` (locations/people/seo/seo-steps.yaml)
  now: `sorenji` 1; 222 words
  plan: base: no LoRA → sorenji 0.9 (segment)
- [ ] `locations/seo-trample` (locations/people/seo/seo-trample.yaml)
  now: `sorenji` 1; 211 words
  plan: base: no LoRA → sorenji 0.9 (segment)

### locations/places/cafe-linde (6)

- [ ] `locations/cafe-linde-counter` (locations/places/cafe-linde/cafe-linde-counter.yaml)
  now: `ferrina` 1; 274 words
  plan: base: no LoRA → ferrina 0.9 (segment)
- [ ] `results/cafe-linde-counter.deal.order` (locations/places/cafe-linde/cafe-linde-counter.yaml, DEAL ORDER)
  now: `ferrina` 1; 194 words
  plan: base: no LoRA → ferrina 0.9 (segment)
- [ ] `results/cafe-linde-counter.deal.stay` (locations/places/cafe-linde/cafe-linde-counter.yaml, DEAL STAY)
  now: `ferrina` 1; 220 words
  plan: base: no LoRA → ferrina 0.9 (segment)
- [ ] `results/cafe-linde-counter.talk.chat` (locations/places/cafe-linde/cafe-linde-counter.yaml, TALK CHAT)
  now: `ferrina` 1; 218 words
  plan: base: no LoRA → ferrina 0.9 (segment)
- [ ] `results/cafe-linde-counter.work.taste` (locations/places/cafe-linde/cafe-linde-counter.yaml, WORK TASTE)
  now: `ferrina` 1; 220 words
  plan: base: no LoRA → ferrina 0.9 (segment)
- [ ] `locations/cafe-linde-window` (locations/places/cafe-linde/cafe-linde-window.yaml)
  now: `ashby7` 0.9; 330 words
  plan: base: no LoRA → ashby7 0.9 (segment)

### locations/places/church (5)

- [ ] `results/station-bullpen.work.fix` (locations/places/church/station-bullpen.yaml, WORK FIX)
  now: `nivdoyle` 1; 176 words
  plan: base: no LoRA → nivdoyle 0.9 (segment)
- [ ] `results/station-bullpen.work.service` (locations/places/church/station-bullpen.yaml, WORK SERVICE)
  now: `nivdoyle` 1; 205 words
  plan: base: no LoRA → nivdoyle 0.9 (segment)
- [ ] `results/station-kitchen.deal.greet` (locations/places/church/station-kitchen.yaml, DEAL GREET)
  now: `tfny7` 1; 174 words
  plan: base: no LoRA → tfny7 0.9 (segment)
- [ ] `locations/station-lobby` (locations/places/church/station-lobby.yaml)
  now: `nivdoyle` 1; 193 words
  plan: base: no LoRA → nivdoyle 0.9 (segment)
- [ ] `locations/station-sheriff-office` (locations/places/church/station-sheriff-office.yaml)
  now: `lorbrandt` 1; 204 words
  plan: base: no LoRA → lorbrandt 0.9 (segment)

### locations/places/docks (2)

- [ ] `locations/docks-river` (locations/places/docks/docks-river.yaml)
  now: `sorenji` 1; 352 words
  plan: base: no LoRA → sorenji 0.9 (segment)
- [ ] `locations/docks-warehouse` (locations/places/docks/docks-warehouse.yaml)
  now: `shndr7` 1; 275 words
  plan: base: no LoRA → shndr7 0.9 (segment)

### locations/places/library (2)

- [ ] `locations/library-computers` (locations/places/library/library-computers.yaml)
  now: `jovessa` 1; 242 words
  plan: base: no LoRA → jovessa 0.9 (segment)
- [ ] `locations/library-stacks` (locations/places/library/library-stacks.yaml)
  now: `imcrw7` 1; 264 words
  plan: base: no LoRA → imcrw7 0.9 (segment)

### locations/places/undercroft (20)

- [ ] `results/undercroft-cell-back.deal.ask` (locations/places/undercroft/undercroft-cell-back.yaml, DEAL ASK)
  now: `ashby7` 0.9, `femdom_handj` 1; 325 words
  plan: base: `femdom_handj` 1 → ashby7 0.9 (segment)
- [ ] `results/undercroft-cell-back.deal.offer` (locations/places/undercroft/undercroft-cell-back.yaml, DEAL OFFER)
  now: `ashby7` 0.9, `R2Y1DH5FQY41` 0.5; 252 words
  plan: base: `R2Y1DH5FQY41` 0.5 → ashby7 0.9 (segment)
- [ ] `results/undercroft-cell-back.risk.climb` (locations/places/undercroft/undercroft-cell-back.yaml, RISK CLIMB)
  now: `pvprsn7v3` 1, `ashby7` 0.8; 276 words
  plan: base: `pvprsn7v3` 1 → ashby7 0.8 (segment)
- [ ] `results/undercroft-cell-back.work.tidy` (locations/places/undercroft/undercroft-cell-back.yaml, WORK TIDY)
  now: `ashby7` 0.9, `pvcg5` 0.9; 237 words
  plan: base: `pvcg5` 0.9 → ashby7 0.9 (segment)
- [ ] `locations/undercroft-cell` (locations/places/undercroft/undercroft-cell.yaml)
  now: `ashby7` 0.9; 217 words
  plan: base: no LoRA → ashby7 0.9 (segment)
- [ ] `results/undercroft-cell.deal.appeal` (locations/places/undercroft/undercroft-cell.yaml, DEAL APPEAL)
  now: `pvprsn7v3` 1, `ashby7` 0.8; 229 words
  plan: base: `pvprsn7v3` 1 → ashby7 0.8 (segment)
  ⚑ cuffs with two people: name whose wrist each cuff is on
- [ ] `results/undercroft-cell.deal.kneel` (locations/places/undercroft/undercroft-cell.yaml, DEAL KNEEL)
  now: `ashby7` 0.9; 313 words
  plan: base: no LoRA → ashby7 0.9 (segment)
- [ ] `results/undercroft-cell.deal.promise` (locations/places/undercroft/undercroft-cell.yaml, DEAL PROMISE)
  now: `pvprsn7v3` 1, `ashby7` 0.8; 237 words
  plan: base: `pvprsn7v3` 1 → ashby7 0.8 (segment)
  ⚑ cuffs with two people: name whose wrist each cuff is on
- [ ] `results/undercroft-cell.deal.sign` (locations/places/undercroft/undercroft-cell.yaml, DEAL SIGN)
  now: `ashby7` 0.9; 346 words
  plan: base: no LoRA → ashby7 0.9 (segment)
- [ ] `results/undercroft-cell.deal.thank` (locations/places/undercroft/undercroft-cell.yaml, DEAL THANK)
  now: `ashby7` 0.9, `pvcg5` 0.9; 258 words
  plan: base: `pvcg5` 0.9 → ashby7 0.9 (segment)
- [ ] `results/undercroft-cell.look.admire` (locations/places/undercroft/undercroft-cell.yaml, LOOK ADMIRE)
  now: `ashby7` 0.9; 321 words
  plan: base: no LoRA → ashby7 0.9 (segment)
- [ ] `results/undercroft-cell.look.watch` (locations/places/undercroft/undercroft-cell.yaml, LOOK WATCH)
  now: `ashby7` 0.9; 370 words
  plan: base: no LoRA → ashby7 0.9 (segment)
- [ ] `results/undercroft-cell.risk.noise` (locations/places/undercroft/undercroft-cell.yaml, RISK NOISE)
  now: `ashby7` 0.9, `HandgagPOV` 1; 310 words
  plan: base: `HandgagPOV` 1 → ashby7 0.9 (segment)
- [ ] `results/undercroft-cell.talk.call` (locations/places/undercroft/undercroft-cell.yaml, TALK CALL)
  now: `ashby7` 0.9; 245 words
  plan: base: no LoRA → ashby7 0.9 (segment)
- [ ] `results/undercroft-cell.work.chore` (locations/places/undercroft/undercroft-cell.yaml, WORK CHORE)
  now: `ashby7` 0.9; 313 words
  plan: base: no LoRA → ashby7 0.9 (segment)
- [ ] `results/undercroft-charm-warm.arrival` (locations/places/undercroft/undercroft-charm-warm.yaml, arrival)
  now: `ashby7` 0.9; 259 words
  plan: base: no LoRA → ashby7 0.9 (segment)
- [ ] `locations/undercroft-trusted-release` (locations/places/undercroft/undercroft-trusted-release.yaml)
  now: `ashby7` 0.9; 364 words
  plan: base: no LoRA → ashby7 0.9 (segment)
- [ ] `locations/undercroft` (locations/places/undercroft/undercroft.yaml)
  now: `ashby7` 0.9; 276 words
  plan: base: no LoRA → ashby7 0.9 (segment)
- [ ] `results/undercroft.deal.terms` (locations/places/undercroft/undercroft.yaml, DEAL TERMS)
  now: `pvprsn7v3` 1, `ashby7` 0.8; 234 words
  plan: base: `pvprsn7v3` 1 → ashby7 0.8 (segment)
  ⚑ cuffs with two people: name whose wrist each cuff is on
- [ ] `results/undercroft.talk.ask` (locations/places/undercroft/undercroft.yaml, TALK ASK)
  now: `ashby7` 0.9; 284 words
  plan: base: no LoRA → ashby7 0.9 (segment)

## Keep as is

No character LoRA: nothing for a pass to separate. They already look like the new base renders;
re-render them with the rest only if the look has drifted. ⚑ marks a woman written in words: check
she is an extra, not a cast member who should get her LoRA in a pass.

- `achievements/escape-artist`: no LoRA; done: Eli's `jack` pass added
- `cards/dossier/criminal-record`: `hngcf5` 0.9
- `cards/dossier/inmate`: no LoRA
- `cards/dossier/served-sentence`: no LoRA
- `cards/favor/cafe-linde-punch-card`: no LoRA
- `cards/favor/graybloods-rep`: no LoRA
- `cards/favor/rootkitty-subscription`: no LoRA
- `cards/favor/seos-informant`: no LoRA
- `cards/favor/seos-snitch`: no LoRA ⚑
- `cards/fetish/boot-fetish`: no LoRA
- `cards/fetish/sock-fetish`: no LoRA
- `cards/fetish/uniform-fetish`: no LoRA
- `cards/gear/contractor-badge`: no LoRA
- `cards/hero/eli-novak`: no LoRA
- `cards/job/reds-errand`: no LoRA ⚑
- `cards/mark/nude`: no LoRA
- `cards/mark/paypig-sharpie`: no LoRA
- `cards/restraint/chastity-cage`: `mtlcg7d` 1
- `cards/restraint/gag`: no LoRA
- `cards/restraint/handcuffs`: `hngcf5` 0.9
- `cards/restraint/mitts`: `pvprsn7v3` 1
- `cards/restraint/prison-chains`: `pvprsn7v3` 1
- `endings/run-out`: no LoRA
- `locations/station-bullpen`: no LoRA ⚑
- `locations/station-gym`: no LoRA ⚑
- `locations/station-kitchen`: no LoRA
- `locations/home-bedroom`: no LoRA
- `locations/home-front`: no LoRA
- `locations/home-laptop`: no LoRA
- `results/home-laptop.look.news`: no LoRA ⚑
- `results/home-laptop.take.hack`: no LoRA
- `locations/home-living`: no LoRA
- `locations/heights`: no LoRA ⚑
- `locations/main-street-north`: no LoRA ⚑
- `locations/main-street-south`: no LoRA
- `locations/mill-street`: no LoRA
- `locations/undercroft-cell-back`: no LoRA
- `results/undercroft-cell-back.look.study`: no LoRA
- `results/undercroft-cell-back.look.wait`: `pvprsn7v3` 1
- `results/undercroft-cell-back.risk.slip`: no LoRA
- `cover`: no LoRA ⚑

