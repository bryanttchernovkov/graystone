# Guide to Writing Effective Krea 2 Image Prompts

**Focus: long-form, detailed, photorealistic prompting.** Krea's own documentation states that "long detailed prompts yield best results," the model was trained on dense natural-language captions, and Large — the photorealism variant — is documented to reward long, dense, paragraph-level description. Short prompts are covered where they are the right tool (exploration, fast drafting, reference-driven workflows), but the default posture of this guide is the fully art-directed dense photographic prompt.

The default recipe for a photoreal result: **Krea 2 Large · Creativity Raw or Low · one dense natural-language paragraph**, with a named light source, camera vocabulary, material micro-texture, and an explicitly described mid-ground and background. At Raw/Low nothing expands the prompt for you — the density has to be yours (see sections 8 and 17).

This guide combines Krea's official documentation and blog posts, the official open-source repo, the fal.ai prompting guide, ComfyUI-community findings, and community-reported practices. It covers all Krea 2 variants (Medium, Large, Turbo, and the self-hosted Raw checkpoint), the text encoder's behavior, style references, moodboards, trained styles/LoRAs, and photography-specific patterns.

## 1. Make every prompt completely standalone

Each prompt must contain everything required to generate that image independently. Krea 2 does not reliably inherit details from another prompt, an earlier generation, or the surrounding conversation.

Avoid:

> The same woman as before, now standing outside.

Prefer:

> A woman in her early thirties with short black curls, warm brown skin, and a mustard-yellow raincoat stands beneath a striped awning on a rainy city street.

When creating a series, repeat all continuity-critical details in every prompt:

- Character appearance and clothing
- Product shape, color, and materials
- Location and time of day
- Artistic medium and visual style
- Recurring color palette
- Camera or composition conventions

Do not use phrases such as "the same character," "as above," "again," "continue the scene," or "in the previous style." Replace those references with the actual information.

A useful test is:

> If this prompt were copied into an empty Krea session, would it still describe the intended image?

For a persistent recurring character, a trained character LoRA (Krea "style") plus a consistent seed is more reliable than re-describing the person in prose — see section 13.

## 2. Describe what should appear, not what should be absent

Write the desired visible result positively. Concepts mentioned in a negative instruction can still influence generation, especially when they appear inside the main prompt.

| Avoid | Describe the desired state |
|---|---|
| no people | an empty, uninhabited beach |
| no blur | tack-sharp focus across the entire frame |
| no clutter | a sparse, orderly room with generous open space |
| no smile | a calm, neutral expression |
| no harsh shadows | soft, even illumination with gentle tonal transitions |
| no bright colors | a restrained palette of charcoal, cream, and muted brown |
| no background objects | a solitary object against a seamless pale-grey backdrop |
| no writing on the package | a blank, unprinted package with a clean matte surface |

If the unwanted element does not require a replacement, simply omit it. For example, instead of writing "a landscape with no text or watermark," describe the landscape itself.

Most hosted Krea model interfaces emphasize a positive prompt and may not expose a separate negative-prompt field, so Krea's own integration guidance recommends positive phrasing. Self-hosted Krea 2 Raw workflows can technically use negative conditioning through classifier-free guidance, but that is a separate advanced control—not a reason to fill the main prompt with prohibitions.

One structured exception exists: moodboard analysis can produce an explicit "avoids" list that steers generation away from qualities you do not want (section 12). That is a dedicated control, not prompt prose.

