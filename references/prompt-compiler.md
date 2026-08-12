# Prompt Compiler

Compile only decisions that can become visible pixels. Begin with what physically exists in the frame, then describe how space, time, movement, light, color, and film reproduction affect it.

Do not start with an aesthetic label or filmmaker name.

## Field Order

Every final prompt must resolve these fields in order:

1. **Visual family, scene, and period feeling:** use the family internally; compile location, time, lived-in late-twentieth-century cues, and aspect ratio rather than a film title.
2. **Subject:** who or what appears, including preservation invariants when applicable.
3. **Action:** what the subject is physically doing.
4. **Emotional state:** express through behavior, distance, or attention rather than adjectives alone.
5. **Camera-subject relationship and composition:** camera proximity/height/movement, subject placement, foreground, subject plane, background, crop, and lens/spatial consequence.
6. **Motion and temporal behavior:** identify the stable anchor and the second apparent clock, then direction, blur intensity, cadence, edge residue, camera movement, and source-linked light streaks.
7. **Practical lighting:** source location and surfaces reached.
8. **Color relationship:** dominant source, secondary source, small accent, contamination, and shadow color.
9. **Environmental details:** two to five scene-specific details that support place and period.
10. **Film and optical reproduction:** grain, halation, exposure, focus, color bleed, and shadow information.
11. **Mood:** one concise emotional reading supported by the visible design.
12. **Relevant hard avoids:** only the risks likely for this recipe.

## Paragraph Shape

Write three or four compact natural-language paragraphs:

1. scene, period, subject, action, and emotional behavior;
2. layered image-input contract when applicable, camera-subject relationship, composition, spatial layers, and lens consequence;
3. stable anchor, second clock, direction, blur intensity, temporal cadence, partial edge residues, camera behavior, and moving practical lights;
4. practical lighting, color relationship, environment, film reproduction, mood, and concise hard avoids.

For Still Tension, paragraph 3 may be short and state that people and architecture remain stable while only one secondary element moves subtly.

## Base Template

```text
A [ratio if needed] frame in [specific lived-in Hong Kong scene] at [time], carrying late-1980s-to-around-2000 everyday details rather than a futuristic city. [Subject] is [action], with [visible emotional behavior and relationship].

Place the camera [distance, height, and movement relationship to the subject]. Place [subject] at [position and scale] in a [composition family]. Use [foreground element] to partially frame or occlude the scene, keep [subject plane] readable, and reveal [background plane]. The close/moderate/normal [spatial feeling] makes [visible near/far consequence].

Keep [stable anchor] comparatively stable and readable while [second clock] moves at a visibly different apparent speed. Let [moving information] travel [direction] with [blur intensity and form], [uneven or smooth cadence appropriate to the request], and [partial edge residue/camera behavior]. Attach [light streak behavior] only to [moving practical source].

Light the scene primarily with [dominant practical source from location], supported by [secondary source] and only a small [accent]. Let these sources contaminate [specific surfaces/skin/glass]. Include [environmental details]. Reproduce as [film behavior], with [shadow/highlight behavior], creating [mood]. Avoid [short relevant list].
```

Do not recite bracket labels in the final prompt.

## Photo Input Replacement

When an edit target or supporting insert is used, add this contract before stylistic changes:

```text
Use the supplied image as [edit target / supporting insert]. Preserve subject identity [High], action/interaction [High or Medium], wardrobe [High or Medium], camera/composition [Medium unless requested], environment [Low for a new Hong Kong location], source text [Low unless requested], and aspect ratio [Exact]. Keep [concrete identity and action invariants] immediately recognizable. Rebuild [environment, blocking, depth, light geometry, and time behavior] and introduce [new environment and supporting elements]. Keep the face and defining subject structure as the stable information zone; apply stronger temporal or spatial transformation outside it. Beyond palette, exposure, grain, halation, and wetness, make at least two visible non-color changes from [selected layers].
```

When a supplied image is reference-only, state:

```text
Use the supplied images only for [motion/color/composition/texture traits]. Preserve none of their actors, identities, wording, brands, exact objects, locations, costumes, or compositions. Create a new subject and a clearly different scene arrangement.
```

## Compilation Rules

- Translate a short request into reasonable scene and emotional choices without interrogating the user.
- For a complex story, choose one moment with one dominant relationship; do not summarize the plot in a single frame.
- State who is stable, who is moving, which direction movement follows, what becomes smeared, and what remains readable.
- For visible motion, state two apparent clocks and how the camera relates to each. `Step-printed` requests require uneven cadence, partial repeated edges or broken smears, and segmented source-linked light traces; one continuous Gaussian blur is insufficient.
- For restrained or still requests, state the repeated route, obstruction, secondary motion, or suspended gesture that makes time perceptible without obligatory blur.
- State the source of each important color. Do not use color names as a detached LUT list.
- Use exact period props only when they serve the scene. Two to four grounded cues are enough.
- Keep text on signs generic and nonessential unless the user provides exact text and asks for it.
- Treat `step-printed`, shutter fractions, or lens millimeters as secondary support. Describe visible frame echoes, smear, direction, and spatial distortion first.
- Use `Hong Kong` as location context when needed, but do not rely on it to carry the design.
- Omit director and film-title names from the compiled prompt unless the user explicitly requires a textual discussion rather than generation.
- Poster prompts may contain only user-supplied title wording; never invent official credits, logos, awards, or branded lockups.
- Do not use `masterpiece`, `award winning`, `beautiful`, `artistic`, `cinematic`, or `iconic` as substitutes for a decision.
- Select only relevant negatives. A long negative catalogue dilutes the visual instructions.

## Compact Hard-Avoid Bank

Select the risks relevant to the recipe:

```text
generic cyberpunk, futuristic city, holograms, clean purple-blue RGB neon, rainbow neon, synthetic fog, mandatory wet asphalt, sterile modern mall, luxury commercial portrait, beauty retouching, studio lighting, glossy advertising, anime, kawaii, American-noir costume shorthand, Hollywood blockbuster light, clean orange-teal grade, perfect HDR, perfect digital sharpness, centered fashion pose, isolated 85 mm bokeh portrait, uniform full-frame blur, radial software blur, duplicated faces, floating light trails, copied actor, copied movie still, exact reference composition
```

## Motion Example

```text
Keep the waiting woman's face, eyes, and upper torso comparatively stable at the right third of the frame. Pedestrians cross left to right between the camera and the curb, stretching into uneven elongated trails; one dark coat briefly obscures her lower body. Add only a faint repeated edge behind her sleeve and short red taillight streaks attached to passing taxis. The storefront and road geometry remain readable.
```

## Step-Printed Time Example

```text
Track close beside the man so his eyes, nose, and upper torso remain readable while the concourse runs at a faster apparent clock. Passing shoulders and tiled columns break into two or three uneven directional residues with small gaps between them rather than one smooth blur; fluorescent fixtures segment into short repeated bars tied to camera travel. Let a foreground commuter erase part of his coat for one instant, while the route geometry remains legible enough to show forward movement.
```

## Still-Tension Example

```text
Keep both diners and the narrow restaurant architecture stable. Only a server crossing the far background and a slow ceiling fan carry subtle motion; no obvious full-frame slow shutter. Hold the silence through unequal depth, a foreground chair edge, green fluorescent spill, warm table light, coarse grain, and deep shadow.
```
