# Motion And Temporal System

## Core Principle

Do not interpret slow shutter as equal blur across the whole image. Assign distinct motion roles before writing the prompt.

For a single generated frame, emulate the visible consequence of undercranked capture restored through repeated-frame printing, frame blending, or a long exposure. Do not claim that a still image literally reproduces a moving-film process. Favor relative speed, directional cadence, readable anchors, uneven discontinuity, and slight repeated-edge residue over a smooth software blur.

## Distinguish Three Time Behaviors

Do not collapse these into one generic `motion blur` instruction:

| Behavior | Visible single-frame translation | Best emotional use | Failure |
| --- | --- | --- | --- |
| Continuous slow shutter | one directional smear connecting positions; practical lights stretch along the same path | traffic passage, crowd pressure, hurried camera | smooth Gaussian streak with no stable anchor |
| Conventional slow-motion feeling | a comparatively clean, suspended gesture with little smear and extended attention | tenderness, observation, aftermath | merely sharp action with a dark grade |
| Step-printed / undercranked time | the subject or one spatial anchor remains comparatively legible while the world advances in coarse temporal steps: broken trails, uneven edge intervals, two or three partial positional residues, choppy rather than silky cadence | isolation, disorientation, searching, memory, urban acceleration | neat triple exposure, transparent full-body clones, or generic blur |

When the request explicitly asks for 慢快门、抽帧、步印、step-printing, or the restless time feeling associated with fast urban circulation, default to the third behavior unless the action clearly calls for continuous vehicle passage.

## Time Is A Relationship

The effect comes from at least two different apparent clocks, not from blur alone. Select one:

- **Still person / accelerated world:** readable face and torso; crowd, vehicle, signage reflection, or foreground bodies advance in coarse directional steps.
- **Tracked person / slipping world:** camera approximately follows the subject; one eye line or torso center survives while limbs and background edges jump backward in uneven residues.
- **Moving vehicle / trapped passenger:** cabin, face, or window frame anchors the image; exterior planes slide and repeat at different speeds.
- **Two people / asynchronous attention:** one gesture or gaze is held while a server, reflection, curtain, fan, or passerby marks another clock between or around them.
- **Absent subject / residual event:** a recently moved curtain, fan, vehicle light, swinging door, or displaced reflection makes time visible in an otherwise stable space.

If every visible plane shares one smooth blur strength, the time design has failed.

## Motion Grammar

Declare these slots for every generation:

| Slot | Required decision |
| --- | --- |
| `STATIC_SUBJECT` | Which face, eyes, torso, hands, or object must remain readable? |
| `MOVING_SUBJECT` | Which body part or subject is moving, and at what relative speed? |
| `MOVING_ENVIRONMENT` | Which pedestrians, vehicles, reflections, lights, or background planes move? |
| `CAMERA_MOVEMENT` | Is the camera locked, drifting, panning, tracking, or handheld? |
| `CAMERA_SUBJECT_RELATION` | Does the camera hold, lag behind, pan with, overtake, or counter-move against the subject? |
| `TEMPORAL_CADENCE` | Is time continuous, suspended, or step-printed with uneven intervals? |
| `TEMPORAL_GHOSTING` | Is there no echo, a slight repeated edge, or irregular overlapping silhouettes? |
| `MOTION_DIRECTION` | Left-to-right, right-to-left, toward camera, away, diagonal, vertical, or mixed? |
| `BLUR_INTENSITY` | None, subtle, moderate, or strong; identify the plane receiving it. |
| `LIGHT_STREAK` | Which practical light moves, in what direction, and how far? |

At least one stable information zone must survive any moderate or strong motion treatment.

For explicit step-printed time, the prompt must resolve `CAMERA_SUBJECT_RELATION`, `TEMPORAL_CADENCE`, and `TEMPORAL_GHOSTING`; ordinary blur language is insufficient.

## Recipe 0: Step-Printed Drift

