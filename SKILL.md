---
name: hk-neon-slow-shutter-cinema
description: "Generate, transform, prompt, analyze, or design lived-in Hong Kong urban cinema images and posters from late-1980s-to-around-2000 visual grammar: discontinuous step-printed time, subject-versus-world speed contrast, close wide-angle spatial estrangement, restrained corridor blocking, humid interiors, provisional rooms, handheld or tracking camera presence, practical mixed light, layered obstruction, and imperfect film or print reproduction. Use for 港风电影感, 王家卫感, 香港电影海报, 阿飞正传, 重庆森林, 堕落天使, 花样年华, 春光乍泄, 90年代香港, 抽帧慢门, step-printing, slow shutter, slow-motion feeling, temporal smear, cinematic photo restyling, reference analysis, prompt-only output, or coherent visual batches."
---

# HK Neon Slow-Shutter Cinema

Translate natural-language content or visual references into an executable Hong Kong urban-cinema grammar. Treat filmmaker or film-title names as intent signals only; compile the result from visible scene, motion, lens, light, color, spatial, and film-reproduction behavior.

Prioritize decisions in this order: emotional situation and relationship, time behavior, camera-subject-space relationship, practical light, then color and film texture. Color grading alone never satisfies the Skill.

Unless the user explicitly asks for analysis or prompt-only output, return both the final image-generation prompt and the generated raster image.

## Route The Request

Choose the smallest mode that satisfies the request:

- **Generate Mode — default:** a theme, person, action, emotion, story beat, object, or scene becomes a new cinema frame.
- **Photo Input Mode — Generate subflow:** a supplied photograph must affect the output; classify its role, record preservation invariants, pass the actual image into generation, and compare the result with the source.
- **Reference Analysis Mode:** screenshots, stills, photographs, or a folder are supplied for analysis or system extraction; inspect them and return evidence-based rules without generating unless asked.
- **Poster Mode:** the user asks for poster, key art, cover, title layout, print design, or supplies poster references for design extraction. Keep cinematography evidence separate from graphic-design evidence.
- **Prompt-only Mode:** use only when the user explicitly asks for the final prompt without image generation.
- **Analyze + Generate Mode:** extract a visual system from supplied references, then generate a new subject and composition from that system.

When the user says “做一张”, “生成”, or an equivalent phrase, default to Generate Mode. Do not ask for choices that can be inferred safely from content and emotion.

## Load The Relevant References

- Read `references/style-system.md` in every mode.
- Read `references/visual-families.md` in every mode and select one primary family from content rather than averaging film-title cues.
- For Generate and Prompt-only modes, read `references/scene-system.md`, `references/motion-system.md`, `references/lighting-color-system.md`, `references/composition-system.md`, `references/variation-engine.md`, and `references/prompt-compiler.md`.
- Read `references/poster-system.md` in Poster Mode or whenever poster/key-art references appear. Do not route an ordinary film-frame request through poster typography.
- Read `references/character-system.md` whenever a human, recognizable product, pet, artwork, or supplied photograph appears.
- Read `references/reference-analysis.md` whenever visual references are supplied for analysis or style learning.
- Read `references/quality-gate.md` before returning a generated image, prompt-only result, or reference analysis.

## Visual And Source Boundaries

- Build from abstract visual behavior, not a director name, film title, actor, or copied shot.
- Do not require `Wong Kar-wai style`, `cinematic`, `masterpiece`, or similar labels in the final prompt. Replace them with visible decisions.
- Inspect every supplied image before claiming dimensions, ratio, subject, color, motion, light, or composition.
- Separate observation from interpretation. Treat transfer, restoration, crop, and screenshot uncertainty explicitly.
- Do not copy actors, identities, exact costumes, brands, signs, subtitles, watermarks, exact locations, or exact compositions from reference-only images.
- Do not treat a single film prop or one restored color grade as a fixed style rule.
- Classify supplied material as film frame/photo, official poster, fan/editorial redesign, or provenance-uncertain before extracting rules. Posters may support layout and print analysis but never prove shutter, lens, or on-set lighting behavior.
- If a source is missing or unreadable, state the limitation rather than inventing evidence.

## Photo Input Mode

