# Variation Engine

Select one coherent option from each axis after interpreting the content. Do not choose a scene, prop, or motion effect independently of the action and emotion.

## Axes

### Visual Family

- Humid Interior Drift;
- Urban Temporal Flux;
- Nocturnal Wide-Angle Estrangement;
- Restrained Corridor Memory;
- Exile And Cramped Tenderness.

### Scene

Pedestrian Crossing, Street Food Stall, Convenience Store, Narrow Alley, Apartment Corridor, Stairwell, Taxi Interior, Bus Interior, Subway Entrance, Footbridge, Old Café, Night Restaurant, Street Corner, Residential Balcony, Rainy Window, or Hotel Corridor.

### Time

- evening rush;
- late evening;
- after midnight;
- pre-dawn;
- rainy daytime;
- fluorescent interior daytime.

### Subject State

- waiting and scanning the street;
- walking slowly against faster circulation;
- running or hurrying toward transport;
- seated and watching through glass;
- two people nearly crossing paths;
- two people sharing silence;
- turning away after a conversation;
- working a late shift;
- alone after a crowd has passed.

### Motion Grammar

- Step-Printed Drift;
- Subject Anchor;
- Moving Subject;
- Crowd Isolation;
- Vehicle Passage;
- Temporal Echo;
- Handheld Drift;
- Still Tension.

### Camera-Subject Relation

- camera tracks with a readable subject while the world runs faster;
- camera stays locked while people cross at unequal clocks;
- camera moves with a vehicle while architecture sweeps past;
- camera remains extremely close and off-axis while the subject turns inside deep space;
- camera observes through a threshold while subjects repeat a route;
- camera shares cramped space and drifts slightly with breath or body movement.

### Composition

- Off-axis Close-up;
- Foreground Occlusion;
- Wide-angle Intimacy;
- Deep Layer Compression;
- Doorway Framing;
- Mirror Fragment;
- Window Reflection;
- Edge Cropping;
- Crowd Isolation;
- Environmental Portrait;
- Low Corner View;
- Oblique Handheld Frame.

### Lighting Palette

- Green Fluorescent / Amber Tungsten;
- Deep Red / Dirty Green;
- Amber / Cyan Spill;
- Warm Interior / Cool Exterior;
- Dirty White / Green;
- Tungsten / Deep Red.

### Spatial / Lens Feeling

- close wide-angle distance-in-proximity;
- moderate-wide environmental intimacy;
- normal-lens locked observation;
- compressed crowd layers;
- low near-ground route perspective;
- reflected multi-plane space.

### Film Texture

- coarse high-speed color-film grain;
- pushed underexposure with soft halation;
- fine grain with mild print softness;
- uneven focus falloff and slight gate weave;
- color-contaminated shadows with clipped practicals;
- modest frame-edge softness and chromatic bleed.

### Emotional Temperature

- restless longing;
- suspended loneliness;
- guarded intimacy;
- missed connection;
- tired tenderness;
- anxious searching;
- private memory;
- nocturnal unease;
- fleeting relief.

## Coherence Rules

- Choose the scene from the action and emotion first.
- Choose motion from relative speed: who or what is stable, who or what moves, and why.
- Choose composition from the relationship between subject and environment.
- Choose a palette that can be produced by the scene's actual practical lights.
- Choose spatial feeling after deciding how close the camera must be and how much environment must remain visible.
- Choose texture last; it should reproduce the selected light and exposure, not hide weak scene design.
- Use Still Tension when overt blur would damage restrained intimacy, legibility, identity, or the user's explicit request.
- Never choose Still Tension for explicit `slow shutter`, `step printing`, `抽帧`, `拖影`, or visible slow-motion requests unless the user also asks to suppress blur. Default those requests to Step-Printed Drift or another two-clock motion grammar.
- Choose one primary visual family before scene, motion, palette, or props. A supporting family may contribute one device only.
- Color cannot be the only shared attribute between recipe variants.
- Do not combine extreme wide-angle distortion, strong full-body blur, dense crowd occlusion, multiple reflections, and heavy grain in one image. Keep one dominant visual risk.

## Content Defaults

Use these only as starting logic:

| Content cue | Preferred direction |
| --- | --- |
| waiting, time stopped | Street Corner or Crossing / Crowd Isolation / Subject Anchor or Crowd Isolation motion |
| rushing, last bus, pursuit | Crossing, Subway Entrance, Footbridge / Moving Subject / Oblique or Low Corner |
| taxi, looking outside | Taxi Interior / Vehicle Passage or Temporal Echo / Window Reflection |
| two people pass | Convenience Store, Corridor, Crossing / opposing motion / Foreground Occlusion |
| silent meal | Night Restaurant or Old Café / Still Tension / Doorway or Deep Layers |
| memory or insomnia | Rainy Window, Balcony, Taxi / Temporal Echo / Reflection |
| supplied portrait | Subject High / Action High or Medium / Camera and Composition Medium / Environment Low / Text Low / exact source ratio; environment carries most transformation |
| explicit slow shutter or step printing | Urban Temporal Flux / Step-Printed Drift / track-with-subject or locked-anchor two-clock relation |
| restrained two-person intimacy | Restrained Corridor Memory / Still Tension or subtle secondary motion / threshold observation |
| extreme night proximity | Nocturnal Wide-Angle Estrangement / Handheld Drift or Vehicle Passage / close off-axis camera |

## Batch Rules

- Between adjacent outputs, change at least two of Time Behavior, Camera-Subject Relation, Scene, Composition, and Relational Blocking.
- For four or more outputs, use at least three scene or composition families.
- Do not repeat the same Scene + Motion + Composition combination within a batch.
- Do not simulate variation by changing only gender, clothing, sign color, subject position, or rain.
- Vary overt temporal intensity: a coherent batch may include strong motion, moderate motion, subtle echo, and Still Tension.
- Preserve family identity through lived-in space, practical mixed light, human-environment integration, layered depth, imperfect film response, and emotional distance.

## Recipe Record

Record the selected strategy exactly in this order:

```text
[visual-family / scene / time / subject-state / time-behavior / camera-subject-relation / composition / lighting / spatial-feeling / texture / emotion]
```

Example:

```text
[Urban Temporal Flux / street corner / after midnight / one woman waiting and scanning the road / Step-Printed Drift with the crowd at a faster clock / locked near the subject while circulation crosses / Foreground Occlusion / Green Fluorescent + Amber Tungsten with small deep-red accent / moderate-wide environmental intimacy / coarse high-speed color-film grain / restless longing]
```

The recipe is an execution record. Do not paste it verbatim into the final image prompt.