- **Use for:** searching, urban disorientation, restless waiting, nearly missed encounters, moving against a crowd.
- **Stable:** one eye line, facial plane, torso center, hand-object contact, vehicle cabin, or architectural vertical.
- **Moving:** crowd bodies, limbs, storefront edges, reflections, or vehicles at unequal apparent speeds.
- **Camera relationship:** pan or drift approximately with the anchor, but lag slightly so the environment slips past.
- **Direction:** choose one dominant travel vector; any weaker counterflow must be spatially separate.
- **Cadence:** broken and uneven, with short held fragments between longer smears; not a silky continuous trail.
- **Echo:** two or three low-opacity partial edge residues behind only the genuinely moving form; never complete clean clones.
- **Light:** practical lights appear as segmented or pulsed streak fragments attached to the source, not a single polished neon ribbon.
- **Failure:** a sharp fashion portrait pasted over blurred extras, global blur, symmetrical triple exposure, or motion that reads as a Photoshop filter.

Pixel language:

```text
the camera drifts with the subject but lags slightly; one eye line and the torso center survive while nearby bodies and storefront edges advance in uneven temporal steps, with broken directional smears, two or three faint partial edge residues, and segmented practical-light traces attached to the moving sources
```

## Recipe 1: Subject Anchor

- **Use for:** waiting, observing, loneliness, shock, indecision.
- **Stable:** face, eyes, upper torso, and the object being held.
- **Moving:** surrounding pedestrians or near traffic.
- **Direction:** choose one dominant flow that crosses around the subject.
- **Blur:** moderate on the moving environment; subtle or none on the face.
- **Echo:** optional slight edge echo on coat hems or hands, never multiple full faces.
- **Light:** streak only practical sources attached to moving people or vehicles.
- **Failure:** a pasted-sharp studio portrait over an unrelated blurry background.

Pixel language:

```text
the subject remains comparatively stable and readable while nearby pedestrians stretch into directional trails, with the eyes and facial structure intact and only a slight temporal echo along the subject's outer edge
```

## Recipe 2: Moving Subject

- **Use for:** running, crossing, searching, catching transport, leaving.
- **Stable:** preserve the facial plane, leading eye, torso center, and essential body action.
- **Moving:** limbs, clothing edges, and background at different strengths.
- **Direction:** align all smears with the actual path of travel.
- **Blur:** moderate on limbs and strong only on the faster background or nearest occluder.
- **Echo:** one or two irregular edge residues may trail behind the body.
- **Light:** vehicle or sign streaks must follow the camera/subject motion.
- **Failure:** face erased, anatomy multiplied, or a body smeared opposite to its movement.

## Recipe 3: Crowd Isolation

- **Use for:** emotional suspension in a busy crossing, concourse, market, or street corner.
- **Stable:** one person as the emotional center, even when off-axis.
- **Moving:** crowd streams at normal or accelerated apparent speed.
- **Direction:** use one main flow and optionally a weaker counterflow.
- **Blur:** elongated figures with leg and clothing trails; keep some silhouettes recognizable as people.
- **Echo:** mild frame-blended cadence rather than transparent clones.
- **Light:** small bag, phone, or storefront reflections can streak with the crowd.
- **Failure:** evenly blurred crowd and subject, or a crowd that looks like smoke.

## Recipe 4: Vehicle Passage

- **Use for:** taxi, bus, minibus, tram, or motorcycle passing a person or camera.
- **Stable:** choose the person, vehicle cabin, or road geometry as the anchor.
- **Moving:** vehicle body, foreground edge, window reflection, or surrounding street.
- **Direction:** match the road and vehicle trajectory.
- **Blur:** strong only on the closest moving plane; preserve one cabin, face, wheel, lane, or vehicle silhouette.
- **Echo:** subtle reflection overlaps are preferred to duplicated vehicles.
- **Light:** headlights and taillights form short directional streaks; do not create light trails from unlit surfaces.
- **Failure:** impossible traffic direction, floating light ribbons, futuristic vehicles, or no readable anchor.

## Recipe 5: Temporal Echo

