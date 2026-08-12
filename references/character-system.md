# Character And Photo Preservation System

## Character Principle

Treat the person as an individual inside a working environment, not as a mannequin carrying a style. Preserve identity before applying motion, lens distortion, color contamination, or period treatment.

## Image Roles

- **Edit target:** preserve the recognizable subject in the final image.
- **Reference image:** learn only requested visual traits; do not retain identity or exact composition.
- **Supporting insert:** preserve a specified person, object, garment, or fragment inside a newly designed scene.

## Preservation Levels

Apply preservation per layer. Never assign one preservation level to the whole source frame.

| Layer | Default for a person moved into a new Hong Kong scene | Notes |
| --- | --- | --- |
| identity and body structure | High | facial geometry, age, hair, proportions, defining marks |
| action and interaction | High when story-critical; otherwise Medium | gaze, hand contact, relationship, body orientation |
| wardrobe and carried objects | Medium; High only when requested or recognition-critical | do not turn unrequested modern branding into a location invariant |
| camera and crop | Medium | preserve general viewpoint without freezing exact composition |
| environment and location | Low | source architecture, signage, furniture, weather, and geography may be rebuilt |
| source text and signs | Low | preserve only exact user-required wording |
| aspect ratio | Exact by default | unless the user requests a new ratio |

High identity preservation never implies High preservation of environment, text, camera, light, or full composition.

### High

Use by default for identifiable people, pets, products, characters, and artworks.

Record visible invariants:

- facial structure, eye spacing, nose, mouth, jaw, age range, and skin characteristics;
- hair shape, length, color, texture, and defining facial hair;
- body proportions, mobility aids, defining markings, and recognizable silhouette;
- wardrobe colors, layers, patterns, accessories, and footwear when required;
- pose, hand-object contact, and interaction when central to recognition;
- product geometry, component count, materials, logos when the user owns and requires them, and recognizable colors.

Allow changes according to the declared layer matrix. Reduce wide-angle distortion and motion on the face when preservation is fragile, but do not reduce the scene transformation merely because identity is High.

### Medium

Preserve the main subject and defining traits while permitting crop, scale, pose details, wardrobe when not required, palette, and surrounding scene to change.

### Low

Use for reference-only inputs. Preserve motion grammar, palette relationship, composition behavior, texture, or mood as requested; preserve none of the source identity, wording, exact objects, or exact layout.

## Facial Readability

- Keep at least one eye line, facial plane, or profile edge readable when the character carries the emotion.
- Permit soft film focus and practical-light shadow; do not equate preservation with clinical digital sharpness.
- Apply strong motion to nearby crowds, limbs, clothing edges, reflections, or background before applying it to the face.
- In a close wide-angle frame, control distortion so identity remains recognizable. Do not elongate noses, duplicate eyes, or stretch jawlines.

## Pose And Interaction

- Derive pose from action: waiting, walking, running, sitting, turning, eating, holding a rail, looking through glass, or sharing a table.
- Avoid fashion-model contrapposto, direct product endorsement, theatrical hand gestures, and fixed eye contact with camera unless requested.
- Make hands contact objects and surfaces plausibly. Treat anatomy failure as a hard fail.
- For two people, define gaze, distance, body orientation, and who occupies which depth plane.

## Wardrobe And Period Logic

- Prefer ordinary late-1980s-to-around-2000 urban clothing: work shirts, simple suits, T-shirts, knitwear, raincoats, patterned blouses, denim, modest dresses, practical shoes, canvas or leather bags.
- Keep user-supplied wardrobe under High preservation when requested.
- Do not make cheongsam, sunglasses, blond wigs, leather coats, or red dresses mandatory; they may belong to one film, period, or character rather than the visual system.
- Avoid costume-party nostalgia, pristine designer styling, futuristic techwear, and modern influencer fashion unless the user explicitly asks for a hybrid.

## Environment Integration

- Let practical light contaminate skin and clothing locally.
- Allow partial occlusion by a door, counter, window, passenger, or vehicle while keeping identity evidence visible.
- Give the subject a plausible relationship to the location: holding a cup, leaning on a rail, waiting by a curb, sitting in the rear seat, or moving through a crowd.
- Avoid a separately lit person pasted over a blurry city.
- Source-locale residue is not part of identity. Remove or rebuild contradictory language, architecture, furniture, road design, storefronts, or landscape unless the user explicitly asks to keep them.
- When a location/style transformation is requested, require the environment to alter blocking, circulation, depth, or practical-light geometry rather than only hue and grain.

## Photo Prompt Contract

State four parts explicitly:

1. **Subject must remain:** concrete identity, body, action, wardrobe, and interaction invariants by layer.
2. **Frame may remain:** any requested camera, crop, route, or geometry constraints; omit unrequested source residue.
3. **Must transform:** at least two visible non-color layers selected from environment semantics, circulation/blocking, spatial depth, lens/crop behavior, temporal behavior, or practical-light geometry.
4. **May be introduced:** new Hong Kong environment, practical sources, supporting figures, reflections, vehicles, or period details.

For High preservation, keep the original face and defining subject structure as the stable information zone. Place temporal smear primarily on the environment.

## Preservation QA

Compare source and result for:

- immediate recognizability at normal view;
- facial structure and age;
- hair and body proportions;
- wardrobe or product invariants;
- pose and object contact when required;
- unintended beautification, ethnicity drift, gender presentation drift, or anatomy failure;
- whether wide-angle or motion treatment changed the person more than the environment.
- whether source-locale residue contradicts the target setting;
- whether removing color, exposure, grain, halation, and wetness reveals at least two substantive changes outside the identity zone.

Repair identity and scene transformation independently. If a central identity invariant fails, tighten only the identity layer, repeat the exact invariant list, and move distortion or blur away from the face. If the result is grade-only, keep identity constraints unchanged but loosen camera/environment preservation and strengthen time, blocking, or spatial behavior. Regenerate at most once and report unresolved limitations honestly.
