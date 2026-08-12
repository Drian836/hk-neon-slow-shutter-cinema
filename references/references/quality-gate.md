# Quality Gate

Inspect the actual raster before returning it. Check at full view for identity, motion causality, anatomy, light, and space; check at thumbnail view for focal hierarchy, palette control, and domain drift.

## Binary Preflight Gates

Run these before scoring. Any triggered hard gate prevents a pass.

### Anti-Grade Gate

Mentally remove or ignore palette shifts, exposure, contrast, grain, halation, bloom, vignette, wetness, and generic blur. For a requested style or location transformation, the result must still show at least two substantive changes among:

- environment semantics and locale evidence;
- human circulation or relational blocking;
- foreground/subject/background structure;
- camera distance, angle, crop, or lens consequence;
- temporal behavior and stable-versus-moving roles;
- practical-light geometry and the surfaces it reaches.

If fewer than two remain, label `GRADE_ONLY_FAIL`. This is a Hard Fail for transformation requests even when the palette is attractive.

### Explicit Time Gate

When the user explicitly requests slow shutter, step printing, 抽帧, 拖影, or visible slow-motion feeling, the raster must show:

1. a readable stable or partly stable anchor;
2. a second apparent clock;
3. motion with a coherent direction;
4. for step-printed intent, uneven or broken temporal residue rather than one smooth software blur;
5. camera-subject-world relation that explains which plane smears.

Missing visible time behavior is a Hard Fail. Color, darkness, rain, grain, and bokeh cannot compensate.

### Visual-Family Gate

The selected family must be recognizable from non-color behavior: humid material stillness, two-clock urban flux, close wide-angle estrangement, restrained repeated obstruction, or cramped relational instability. If only the palette points to the family, it fails this gate.

## Generated Image Checks

### Domain And Period

- The image feels like a lived-in late-1980s-to-around-2000 Hong Kong urban moment rather than a futuristic city, generic Asian street, or costume set.
- Environment participates in the story through working surfaces, circulation, transport, architecture, reflection, or occlusion.
- Period cues are limited, plausible, and mutually consistent.
- The result avoids generic cyberpunk, rainbow neon, synthetic fog, mandatory wet streets, sterile malls, and contemporary luxury advertising.

### Subject And Character

- The emotional subject is immediately findable and remains readable.
- Face, body, hands, and object interaction are anatomically plausible.
- The subject is embedded in the location rather than separately studio-lit or pasted over blur.
- Wardrobe and pose fit the action, period, and requested preservation constraints.

### Motion And Time

- Stable information and moving information are visibly distinct.
- Motion has a clear direction and agrees with the subject, crowd, vehicle, camera, and road geometry.
- The face or required identity zone remains readable when identity matters.
- Temporal smear, edge echo, or light streaks are spatially selective and physically attached to motion.
- The image avoids uniform full-frame blur, radial software blur, transparent clones, duplicated faces, and floating light trails.
- Still Tension outputs remain in the family through suspended time, layered space, practical light, grain, and emotional distance even without obvious blur.
- Explicit step-printed outputs show uneven cadence, partial edge echoes or broken smears, and source-linked segmented traces while retaining a readable anchor.
- Smooth long-exposure trails and conventional slow-motion softness are not mislabeled as step printing.

### Composition And Space

- The selected composition family is visible in the raster.
- Foreground, subject plane, and background have a believable relationship when the scene supports layers.
- Occlusion or reflection clarifies distance or emotion rather than hiding essential information.
- Wide-angle distortion supports distance-in-proximity without turning faces into caricatures.
- The result avoids centered commercial portraiture, empty bokeh backgrounds, perfect symmetry by default, and accidental destructive crops.

### Light And Color

- One dominant practical source explains most of the illumination.
- One secondary source and at most one small accent remain subordinate.
- Color contamination lands on plausible skin, glass, metal, wall, road, or clothing surfaces.
- Neon or signage is localized and architectural, not a full-frame rainbow effect.
- Deep shadows retain selective information around faces, hands, clothing, or architecture.
- The result avoids clean orange-teal grading, perfect HDR, studio rim light, and beauty retouching.

### Film Reproduction

- Grain, halation, exposure imperfection, focus falloff, and color bleed feel integrated rather than added as a uniform filter.
- Practical highlights may bloom slightly without turning every bright edge into glow.
- The image avoids perfect digital sharpness and overprocessed clarity while retaining the focal information.

## Photo Input Preservation

Apply when Photo Input Mode is used:

- Every input has an explicit role and preservation matrix by layer.
- Every image meant to affect generation was passed into the generation call.
- High-preservation identity, facial structure, hair, body proportions, wardrobe when required, product geometry, object count, silhouette, pose, and interaction have not drifted materially; lower-preservation environment and text are not accidentally frozen.
- Motion and wide-angle treatment affect the environment more strongly than the identity zone unless the user permits otherwise.
- Reference-only inputs contribute only requested grammar and do not reappear as copied subjects, text, brands, or compositions.
- The final response reports role, preservation level, invariants, and any unresolved limitation.
- Source-locale residue does not contradict the target Hong Kong scene unless explicitly preserved.
- The Anti-Grade Gate passes independently of identity preservation.

## Poster Checks

Apply in Poster Mode:

- Source references were classified as frame/photo, official poster, fan/editorial redesign, or provenance-uncertain.
- Cinematography claims do not come from poster design alone.
- Thumbnail hierarchy has one dominant image/title relationship.
- User-supplied bilingual wording is legible, deliberately aligned, and limited to a clear hierarchy.
- Image behavior, typography, and print texture form one system rather than three overlays.
- The result does not copy a title lockup, actor, exact frame, logo, laurels, credits, watermark, product packaging, or whole reference layout.

## Reference Analysis Checks

- Every factual visual claim comes from an inspected file, its metadata, or a clearly cited reported source.
- Observed, inferred, and reported evidence remain distinguishable.
- Fixed rules are supported by recurrence or clearly labeled as user-required.
- Variable rules reflect observed variation or are labeled proposed safe variation.
- Actors, exact costumes, text, brands, landmarks, and one-shot arrangements remain sample residue.
- Transfer, restoration, crop, and sample-size limitations are stated where relevant.
- Reusable rules describe visible behavior rather than only naming a director, film, genre, or mood.

## Prompt-only Checks

- The prompt follows the compiler field order and three- or four-paragraph shape.
- It defines scene, subject, action, emotion, composition, motion roles, practical light, color relationship, environment, film reproduction, and relevant avoids.
- It does not rely on filmmaker names or vague prestige adjectives.
- The response does not imply that an image was generated or inspected.

## Failure Levels

### Hard Fail

- generic cyberpunk or wrong visual domain;
- identity loss or major product-geometry drift;
- severe anatomy or interaction failure;
- uniform full-frame blur or no readable subject;
- motion direction contradicts action or traffic;
- copied actor, exact reference shot, brand, subtitle, or watermark;
- glossy commercial advertising or studio beauty portrait;
- implausible period/location cues that dominate the image.
- `GRADE_ONLY_FAIL` on any requested style or location transformation;
- no visible time signature when explicit slow-shutter, step-print, 抽帧, 拖影, or slow-motion behavior was requested;
- poster references treated as proof of camera or shutter technique;
- copied or invented official-looking title lockup, logo, laurels, credits, or watermark.

### Soft Fail

- motion is too weak but still coherent;
- palette is slightly too clean or accent is too large;
- grain or halation is underexpressed;
- spatial layering is shallow;
- environment is plausible but generic;
- shadow information is slightly limited;
- emotional relation is present but not strong.

## Scored Acceptance

After binary gates pass, score 100 points:

| Layer | Points |
| --- | ---: |
| Hong Kong and requested-period evidence | 20 |
| non-color scene transformation | 15 |
| temporal or suspended-time grammar | 15 |
| composition, obstruction, and spatial layers | 10 |
| practical-light causality | 10 |
| film/print reproduction and emotional distance | 15 |
| identity, pose, aspect, and anatomy preservation | 15 |

Pass requires **75 or more** and no Hard Fail. For generation without a photo target, reassign the last 15 points to subject readability/anatomy (10) and compliance with requested ratio/text constraints (5). For Poster Mode, score its image layer with this table, then require every Poster Check separately.

## Bounded Repair

If a central check fails:

1. Name the failed layer: domain, visual family, identity, transformation depth, motion/time, composition, light/color, environment, film/print reproduction, or poster hierarchy.
2. Keep the successful recipe decisions unchanged.
3. Tighten only the failed layer with concrete pixel behavior.
4. Regenerate once at most.
5. Inspect again. If the second result still fails, return the better result and state the remaining limitation; never describe failed preservation or QA as successful.

Repair priority:

1. identity, anatomy, and requested invariants;
2. binary Anti-Grade and Explicit Time gates;
3. correct visual domain, family, and period;
4. readable focal subject;
5. motion causality, camera relation, and spatial relationship;
6. practical-light and palette control;
7. film/print texture and secondary mood refinements.

If identity fails, tighten identity only. If transformation depth fails, keep identity constraints unchanged while loosening environment/composition preservation and strengthening blocking, space, camera, or time. Do not solve a structural failure by adding saturation, grain, rain, or more generic blur.