- **Use for:** memory, déjà vu, insomnia, disorientation, a nearly missed encounter.
- **Stable:** one primary facial or spatial anchor.
- **Moving:** a hand, head turn, crossing figure, curtain, or vehicle edge.
- **Direction:** echo behind the actual movement, not equally on both sides.
- **Blur:** subtle to moderate.
- **Echo:** slight repeated silhouettes, uneven edge intervals, frame-blended overlap, or temporal discontinuity.
- **Light:** repeat only the light associated with the echoed movement.
- **Failure:** clean triple exposure, symmetric clones, or paranormal ghost imagery.

## Recipe 6: Handheld Drift

- **Use for:** hurried pursuit, cramped interiors, spontaneous street encounters, unsettled intimacy.
- **Stable:** one eye line, face, hand, sign edge, or architectural reference.
- **Moving:** background edges and nearby occluders respond to slight camera movement.
- **Direction:** short oblique or lateral drift; avoid a perfect radial center.
- **Blur:** subtle to moderate and spatially uneven.
- **Echo:** usually none or very slight.
- **Light:** practicals may drag a short distance consistent with camera movement.
- **Failure:** random shake applied uniformly, Dutch-angle cliché, or unreadable composition.

Pair Handheld Drift with Step-Printed Drift when urgency or instability is requested: preserve one anchor, then let short oblique camera lag and coarse frame residues affect different depth planes unequally.

## Recipe 7: Still Tension

- **Use for:** restrained intimacy, silent meals, guarded conversation, aftermath, quiet memory.
- **Stable:** people and architecture remain readable.
- **Moving:** minimal gesture, distant passerby, fan, curtain, rain, or traffic reflection only.
- **Camera:** locked or nearly locked.
- **Blur:** none or subtle on one secondary element.
- **Echo:** none.
- **Time:** express duration through repeated architecture, held posture, empty space, or a practical light burning above the subject.
- **Failure:** losing the visual family because overt slow shutter is absent. Preserve mixed practical light, layered space, film imperfection, and emotional distance.

## Intensity Rules

- Use no more than one strongly blurred plane in most images.
- Keep the face readable when identity or emotion matters. A readable face may be softly imperfect; it need not be digitally sharp.
- Keep motion physically causal. Limbs, clothes, crowds, vehicles, reflections, and light trails must agree on direction and relative speed.
- Use repeated edge echoes sparingly; one to three low-opacity residues are usually enough as prompt language.
- Prefer `directional motion smear`, `elongated pedestrian trails`, `subject partially frozen against moving environment`, `slight repeated edge echoes`, `streaked practical lights`, and `uneven motion cadence`.
- Treat shutter fractions, frame rates, or lens parameters as optional support, never as the primary instruction.
- A still image cannot prove literal frame rate. Judge the visible cadence: unequal gaps, partial positional residue, segmented source-linked streaks, and different apparent clocks.
- `slow motion` alone is ambiguous. Translate it into conventional suspended gesture or step-printed discontinuity from the requested emotion and action.

## Motion Repair Map

| Failure | Prompt repair |
| --- | --- |
| Whole frame is soft | Name the stable face/torso/object and restrict blur to one moving plane. |
| Motion has no direction | State origin, destination, and dominant vector. |
| Subject disappears | Reduce subject blur one level and repeat identity/readability constraints. |
| Echo becomes clones | Replace full silhouettes with slight irregular edge echoes. |
| Light trails float | Attach each trail to a moving headlight, taillight, sign reflection, or camera drift. |
| Result feels digitally filtered | Add uneven cadence, spatially selective smear, occlusion, grain, and practical-source logic. |
| Result is only dark/recolored | Require a second apparent clock, camera-subject relation, and visible discontinuous residue independent of color. |
| Motion is smooth but should feel step-printed | Break one long trail into uneven segments; add two or three partial edge residues and preserve a stable anchor. |
| Still Tension erased the requested slow shutter | Switch to Step-Printed Drift or add an asynchronous secondary clock that is visible at thumbnail size. |
