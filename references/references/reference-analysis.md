# Reference Analysis

Inspect the actual files before extracting rules. The goal is a reusable visual grammar, not praise, imitation, or a list of aesthetic labels.

## Evidence Pass

For every usable image, record or inspect:

- filename, available dimensions, ratio, crop, and visible player/subtitle contamination;
- source or transfer information when known;
- scene and period cues;
- subject count, identity sensitivity, pose, gaze, and interaction;
- stable information and moving information;
- motion direction, blur intensity, edge echo, camera movement, and practical-light streaks;
- foreground, subject plane, background, occlusion, reflection, and lens/spatial feeling;
- dominant practical light, secondary source, accent, white-balance conflict, and skin contamination;
- environmental details and signs of daily use;
- grain, halation, exposure, focus falloff, color bleed, and shadow detail;
- inferred emotional temperature;
- actor, exact costume, prop, brand, sign, subtitle, landmark, title, and exact composition that must remain sample residue.
- source class: film frame/photo, official poster/key art, fan/editorial redesign, or provenance-uncertain.

Use metadata for exact dimensions. Treat visual percentages, lens impressions, and shutter behavior as estimates unless source records support them.

## Evidence Labels

- **Observed:** directly visible in the pixels or metadata.
- **Inferred:** a plausible interpretation of emotion, lens feeling, light source, or motion process.
- **Reported:** supported by a cited interview, production note, release note, or other source supplied in the task.

Do not merge these labels.

Poster captions, tags, and fan descriptions are not reported cinematography evidence. A poster may be observed for layout, type, collage, and print behavior only. Verify camera, shutter, lens, frame-rate, lighting, or production claims through a film frame plus an authoritative reported source.

## Synthesis Rules

- Promote a trait to the fixed system only when it repeats across most usable references or is explicitly required by the user.
- Treat a changing trait that preserves family resemblance as variable.
- Keep one-off actors, costumes, objects, signs, locations, and compositions as sample residue.
- With one reference, report observations and proposed variations; do not claim collection-wide frequency.
- With fewer than three references, lower confidence in fixed palette, motion frequency, and composition rules.
- Different restorations, transfers, crops, displays, and screenshots can materially alter hue, contrast, grain, and ratio. Do not convert one transfer grade into a universal color rule.
- Separate the visual grammar of a historical setting from the production date. For example, a film made around 2000 but set in the 1960s must not make period costume a fixed rule for a 1990s output.
- When references mix films or photographers, identify cross-source recurrence before naming a fixed system.
- When references mix film frames and posters, synthesize two systems: an image/cinematography system and a graphic/poster system. Never let a poster's halftone, title type, mirrored portrait, or product collage become a fixed rule for ordinary film-frame generation.
- Do not copy source wording, actors, exact costumes, brands, watermarks, subtitles, exact dates, or shot compositions into the reusable prompt.

## Style Grammar Versus Sample Residue

Reusable grammar may include:

- stable subject against directional crowd motion;
- close wide-angle distance-in-proximity;
- foreground obstruction and deep lived-in space;
- localized fluorescent/tungsten/sign contamination;
- still tension in narrow repeated architecture;
- grain, halation, uneven exposure, and deep shadow;
- emotional distance expressed through blocking and circulation.

Sample residue may include:

- a recognizable actor or hairstyle;
- one film's signature wig, sunglasses, cheongsam, raincoat, motorcycle, or canned product;
- exact restaurant, mansion, stairwell, street sign, subtitle, date, or brand;
- an exact frame arrangement or color grade from one release.

## Output Structure

```markdown
## 风格名称
[specific Chinese and English name]

## 一句话总结
[one operational visual definition]

## Observed Evidence
- Files and metadata:
- Scene and period:
- Subject and interaction:
- Motion and time:
- Composition and space:
- Practical light and color:
- Environment:
- Film reproduction:

## Fixed System
[traits supported across the set]

## Variable System
[safe axes that preserve family resemblance]

## Sample Residue — Do Not Reuse
[source-specific identity, objects, text, and compositions]

## Reusable Rules
[concise scene, motion, composition, light, and reproduction rules]

## Suggested Variation
[new recipe that changes visual grammar]

## Reusable Prompt
[source-safe prompt template]

## Hard Avoids
[relevant negative constraints]

## Confidence / Limitations
[sample size, transfer uncertainty, unreadable files, and inference limits]
```

When analysis is followed by generation, use the fixed system as constraints, select a new combination from the variable system, and deliberately change the source composition.
