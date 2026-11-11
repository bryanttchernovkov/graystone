# Storyline plan: Juno, Miss Carrow, Elise Harker

Planning doc for the library triangle. The engine doesn't read it. Work from the engine repo root
with the `universe-author` skill, validate with `./umt validate graystone` after every change, and
commit in this repo (`git -C universes/graystone …`). Never run `./umt art` without `--dry-run`:
the author renders.

## The idea in one paragraph

Juno Vance (@rootkitty) is a femboy hacker who passes for a girl in town and sells the truth on his
page. Miss Imogen Carrow, the head librarian, and her partner Detective Elise Harker are both
female supremacists who smoke, and both have their eye on Juno. The player gets close to Juno (an
errand, a date, a hack), and gets close to the two women (favor, then their office). With Juno's
USB key in his pocket he can betray him to them. They arrest Juno, put the player in a cage, and
make him watch them together. After that, Elise's strap-on is available, and only while he's caged.

## Characters

- **Juno Vance**: see `cast.md` ("The library"). He/him in prose; his art prompts stay as they
  are (`jovessa woman`, what the town sees). Use `<lora:femboy_krea2:1>` (trigger `androgynous
  femboy`) for the scenes where the truth is shown, with his face as a `jovessa` pass.
- **Miss Imogen Carrow**: see `cast.md`. LoRA `imcrw7_krea2_000001200:1`. Her methods: OTK
  spanking, smoking and the human ashtray, worship of her stockinged feet and heels. Suspicious of
  Juno; calls him "Miss Vance" as an insult. Keeps a file on him in the V drawer under her desk.
- **Detective Elise Harker**: new, **no `cast.md` entry yet**. Imogen's partner. Quiet, smart,
  controlled; smokes; believes men belong in chastity; wants Juno in cuffs and a cage "for the fun
  of it". No fixed location: she appears in Carrow's office (later possibly the V0.3 interrogation
  detective, see `ideas.md`). LoRA `vqntz7_krea2_000001200:1`, trigger `vqntz7 woman`; read
  `~/code/prive/loras/char-elise-harker/README.md`. `in her detective suit` carries the long gray
  pinstriped coat, white shirt buttoned to the collar, black tie, black underbust corset, black
  trousers, belt badge (+ `black block-heel ankle boots` in full-length shots). Outside that suit,
  write out "long hair split down the middle, black on one side and platinum white on the other".
  Smoking is opt-in ("a lit cigarette").

## Done (uncommitted at the time of writing)

**Juno retcon (lore only):** cast entry, bible, his page, DMs, table, library and laptop prose.

**Juno's chain**:

| Step | Where | Gate | Gives |
|---|---|---|---|
| TALK-FLIRT | `library-juno-table` | requires `hooked`, unless `charmed`/`dating` | `junos-good-side` (`charmed`) |
| TAKE-DRAWER (cost 3, tag `pilfer`) | `library-desk` | requires `charmed`, unless `file` | `carrows-v-file` (`file`) |
| setback on DRAWER | `carrow-caught` (Good Side's penalty) | — | she hands the file over anyway |
| DEAL-GIVE | `library-juno-table` | requires `file` | loses file + Good Side, gains `junos-trust` (`dating`) |
| TALK-DATE | `library-juno-table` | requires `dating` | `move.to: juno-apartment` |
| TALK-STAY | `juno-apartment` | — | the date, ends on *Stay* / *Not tonight* |
| DEAL-HACK | `juno-apartment` | — | `rootkitty-usb` (`rootkit`) |
| RISK-PLANT (cost 3, tag `snoop`) | `station-bullpen` | requires `rootkit` | loses the key, gains `backdoor`; achievement `root-access` |

`backdoor` has WORK-WIPE: loses the Criminal Record once, and itself.

**Open hooks for the author's own scenes:**
- `carrow-caught` TALK-GO goes straight to `library-computers`. To add her spanking, point it at
  a new beat (`pvotk7` base, `imcrw7` pass, gains `sore-bottom`) that ends at `library-computers`.
  Spanking never fills her favor.
- `juno-apartment` TALK-STAY, option *Stay*, is a short fade-out. Give it a `move.to` to a new
  beat (POV, `femboy_krea2` base, `jovessa` face pass) and an achievement on that beat.

**Art to render (author):** `./umt art graystone --dry-run` lists 8 images.

## Done: Miss Carrow and Elise (uncommitted, 2026-11-11)

**Elise's `cast.md` entry** is under "The library", after Juno, with her LoRA, appearance block,
character and methods; Carrow's methods are filled in. `pvsmk7` and `pvstrp9` are in the kink
LoRA table.

**Carrow's chain:**

| Step | Where | Gate | Gives |
|---|---|---|---|
| LOOK-INQUIRE | `library-desk` | unless `noted`/`confidant` | `carrows-notice` (`noted`), boost 1 of 3 |
| TALK-RECOMMEND, WORK-VOLUNTEER (tag `proper`) | `library-desk` | — | +1 boost on the Notice, and its slots |
| LOOK-SPY (cost 1, tag `proper`) | `library-computers` | requires `noted`, unless `juno-arrested` | +1 boost on the Notice |
| Notice full | — | — | `carrows-confidence` (`confidant`) |
| TALK-ALONE | `library-desk` | requires `confidant` | `move.to: carrow-office` |
| TALK-SIT (cost 2), once | `carrow-office` | requires `confidant`, unless `conspirator` | ash in his hands, the plan for Juno; `tea-upstairs` (`conspirator`) |
| DEAL-ASHTRAY (cost 2) | `carrow-office` | requires `conspirator` | ash on his tongue; `ashtray-fetish` (`ash`) |
| DEAL-WORSHIP (cost 2) | `carrow-office` | requires `conspirator` | her stockinged feet and pumps; `heel-fetish` (`heels`) |
| TALK-TELL (cost 5) | `carrow-office` | requires `conspirator` + `rootkit` | loses `rootkitty-usb`; `chastity-cage` (`caged`), `the-third-chair` (`cucked`, `juno-arrested`); `move.to: carrow-watch`; achievement `overdue` |
| LOOK-WATCH | `carrow-watch` | — | the two of them together; back to `library-stacks` |
| DEAL-BEND (cost 3) | `carrow-office` | requires `cucked` + `caged` | Elise's strap-on |

`juno-arrested` hides APPROACH, LOGIN, WATCH and SPY in the computer corner and ASK, FLIRT, GIVE and
DATE at his table, and opens LOOK-EMPTY (his table, wiped down). The office is on `maps/carrow.yaml`
(CO, CW); out goes to the reading room.

**Art to render (author):** `./umt art graystone --dry-run` lists 22 images, 16 of them new: the
office and the watching beat (location and result art), six cards and `overdue`. Untested: `pvsmk7`
and `pvstrp9` in this checkpoint, `vqntz7` as a pass, and `hcstand2` under a `vqntz7` and a `jovessa` face pass (`overdue`: Harker cuffing Juno at his
table). The watching beat is POV in the worn cage (`pvcg5`) with the two women in words and a pass
each.

**Left open:**
- The two author hooks above (Carrow's back room from `carrow-caught`, Juno's *Stay*).
- Nothing reads `ash` or `heels` yet, and they have no fetishist achievements.
- With Juno arrested, his page and DMs (`juno-page`, the SIMP card actions) still work as if he
  were free. (The Backdoor can't coexist: PLANT and TELL both spend the one USB key.)
- If the cage ever comes off (later storylines), BEND just disappears.

## Rules to keep (from the skill and the bible)

- Results are fixed: prose never assumes what he holds or did. Gate with tags, never card IDs.
- Every `choose` has a free option; purchases are priced options.
- The prompt promises the result: if it turns sexual or punitive, the prompt says so.
- Achievement art is third person (Eli, with his `jack:1` pass first); everything else is POV.
- Two named women in one frame: base with both written out in words, then one pass per woman
  with her own LoRA.
- New tags go in `universe.yaml` with a comment, and each tag needs an icon in `icons/`.
- Keep the notes current: a header comment on every file, `cast.md` for looks, `ideas.md` checkboxes.