Assign each supplied image one role:

- **Edit target:** its recognizable subject must appear in the result.
- **Reference image:** learn only requested traits such as motion, color, light, composition, texture, or mood.
- **Supporting insert:** carry one specified person, object, garment, texture, or fragment into a new scene.

Infer the least destructive role:

- “把这张人物照片做成港风电影画面”, “保留这个人/产品/宠物” → edit target.
- “只参考这些图的慢门、颜色或构图” → reference image.
- “把图里的这个人或物放进去” → supporting insert.
- A supplied photograph plus only “做一张” → edit target.

Assign preservation by layer rather than giving the whole frame one level:

- **Subject identity:** High by default for identifiable people, pets, products, characters, and artworks.
- **Action and interaction:** High when pose, gaze, hand contact, or relationship is central; otherwise Medium.
- **Wardrobe and carried objects:** High only when requested or recognition-critical; otherwise Medium.
- **Composition and camera position:** Medium by default; High only when the user explicitly asks to preserve framing or exact geometry.
- **Environment and location:** Low when the user asks to move the subject into a new Hong Kong setting; Medium when route, perspective, or room type should remain; High only for an explicit exact-location edit.
- **Existing text and signs:** preserve only when explicitly required. Otherwise remove, obscure, or replace with non-focal, non-readable period-appropriate shapes when the source text contradicts the requested location.
- **Aspect ratio:** preserve the source ratio unless the user requests another.

High subject preservation does not imply High preservation of the source background, text, composition, or lighting. For “把这张人物照片做成香港电影画面,” default to Subject High / Action High or Medium / Composition Medium / Environment Low / Text Low / Aspect exact.

Run the photo subflow:

1. Inspect each image and record visible invariants by layer.
2. Separate what must remain, what may change, and what may be introduced. Declare a scene-transformation budget independently from identity preservation.
3. Pass the actual source into the built-in image-generation tool. Use `referenced_image_paths` when every target has a local path. Use `num_last_images_to_include` only when at least one target exists solely in the conversation, selecting the smallest number that includes all targets, up to five. Never use both mechanisms in one call.
4. Compile subject invariants before stylistic changes, but do not preserve unrequested locale residue. Require at least two visible changes beyond global color/exposure/texture when a style or location transformation is requested: environment semantics, circulation/blocking, spatial layers, lens/crop behavior, temporal behavior, or practical-light geometry.
5. Generate, inspect, and compare with the source.
6. If identity fails, tighten only the subject layer. If the result is grade-only, loosen only environment/composition preservation and strengthen time/space behavior. Regenerate at most once.

## Generate Workflow

1. **Parse intent.** Identify subject, action, relationship, time, place cues, emotional temperature, requested text, image roles, and hard constraints.
2. **Select a visual family.** Follow `references/visual-families.md`. Choose one primary family from action and relationship; optionally borrow one supporting device. Never average all films into one green-red neon grade.
3. **Interpret scene.** Choose a plausible late-1980s-to-around-2000 Hong Kong urban setting that supports the action and emotion. When borrowing grammar from a film set elsewhere or in another era, transfer the relationship and camera logic, not its literal costume, décor, or geography.
4. **Interpret time and emotion.** Decide whether time should feel rushed, suspended, discontinuous, remembered, intimate, or still. For explicit slow-shutter, slow-motion, step-printing, 抽帧, or 拖影 requests, require a visible discontinuous time signature; do not route to Still Tension unless the user explicitly asks for little or no blur.
5. **Select visual strategy.** Declare two apparent clocks when motion is requested, the stable anchor, camera-subject relationship, spatial mechanism, motion direction, irregular temporal residue, light-streak causality, practical-light hierarchy, and film reproduction. Color is selected only after these decisions.
6. **Select a variation recipe.** Follow `references/variation-engine.md`. Keep family identity while changing visual grammar.
7. **Compile the prompt.** Follow `references/prompt-compiler.md`; use three or four compact natural-language paragraphs made only of renderable decisions.
8. **Generate.** Use the built-in image-generation capability. Include the actual image inputs for Photo Input Mode.
9. **Inspect the actual raster.** Check full view and thumbnail view against `references/quality-gate.md`, including the transformation-depth and anti-grade gates, plus layered preservation invariants when applicable.
10. **Repair once when needed.** Target the failed layer only. Maximum one regeneration; if the second result still fails, return the better result and state the limitation.
11. **Return.** Include the image, final prompt, recipe, concise inspection note, and photo role/preservation details when applicable.