Sources: [Krea prompt-engineering reference](https://github.com/krea-ai/skills/blob/main/krea-generate/references/prompt-engineering.md), [official Krea 2 sampling implementation](https://github.com/krea-ai/krea-2/blob/main/sampling.py)

## 3. Use natural language instead of keyword soup

Krea officially recommends natural-language prompts. Write a coherent description rather than a pile of model-specific tokens, quality boosters, or weighting syntax.

Avoid:

> woman, portrait, beautiful, masterpiece, 8k, best quality, cinematic, ultra detailed, sharp, trending

Prefer:

> A close head-and-shoulders portrait of an elderly violin maker seated beside a workshop window. Soft overcast daylight reveals the texture of his hands and linen apron. Quiet documentary photography, natural skin texture, subdued brown and slate-blue palette, shallow depth of field.

A comma-separated phrase can still work, but every phrase should add meaningful visual information. Krea's published examples range from one short sentence to dense descriptive paragraphs.

This is not just a style preference — it matches the architecture. Krea 2's text encoder parses sentences and grammar, and ignores quality-boilerplate tokens entirely (section 8).

## 4. Know which variant you are prompting

Krea 2 ships in several variants, and the best prompt length and vocabulary differ between them.

| Variant | Character | Best for | Notes |
|---|---|---|---|
| **Medium** (hosted) | Heavier post-training: stable, consistent output | Illustration, anime, painting, concept art, expressive styles | The default for everyday work; from $0.03/image |
| **Large** (hosted) | Softer post-training: "rawer, more textured, more flexible" | Photorealism, editorial, raw/gritty looks (motion blur, grain, low dynamic range) | Richest output, slower; from $0.06/image |
| **Medium Turbo** (hosted) | Distilled, ~4 seconds, 2 credits, 1K, batches of 4 | Rapid prompt testing, slider exploration, drafts | Avoid for final photoreal production or maximum consistency |
| **Raw** (self-hosted checkpoint) | Undistilled base, most malleable | Fine-tuning, LoRA training, research | LoRAs trained on Raw are designed to apply cleanly on Turbo |
| **Turbo** (self-hosted checkpoint) | 8-step distilled (CFG 0) | Fast local inference, up to 2K | Raw runs ~52 steps at CFG 3.5 in the official implementation |

Practical prompting implications:

- **Rule of thumb (fal.ai):** default to Medium; choose Large when you want realism or a raw, textured look.
- **Large rewards long, dense, paragraph-level description** — fal.ai's longest landscape and still-life prompts run on Large. Gritty realism cues ("slight motion blur," "film grain," "low dynamic range") land especially well there.
- **Medium is the stronger illustration engine** — anime, flat-color, painterly, and concept-art styles are more stable there than on Large.
- **Turbo works well with concise prompts.** Use it to sweep prompt variants cheaply, then re-run the winning prompt on Medium or Large. The docs explicitly position Turbo as the exploration tool before "graduating" drafts.
- The hosted API currently exposes 1K resolution for Medium/Large; the open Turbo checkpoint supports up to 2K. Both checkpoints were trained at 2048×2048, so ComfyUI users should generate at native scale rather than generating small and upscaling.

Aspect ratios and pixel sizes (all hosted variants):

- Square: 1:1 → 1024×1024
- Landscape: 4:3 → 1184×896; 3:2 → 1248×832; 16:9 → 1376×768; 2.35:1 → 1568×672
- Portrait: 4:5 → 928×1152; 2:3 → 832×1248; 9:16 → 768×1376

Sources: [Krea 2 docs (Medium & Large)](https://www.krea.ai/docs/user-guide/features/krea-2), [Krea 2 Turbo docs](https://www.krea.ai/docs/user-guide/features/krea-2-turbo), [Krea 2 developer overview](https://www.krea.ai/docs/developers/krea-2/overview), [fal.ai Krea 2 prompting guide](https://fal.ai/learn/tools/krea-2-prompting-guide), [ComfyUI prompt & style guide](https://www.instasd.com/post/krea-2-prompt-and-style-guide-comfyui)

## 5. Build the prompt in a clear visual order

A reliable structure is:

> **Medium + subject + action + setting + composition + lighting + color + finishing details**

Not every prompt needs every category. Include only details that matter.

### Medium

State what kind of image it is:

- Documentary photograph
- Editorial fashion photograph
- Hand-painted gouache illustration
- Graphite architectural sketch
- Clay stop-motion frame
- Screen-printed poster
- Stylized 3D render

If the user requests a particular medium, preserve it. Krea's own prompt-expansion guidance specifically warns against changing a photograph into an illustration—or vice versa—just because another medium might be easier.

Krea 2 also has real world knowledge: midtraining emphasized captions mentioning rare named concepts, so known subjects, landmarks, characters, and brands can be evoked by name.

### Subject and action

Identify the central subject first, then attach its attributes and actions clearly:

> A small red fox with wet autumn fur steps carefully across a fallen birch trunk.

This is more grounded than:

> A red fox, wet fur, autumn, walking, birch tree.

### Setting

Describe where the subject exists:

> In a misty forest clearing just after sunrise, surrounded by copper-colored ferns and slender white birch trees.

Community testing on prompt adherence found that describing the **mid-ground and background** explicitly (not just the subject) measurably improves how well the full scene follows the prompt.

### Composition

Use spatial and photographic language:

- Close-up, medium shot, full-body view, or wide establishing shot
- Eye-level, overhead, low-angle, or three-quarter view
- Centered, asymmetrical, or subject in the lower-left third
- Foreground, middle ground, and distant background
- Large open space above or beside the subject
- Symmetrical frontal composition

Camera and composition vocabulary maps directly to output in **both** photography and illustration — fal.ai's illustration examples use the same language ("exaggerated wide camera angle," "contrapposto pose," "wide angle") that photographic prompts do. Obvious, unambiguous framing words ("wide angle," "close-up," "sharp focus") work better than subtle variations.

Prefer spatial relationships over disconnected lists:

> The cyclist occupies the lower-right third, riding toward the distant lighthouse on the left horizon.

### Lighting and color

Specify the light source and its effect:

> Late-afternoon sunlight enters from the left, creating long soft-edged shadows and warm highlights against a cool blue background.

Avoid contradictory instructions such as "soft diffused light, hard dramatic shadows, flat lighting." The ComfyUI community's rule of thumb: when results look "mushy," the cause is usually two competing actions in one prompt **or no described light source** — always say where the light comes from.

### Surface and finish

Add texture only when it contributes to the intended look:

- Coarse watercolor paper
- Visible dry-brush marks
- Fine 35 mm film grain
- Smooth translucent resin
- Weathered limestone
- Crisp vector-like edges

Source: [Official Krea 2 expansion instructions](https://github.com/krea-ai/krea-2/blob/main/docs/expansion.txt)

## 6. Keep details grouped with the correct subject

When several people or objects appear, describe each one separately. This reduces attribute leakage.

Ambiguous:

> Two hikers, one in a red coat and one holding a map, blue backpack, standing by a cabin.

Clearer:

> Two hikers stand beside a timber cabin. The taller hiker wears a red coat and carries a blue backpack. The shorter hiker wears a grey fleece and holds an unfolded trail map with both hands.

State important relationships explicitly:

- Who is holding which object
- Who stands on the left or right
- Which direction each person faces
- What is foreground versus background
- Whether subjects look at each other or at the camera

Krea's official expansion instructions recommend grouping subjects with their own attributes, actions, poses, and spatial layout.

## 7. Be detailed without inventing irrelevant details

More detail is useful only when it narrows a meaningful creative decision. Do not arbitrarily assign colors, clothing, props, or materials merely to make the prompt longer.

Over-specified:

> A baker wearing a teal cotton shirt, maroon apron, silver wristwatch, brown shoes, yellow socks, and tortoiseshell glasses holds a walnut rolling pin beside three blue bowls...

Focused:

> A flour-dusted baker shapes bread at a worn wooden counter in a small morning bakery. Natural window light, warm documentary photography, intimate waist-up composition.

Prioritize details in this order:

1. Subject identity and action
2. Essential relationships
3. Composition
4. Medium or style
5. Lighting and palette
6. Supporting texture and atmosphere

Krea 2 was trained heavily on rich natural-language captions, so dense prompts can provide strong supervision. However, its prompt expander also turns underspecified ideas into richer directions, meaning unnecessary detail can restrict useful exploration.

For photoreal production, resolve that trade-off toward density. At Creativity Raw/Low no expander fills the gaps, so a short prompt produces a generic image. The over-specification warning targets invented identity — arbitrary characters, props, and colors the brief never implied — not dense description of light behavior, material surfaces, and environment, which is precisely the detail that pulls a result toward photorealism. Dense and coherent beats long and padded: every sentence must add visual information.

Source: [Krea 2 technical report](https://www.krea.ai/blog/krea-2-technical-report)

## 8. How Krea 2 actually reads your prompt

Understanding the encoder changes how you write. These findings come from the technical report and the ComfyUI community's analysis of the open checkpoint.

**The text encoder is Qwen3VL 4B — a vision-language model that parses sentences, not tags.** It reads grammar: spatial relationships, possessives, and counts survive into the image. "Quality confetti" ("masterpiece, best quality, 8k") is simply ignored — it adds nothing.

**Legacy prompt-weighting syntax does not work.** `(word:1.2)` was designed for CLIP's per-token weighting. Qwen3VL reads full sentences, so scaling one token shifts the whole conditioning — pushed far enough, the image degrades before any "emphasis" lands. Working alternatives:

- **Order is emphasis.** The encoder front-loads. "A weathered brass compass on a nautical chart" keeps the compass dominant; "A nautical chart with a brass compass on it" hands the frame to the chart.
- **Restate, don't multiply.** Instead of `(rust:1.4)`, write "a rusted iron gate, orange corrosion eating through the hinges."
- **Specificity beats loudness.** "Oxblood" lands the color on the first try; "red" repeated or weighted fights the model.

**The minimal reliable formula** (ComfyUI community): one subject, one action, where the light comes from, one or two textures. A compact but complete prompt following that formula outperforms a long prompt with two competing actions and no stated light source.

**Training distribution favors long, enriched captions.** Captions in training were built from OCR text, camera metadata, and enriched descriptions, reformatted into varied lengths. Long captions dominated (dense supervision), but short prompts were included throughout — which is why a bare prompt like "a cat riding a bicycle" still works, and why the hosted expander (Creativity setting, section 9) exists to close the gap. The expander even carries a deliberate photographic-medium bias, so photorealistic intents get expanded with photographic language.

**Reproduce results with the seed.** On the API, reusing the same prompt *and* seed reproduces the result; reuse is essential when A/B-testing prompt edits.

Sources: [Krea 2 technical report](https://www.krea.ai/blog/krea-2-technical-report), [ComfyUI prompt & style guide](https://www.instasd.com/post/krea-2-prompt-and-style-guide-comfyui), [Krea 2 developer overview](https://www.krea.ai/docs/developers/krea-2/overview)

## 9. Match prompt precision to the desired workflow

Production comes first in this guide; exploration is how you find the direction you then produce densely.

### For controlled production (the default)

Write a fuller brief:

> A playful 1960s editorial cartoon of a small orange tabby riding a pale-blue bicycle through a quiet European square. Side view, the cat and bicycle fully visible, low storefronts forming a simple background. Flat mustard, coral, blue, and cream palette, loose black ink outlines, slightly misregistered screen-print texture, landscape composition.

For photography, apply the full long-form pattern in section 17 — medium and shot type, subject and wardrobe materials, pose anatomy, mid-ground and background, composition, a complete lighting sentence, palette, and lens/finish cues, as one dense paragraph.

Use Krea's Creativity setting accordingly. Creativity controls how much the built-in prompt expander fills in style, composition, camera angle, and palette when your prompt leaves gaps:

- **Raw:** No expansion; renders only what is explicitly described. Use when the prompt is fully art-directed.
- **Low:** Minimal expansion; stays literal and fills only obvious gaps.
- **Medium (default):** Balanced interpretation; adds reasonable detail without straying from intent.
- **High:** Strong creative liberty with style, mood, and aesthetics. Best for short or open-ended prompts where you want surprise.

Krea recommends Raw or Low for precise prompts and Medium or High for loose prompts. Note the interaction with length: a short prompt plus Medium/High leans on the expander to write the dense caption for you, while a short prompt at Raw/Low stays short — generic and underspecified. For photoreal control, write the density yourself and set Raw or Low.

Source: [Krea Generative Sliders guide](https://www.krea.ai/blog/generative-sliders), [Krea 2 developer overview](https://www.krea.ai/docs/developers/krea-2/overview)

### For exploration (finding the direction)

Start with a simple concept:

> A cat riding a bicycle.

Generate several results, identify an appealing direction, and then add one or two constraints:

> A cat riding a bicycle, playful 1960s cartoon illustration with flat colors and loose ink outlines.

Krea explicitly recommends this broad-to-narrow workflow because simple prompts are treated as invitations to explore different visual interpretations. Their recommended loop: "start vague, see where the model takes you, lock in what works, push deeper." Adding a style cue narrows the variety *within* that style rather than collapsing it to one look. Rough, degraded aesthetics ("extremely grainy lo-fi VHS still") are honored rather than cleaned up — the model is deliberately unopinionated.

Exploration ends where production begins: once a direction wins, write the dense paragraph and re-run it at Raw/Low for the final.

Source: [Krea 2 exploration guide](https://www.krea.ai/blog/explorative-prompting-krea-2)

## 10. Treat settings as settings, not prose

When Krea provides a dedicated control, use it instead of redundantly forcing it into the prompt:

- Aspect ratio controls the canvas.
- Creativity controls prompt interpretation/expansion.
- Intensity, Complexity, and Movement (generative sliders) control visual character.
- Style-reference strength controls how strongly a reference influences the result.
- Seed controls reproducibility.

The generative sliders range from −100 to +100 with 0 as neutral, and work on every Krea 2 variant:

| Slider | Negative direction | Positive direction |
|---|---|---|
| Intensity | Muted, understated, bland | Bold, heavily stylized |
| Complexity | Minimal, clean composition | Chaotic, dense, detail-rich |
| Movement | Static, grounded | Dynamic poses, motion blur, camera movement |

Krea's documented starting points:

- Clean design, icons, editorial illustration: Complexity ≈ −60, Movement near 0
- Cinematic, fashion, character work: Intensity ≈ +60, Movement ≈ +30
- Expressive worlds: Intensity and Complexity positive, plus Movement for energy
- Example from the docs: "cinematic portrait of a samurai at dusk" with Intensity 75, Movement 30

Sliders are deliberately independent of Creativity: Creativity governs how literally the prompt is read; sliders shape the visual character. Krea also offers a Random mode that re-randomizes sliders per generation for quick exploration — once a promising direction appears, disable it and tune sliders individually.

For systematic iteration, keep the prompt fixed and adjust one setting at a time. Krea specifically demonstrates this approach with its generative sliders.

Sources: [Krea 2 generative sliders (developer docs)](https://www.krea.ai/docs/developers/krea-2/generative-sliders), [Introducing Generative Sliders](https://www.krea.ai/blog/generative-sliders)

## 11. Separate content from style references

A helpful mental model is:

> **The prompt describes what is in the image. The reference describes how it should look.**

Even with a style reference, the text prompt should remain standalone regarding content:

> A white ceramic teapot and two small cups arranged on a low oak table beside an open window, quiet morning atmosphere, asymmetrical still-life composition.

Do not write:

> Make the objects like the reference, but use the arrangement we discussed.

Strength calibration (API scale −2 to 2 per reference; the web UI shows roughly equivalent percentages):

- **~0.3–0.5 (UI ~20–50%):** subtle influence — the prompt leads, the reference adds character (palette hints, faint painted quality)
- **~0.6 (UI ~50%):** the documented balanced starting point — clearly stylized but the prompt stays in charge
- **~0.8–1.0 (UI 80%+):** the reference dominates — same palette, brush strokes, composition; useful when the prompt is generic. Pushed further, style may start overriding subject details, leaking colors and composition from the reference.
- **Negative values:** steer the output *away* from the reference's style.
- **Multiple references:** up to four, each with its own strength. Blending is additive — start with strengths that sum near 1.0 (e.g., 0.6 + 0.4) and rebalance from there. Krea notes the most interesting results usually come from stacking two or three.
- Tune incrementally, nudging by 0.1 at a time.

The general rule from the docs: the more descriptive and specific your prompt, the *lower* the reference strength should be; generic prompts should lean on higher strength so the visual identity comes from the reference.

Sources: [Krea 2 style transfer (developer docs)](https://www.krea.ai/docs/developers/krea-2/style-transfer), [Krea 2 deep dive walkthrough](https://www.krea.ai/blog/krea-2-deep-dive-walkthrough)

## 12. Let moodboards carry the visual direction

A moodboard is a saved collection of images sharing a creative direction — palette, texture, style, mood, composition. Krea calls moodboards "the most precise way to set a visual direction in Krea 2," and the system reasons over the whole set (style transfer plus clustering and custom LLMs), capturing concepts, characters, expressions, and atmosphere rather than just surface style.

When a moodboard carries the look, **the text prompt can be short and purely subject-focused**. Krea's own moodboard examples are one-liners:

> a flying whale with small fish swimming around her in the air

> extreme close-up of a jaguar's mouth with chromed teeth, side view

Moodboard strength ranges from −0.5 to 1.5, with 0.35 as the documented starting point (API: one moodboard per request; combining a moodboard with style references costs only the moodboard rate).

Moodboard analysis produces three usable outputs:

- **Taste profile** — a high-level summary of the direction, useful as a mirror of your own taste.
- **Keywords** — style tags applied automatically.
- **Avoids** — an underrated negative-steering list: qualities the board says you *don't* want, encoded as a control rather than prompt prose.

Mental model: style references transfer a precise look; a moodboard hands the model a vibe and sees what it does with it. Krea's intended pipeline is **explore → refine with style references → lock in an aesthetic universe with a moodboard**, though each works standalone.

Source: [Krea 2 moodboards (developer docs)](https://www.krea.ai/docs/developers/krea-2/moodboards), [Krea 2 deep dive walkthrough](https://www.krea.ai/blog/krea-2-deep-dive-walkthrough)

## 13. Use trained styles and LoRAs correctly

Krea supports trained LoRA "styles" (including character LoRAs) on every Krea 2 variant, including Turbo. Two rules matter when a style is active:

1. **Keep the prompt about content, not style.** Style words in the prompt fight the LoRA. Describe the subject, scene, composition, and light; let the LoRA supply the aesthetic.
2. **Use the exact trigger phrase.** Officially released Krea 2 style LoRAs each have one:

| LoRA | Trigger phrase |
|---|---|
| Darkbrush | monochrome ink wash style |
| Dotmatrix | monochrome stippling style |
| Kidsdrawing | naive expressive sketch style |
| Neondrip | textured abstract style |
| Rainywindow | rainy window style |
| Retroanime | purple retro anime style |
| Softwatercolor | art deco watercolor style |
| Sunsetblur | ethereal motion blur style |
| Vintagetarot | vintage tarot style |

For character consistency work (e.g., recurring portrait subjects), a character LoRA plus a fixed seed beats re-describing the person in every prompt — the prompt then only needs pose, wardrobe, setting, light, and framing.

Self-hosting notes from the ComfyUI community: all official LoRAs were trained on the Raw checkpoint and apply cleanly to Turbo. A popular quality trick is running Raw with the Turbo LoRA at ~0.6 weight and ~12 steps instead of 8. LoRA strength itself is also the reliable numeric emphasis control — a substitute for the prompt-weighting syntax that the Qwen3VL encoder does not support (section 8).

Sources: [ComfyUI prompt & style guide](https://www.instasd.com/post/krea-2-prompt-and-style-guide-comfyui), [Krea 2 developer overview](https://www.krea.ai/docs/developers/krea-2/overview)

## 14. Quote exact text that must appear

When an image must contain visible words, place the exact wording in quotation marks:

> A small red neon sign above the diner entrance reading "OPEN ALL NIGHT."

Also describe placement, hierarchy, and typography:

> A minimalist cream book cover with the title "THE QUIET CITY" centered in large condensed black sans-serif letters and the author name "MARA VOSS" in small uppercase letters along the bottom edge.

Krea's official prompting guide explicitly recommends quotation marks for rendered text, and the technical report confirms text rendering was a first-class training objective (OCR-informed captions, text-density filtering, and a dedicated text-rendering reward). Official example phrasing embeds the typography as a described attribute: "hand-lettered sans-serif typography reading 'run wild.'"

Calibrate expectations: text rendering is a genuine strength of Krea 2, but community testing places it between SDXL and Ideogram — reliable for signs, labels, and short runs of text; weaker for long poster headlines. Keep required text short, spell it once (do not list alternative spellings), and let the typography description do the styling.

Do not add several alternative spellings or repeat the desired text.

## 15. Keep one prompt internally consistent

Before generating, look for conflicts:

- Close-up versus full-body view
- Empty room versus a crowd
- Noon sunlight versus nighttime
- Flat vector art versus detailed oil-paint texture
- Frozen motion versus strong motion blur
- Minimal composition versus densely packed objects
- Front view versus profile view

If competing qualities are intentional, explain their relationship:

> A minimal composition containing one intricately decorated ceremonial mask.

That is clearer than asking for a "minimal, extremely complex composition."

The community's version of this rule, from the "no one weird trick for prompting Krea 2" discussion:

- **Internal stylistic consistency matters more than magic words.** A prompt mixing three eras and four media fights itself.
- **Use real terms of art.** Name actual styles, media, and techniques ("ukiyo-e woodblock print," "risograph," "ligne claire," "contrapposto") rather than approximating with vague adjectives.
- **Avoid purple prose.** Overwrought flowery language does not improve results; concrete visual statements do.
- **Iterate frequently.** No single prompt formula produces great results — small, frequent revisions beat one "perfect" prompt.

Sources: [r/StableDiffusion: no one weird trick for prompting Krea 2](https://www.reddit.com/r/StableDiffusion/comments/1vd2ct3/theres_no_one_weird_trick_for_prompting_krea_2/), [r/StableDiffusion: Krea 2 prompt adherence](https://www.reddit.com/r/StableDiffusion/comments/1ujid04/krea_2_prompt_adherence/)

## 16. Iterate one variable at a time

When refining an image:

1. Preserve the successful parts of the prompt.
2. Identify the single biggest mismatch.
3. Rewrite that aspect positively and concretely.
4. Keep the seed when comparing prompt changes.
5. Generate again (batches of up to 4 and compare).
6. Change another variable only after evaluating the first.

A practical progression is:

- Version 1: broad concept
- Version 2: add composition
- Version 3: refine lighting
- Version 4: refine medium or texture
- Version 5: make small subject-specific corrections

This makes it possible to understand which instruction changed the result.

The variant-aware version of this loop: iterate cheaply on Turbo (fast, 2 credits, batch of 4), then re-run the winning prompt and settings unchanged on Medium or Large for the final render. The style system, sliders, seeds, and creativity behave the same across variants, so settings transfer directly.

## 17. Long-form photography and portrait prompts

Krea 2 Large is the photorealism variant, its expander deliberately biases photographic requests toward photographic language, and it is documented to reward long, dense, paragraph-level description. This is the guide's flagship pattern: a length target, a sentence plan for a long-form photoreal prompt, the vocabulary that fills it, and a worked example.

### Length target

One cohesive paragraph. The official repo examples run roughly 25–100 words; a fully art-directed production prompt typically lands between 150 and 300 words. There is no prize for length itself — the encoder parses sentences and ignores boilerplate — so density means every sentence carries visual information. At Creativity Raw/Low, whatever you do not write does not exist in the image.

### The sentence plan

Write, in order, one or two sentences for each:

1. **Medium and shot type** — "waist-up three-quarter portrait photograph," "close-up macro photograph," "cinematic editorial photograph."
2. **Subject identity and role** — who or what, plus demeanor. When a character LoRA or reference carries the appearance, stop at name, role, and expression; do not describe the face.
3. **Pose with grounded anatomy** — torso angle, gaze, hand positions, grip, body orientation.
4. **Wardrobe and materials** — every garment with its surface behavior: weave, matte or sheen, stitching, grain.
5. **Hands, props, and grip** — the prop's material and finish, how the fingers hold it, where it sits in the frame.
6. **Mid-ground and background** — explicitly described; community testing shows this measurably improves adherence.
7. **Composition** — viewpoint, framing, subject placement, depth of field.
8. **The lighting sentence** — source, direction, quality, and what it does to the surfaces named above.
9. **Palette and finish** — restrained color list, skin and fabric realism, lens or film cues.

### Vocabulary that reliably works

Patterns drawn from Krea's own examples and fal.ai's guide:

**Lead with the photographic medium and shot type:**

> Close-up macro photograph of a lower eyelid and cheek, extreme proximity revealing every pore.

> Cinematic portrait photography, studio shot, model with closed eyes and head tilted back.

**Describe light like a photographer** — source, direction, quality, and what it does:

> Cold blue daylight mixing with warm tungsten bulbs overhead, wet reflective concrete floor.

**Use concrete skin and surface vocabulary** rather than quality boosters: "natural skin texture," "every pore," "dense black spots," "vibrant orange sticky toes."

**Name lens and format cues when they matter:** "macro lens," "shallow depth of field," "35 mm film grain," "medium format." Krea 1's official docs give the same advice: "shot on 35mm," "golden hour," specific lighting beats generic adjectives.

**Anchor on photographers, directors, or publications when appropriate:**

> Photographed in the style of Tim Walker.

> Cinematography in a film in the style of Zhang Yimou and Raise the Red Lantern.

**Embrace imperfect-realism cues on Large:** "slight motion blur on his hands," "film grain," "low dynamic range" — the variant is specifically trained toward these raw textures, and the model will not "clean them up."

**For posed portrait work**, specify grounded anatomy and spatial facts — hand positions, grip, gaze direction, body orientation, wardrobe seams and accessories, what is in the frame — exactly as in the template example below. Fine hair detail is a reported soft spot (section 18); tight crops and explicit hair/lighting description help.

### Worked example

A ~280-word production prompt following the sentence plan (uniformed waist-up portrait with a precise prop pose; appearance carried by a character LoRA, so identity is name, role, and demeanor only — see section 13):

> A waist-up three-quarter portrait photograph of Hana Park, a Chinese female sheriff. She stands with her torso turned at a natural three-quarter angle while her face turns toward the camera, her posture upright and her expression serene, attentive, and quietly authoritative. She wears the Graystone Sheriff's Department uniform: a neatly pressed tan long-sleeved cotton shirt with a fine visible weave and dark brown epaulettes, a straight brown necktie with a matte surface, a fitted black leather duty belt with a subtle sheen and precise edge stitching, and brown jodhpur uniform trousers beginning at the lower edge of the frame. Her right hand is raised beside her right shoulder with the palm facing inward. She pinches the top link of a short steel handcuff chain between the tips of her right thumb and index finger, her grip light. The chain drops vertically from her fingertips, entirely in front of her hand, with both empty steel cuffs hanging freely below her fingers at two slightly different heights, their brushed metal surfaces catching cool institutional reflections. Her right wrist remains clearly visible above and behind the dangling cuffs, while her left arm rests naturally beside her torso. Behind her, the softly focused interior of a secure prison corridor recedes into gray concrete walls, barred cell doors, and steel fixtures, blurred by a shallow depth of field that isolates her as the focal point. Eye-level composition with the raised hand and both cuffs fully inside the frame. The lighting is soft and diffused, a gentle key light from above and slightly left falling across her face, a subtle cool rim light along her silhouette, and a restrained tan, brown, and steel-gray palette of polished cinematic law-enforcement profile photography.

Note what it does: every sentence maps to a step of the plan, no boilerplate or quality tags appear, the light is named with a direction, and the background and mid-ground are described rather than assumed.

Sources: [fal.ai Krea 2 prompting guide](https://fal.ai/learn/tools/krea-2-prompting-guide), [Krea 1 prompting docs](https://www.krea.ai/docs/user-guide/features/krea-1), [Krea 2 technical report](https://www.krea.ai/blog/krea-2-technical-report)

## 18. Known weaknesses and how to prompt around them

- **Fine texture detail (e.g., hair)** can struggle, per community testing of CivitAI-style prompts. Countermeasures: larger subject scale in frame, explicit hair and lighting description, or graduate to Large and upscale.
- **Long headline text** is weaker than short signs and labels — keep required text short and quoted (section 14).
- **Precise structured compositions and exact anatomical accuracy** are not Krea 2's forte (carried over from Krea 1's documented tendencies) — lock composition with explicit spatial language and use Creativity Raw/Low when layout must hold.
- **Turbo for finals** — fast but not intended for final photorealistic production or maximum consistency across a campaign set; use Medium/Large for finals.
- **Prompt-weighting syntax** `(word:1.2)` is unsupported and degrades output — use order, restatement, and specificity instead (section 8).
- **Keyword confetti is dead weight** — the encoder ignores it; spend the tokens on light, texture, and spatial relationships instead.

Sources: [r/comfyui: Krea 2 prompts from CivitAI creators](https://www.reddit.com/r/comfyui/comments/1uixdzs/krea_2_some_prompts_of_civiais_creators_in_krea_2/), [Krea 1 prompting docs](https://www.krea.ai/docs/user-guide/features/krea-1), [Krea 2 Turbo docs](https://www.krea.ai/docs/user-guide/features/krea-2-turbo)

## Reusable Krea 2 prompt template

> A **[medium]** showing **[primary subject with defining attributes]** **[performing an action]** in **[setting and time]**. **[Other subjects and their explicit relationships]**. **[Shot size, viewpoint, placement, and depth]**. **[Light source, direction, softness, and atmosphere]**. **[Color palette]**. **[Stylistic treatment, materials, and texture]**. **[Exact visible text in quotation marks, if required]**.

Example:

> An editorial photograph showing a ceramic artist with cropped silver hair examining a newly glazed cobalt-blue vase in a small whitewashed studio. She holds the vase at chest height and looks down at its surface; shelves of unfinished pottery recede softly behind her. Medium three-quarter portrait at eye level, subject placed slightly left of center. Cool morning light enters through a large window on the right, creating soft reflections on the glaze and gentle shadows across the room. Restrained white, clay, and deep-blue palette, natural skin texture, subtle 35 mm film grain, quiet contemplative mood.

Minimal formula when iterating fast (Turbo, or any variant with a moodboard/style carrying the look):

> **[Subject] + [one action] + [where the light comes from] + [one or two textures]**

## Instructions for an AI that writes Krea 2 prompts

The following text can be used as a reusable system instruction:

```text
Write one standalone Krea 2 image prompt for each requested image. Default to photorealistic photography and to long, dense, fully art-directed prompts: one cohesive paragraph, roughly 120–300 words for a single subject, in which every sentence adds visual information. Never pad with boilerplate, and never leave gaps — at low-expansion settings, anything not written does not exist in the image.

Before writing, determine the subject, action, mood, medium, composition, framing, lighting, and grounded visual details. Internally consider two or three suitable visual directions and select the one that best serves the request. Keep this planning internal; do not output reasoning, planning tags, or alternative drafts.

Each prompt must contain all information needed to generate that image independently. Never refer to another prompt, a previous image, prior context, or “the same” subject. Repeat every continuity-critical character, product, setting, palette, and style detail in each prompt.

Describe the desired visible result positively. Do not write absence-based instructions such as “no people,” “no blur,” “without text,” or “don’t change.” Replace them with positive visual states such as “an empty landscape,” “tack-sharp focus,” “a blank unprinted surface,” or a direct description of the intended result. If an unwanted element does not need a replacement, omit it entirely.

Use cohesive natural language, not keyword soup, quality tags, JSON, or commentary. The model parses full sentences: spatial relationships, possessives, and counts are understood, while boilerplate quality tokens are ignored. Do not use token-weighting syntax such as (word:1.2). Establish emphasis through order (most important subject first), restatement, and specificity. Include exactly one action per subject, always name the light source and its direction, and add at most a few deliberate textures.

Build the paragraph in this order: photographic medium and shot type; subject identity and role; pose with grounded anatomy; wardrobe and materials with their surface behavior; hands, props, and grip; explicitly described mid-ground and background; composition and framing; a complete lighting sentence naming the source, direction, quality, and its effect on the surfaces named above; restrained color palette; lens, film, or finish cues. Omit physical appearance descriptors whenever a character LoRA, style reference, or moodboard carries the subject's look — spend that length on wardrobe, environment, and light instead.

Group every subject with its own attributes and actions. State important positions and interactions explicitly. Preserve all user-specified subjects, actions, colors, relationships, and artistic media. Do not invent unnecessary objects, clothing, colors, or props.

If the user's input is already detailed, lightly polish and finalize it instead of heavily expanding or replacing its language and direction. Preserve any explicitly requested medium, including photography, illustration, painting, sketch, or 3D rendering.

Resolve contradictions before writing. Use concrete, visually observable language and genuine terms of art for styles and media. Describe poses through grounded anatomy and spatial relationships: identify the hand, fingers, grip, body orientation, object position, and placement inside the frame whenever these details matter. Treat depictions of people with dignity and use respectful, neutral descriptions of the human form. If visible text is requested, reproduce the exact wording once inside quotation marks and specify its placement.

Return only the finished prompt or prompts. When returning multiple prompts, label them outside the prompt text, but ensure every individual prompt remains fully standalone.
```

## Final checklist

Before using a prompt, confirm that:

- It works without previous conversation or images.
- The right variant is chosen for the goal (Turbo to iterate, Medium for illustration, Large for photoreal finals).
- It is a dense single paragraph: named light source, camera and lens cues, material micro-texture, and a described mid-ground and background.
- Physical appearance is left to the character LoRA or reference when one is active.
- It states what should be visible rather than listing unwanted elements.
- The main subject and action are immediately clear, one action per subject.
- A light source and its direction are named.
- Attributes are attached to the correct subject.
- Important spatial relationships are explicit.
- Medium, composition, lighting, and style agree with one another.
- Every detail serves the image; no keyword confetti or weighting syntax.
- Exact rendered text is quoted once.
- Style vocabulary is omitted when a style reference, moodboard, or LoRA carries the look (or reduced to its trigger phrase).
- Multiple prompts repeat all continuity-critical details.
- The prompt is one coherent visual description, not production commentary.

## Sources

Official:

- [Official Krea 2 prompting guide](https://github.com/krea-ai/krea-2/blob/main/docs/prompting.md)
- [Official Krea 2 prompt-expansion instructions](https://github.com/krea-ai/krea-2/blob/main/docs/expansion.txt)
- [Krea 2 technical report](https://www.krea.ai/blog/krea-2-technical-report)
- [Krea 2 docs: Medium & Large](https://www.krea.ai/docs/user-guide/features/krea-2)
- [Krea 2 docs: Turbo](https://www.krea.ai/docs/user-guide/features/krea-2-turbo)
- [Krea 2 developer overview](https://www.krea.ai/docs/developers/krea-2/overview)
- [Krea 2 developer docs: generative sliders](https://www.krea.ai/docs/developers/krea-2/generative-sliders)
- [Krea 2 developer docs: style transfer](https://www.krea.ai/docs/developers/krea-2/style-transfer)
- [Krea 2 developer docs: moodboards](https://www.krea.ai/docs/developers/krea-2/moodboards)
- [Exploratory prompting in Krea 2](https://www.krea.ai/blog/explorative-prompting-krea-2)
- [Krea 2 deep dive: exploration, style references, and moodboards](https://www.krea.ai/blog/krea-2-deep-dive-walkthrough)
- [Introducing Generative Sliders](https://www.krea.ai/blog/generative-sliders)
- [Krea prompt-engineering reference](https://github.com/krea-ai/skills/blob/main/krea-generate/references/prompt-engineering.md)
- [Official Krea 2 sampling implementation](https://github.com/krea-ai/krea-2/blob/main/sampling.py)
- [Krea 1 prompting docs](https://www.krea.ai/docs/user-guide/features/krea-1)

Third-party and community:

- [fal.ai Krea 2 prompting guide](https://fal.ai/learn/tools/krea-2-prompting-guide)
- [ComfyUI Krea 2 prompt & style guide (InstaSD)](https://www.instasd.com/post/krea-2-prompt-and-style-guide-comfyui)
- [r/StableDiffusion: there's no one weird trick for prompting Krea 2](https://www.reddit.com/r/StableDiffusion/comments/1vd2ct3/theres_no_one_weird_trick_for_prompting_krea_2/)
- [r/StableDiffusion: Krea 2 prompt adherence](https://www.reddit.com/r/StableDiffusion/comments/1ujid04/krea_2_prompt_adherence/)
- [r/comfyui: Krea 2 prompts from CivitAI creators](https://www.reddit.com/r/comfyui/comments/1uixdzs/krea_2_some_prompts_of_civiais_creators_in_krea_2/)