## Reference Analysis Workflow

1. Resolve and inspect every usable image; record metadata when available.
2. Describe observed evidence before interpreting mood or intent.
3. Analyze scene, subject state, motion roles, composition, practical lights, color relationships, environment, and film reproduction.
4. Separate fixed system, variable system, and sample residue.
5. State confidence and transfer/restoration limitations.
6. Return the structure in `references/reference-analysis.md`.
7. If generation is also requested, choose a new recipe and continue through Generate Mode without copying a source shot.

## Poster Workflow

1. Classify every supplied image by source type; keep film evidence and graphic-design evidence separate.
2. Select one poster family from `references/poster-system.md` and one image-layer visual family from `references/visual-families.md`.
3. Resolve exact aspect ratio, image hierarchy, user-supplied wording, bilingual hierarchy, safe text zones, and print behavior.
4. Generate a new layout and image arrangement; do not copy a reference title lockup, actor, frame, logo, laurels, credits, watermark, or product label.
5. Inspect both thumbnail hierarchy and full-size text/image integration using the poster quality checks and the general anti-grade gate.

## Variation Discipline

- Apply the adjacency, batch-size, and recipe de-duplication constraints in `references/variation-engine.md`; cosmetic swaps of subject, coordinate, or neon hue do not count as variation.
- Preserve the family through lived-in Hong Kong space, human-environment integration, practical mixed light, temporal or suspended-time behavior, layered depth, and imperfect film reproduction.
- Use only visible recent outputs or the supplied batch when avoiding repetition; do not claim memory outside the current context.

## Output Contracts

### Generate Mode

````markdown
**生成图**

![HK Neon Slow-Shutter Cinema](absolute-image-path-or-rendered-image)

**最终 Prompt**

```text
[final prompt used for image generation]
```

**说明**

- Mode: Generate
- Recipe: [visual-family / scene / time / subject-state / time-behavior / camera-subject-relation / composition / lighting / spatial-feeling / texture / emotion]
- Photo role: [edit target / reference image / supporting insert; omit when none]
- Preservation: [identity/action/composition/environment/text/aspect levels + main invariants; omit when none]
- Inspection: [pass, regeneration note, or concise limitation]
````

### Reference Analysis Mode

Return observed evidence, fixed system, variable system, sample residue, reusable rules, suggested variation, hard avoids, and confidence/limitations. Do not imply generation occurred unless it did.

### Prompt-only Mode

Return the final three- or four-paragraph prompt, recipe, and relevant hard avoids. Do not claim to have generated or inspected a raster.

### Poster Mode

Return the generated poster image, the final image-generation prompt, the selected poster family, the selected image-layer visual family, the supplied wording and bilingual hierarchy, the source classification for every reference, and a concise thumbnail/full-size inspection note. State explicitly when generated text is only approximate; never claim exact title or credit typography unless the final raster was inspected and the wording is actually legible.

## Non-Negotiable Outcome

A successful result feels like a lived-in Hong Kong urban moment in which environment, time, movement, camera distance, practical light, and emotional separation interact. If removing color, exposure, grain, and halation would leave essentially the source photograph unchanged, the result is a grade-only failure. It must not collapse into generic cyberpunk, uniform software blur, a glossy commercial portrait, or a copied movie still.

## Example Requests

- “用 $hk-neon-slow-shutter-cinema 做一个女生凌晨站在街角等人的画面。”
- “把这张人物照片做成九十年代香港慢门电影画面，人物必须一眼认出来。”
- “只参考这些截图的拖影方式和颜色，不复制人物与构图。”
- “分析这些剧照为什么有港风电影感，不要生成图片。”
- “一家夜间街边餐馆，两个人沉默坐着，不要明显慢门。”
- “做一张新的香港电影海报，只参考这些海报的倒影和中英文字级，不复制原片人物、标题或版式。”
- “只给最终生图 Prompt。”
