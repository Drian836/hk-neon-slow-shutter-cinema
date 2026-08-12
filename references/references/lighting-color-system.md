# Lighting And Color System

## Source-First Rule

Build color from visible or inferable practical sources, not from a global LUT label.

Use this hierarchy by default:

1. one dominant practical-light family;
2. one secondary source with a different temperature or color;
3. at most one small accent from a sign, vehicle, garment, or object.

Do not give red, blue, purple, cyan, green, and pink equal weight. Limited source conflict creates lived-in color; an unrestricted spectrum creates cyberpunk drift.

## Practical-Light Behaviors

- **Fluorescent cast:** broad dirty-white, green, or cool-cyan top/side illumination; flat on walls but uneven across faces; may reveal tired skin and tiled surfaces.
- **Tungsten spill:** localized amber or warm-yellow pools around bulbs, counters, doorways, and tables; falls off quickly into brown-black shadow.
- **Signage reflection:** localized red, green, or cyan contamination on glass, metal, cheek, wet ground, or vehicle paint; never an unmotivated full-frame wash.
- **Vehicle light:** headlight or taillight accents tied to road direction, glass, and motion; short halation or streaks are valid.
- **Window reflection:** combines interior and exterior planes, often mixing warm interior light with cool city spill.
- **Street lamp:** dirty warm-white or sodium-like amber that reveals only a section of pavement, wall, or figure.
- **Daylight through aged glass:** desaturated cyan/green fill that can oppose a warmer interior source.

## Palette Families

| Family | Dominant source | Secondary source | Optional accent | Best use | Avoid |
| --- | --- | --- | --- | --- | --- |
| Green Fluorescent / Amber Tungsten | dirty green-white ceiling or storefront fluorescent | localized amber doorway or cooker | deep red sign or cup | restaurant, convenience store, corridor | lime sci-fi glow across everything |
| Deep Red / Dirty Green | red sign or curtain spill | worn green fluorescent fill | dirty white practical | street corner, café, intimate threshold | equal red-blue-purple neon |
| Amber / Cyan Spill | tungsten interior or street lamp | cyan window/storefront spill | red vehicle light | taxi, rainy window, night exterior | clean blockbuster orange-teal |
| Warm Interior / Cool Exterior | brown-gold room light | muted blue-green exterior | small sign reflection | café, apartment, hotel, bus | polished luxury interior |
| Dirty White / Green | imperfect fluorescent white | green contamination in walls/shadows | small warm object | snack counter, subway, bus | clinical hospital-white cleanliness |
| Tungsten / Deep Red | amber bulb or restaurant pendant | dark red signage/curtain reflection | tiny cool window trace | old café, stairwell, hotel | saturated red wash with no source |
| Humid Daylight / Tobacco Amber | aged-window cyan-green daylight | weak tobacco-amber bulb or reflected wall warmth | muted red-brown object | rented room, washroom, old café, early-morning interior | universal green-orange skin grade |
| Cold Exterior / Weak Warm Room | cool street, window, or overcast daylight spill | small weak bulb, cooker, or bedside lamp | localized red or green household object | provisional room, weary couple, travel aftermath | polished orange-teal contrast |

## Color Distribution

- Let the dominant source control most illuminated surfaces.
- Keep the secondary color visibly subordinate and spatially motivated.
- Limit the accent to a small region that remains legible at thumbnail scale.
- Preserve neutral or near-neutral areas: black, dirty white, brown, gray metal, worn tile, skin, or unlit wall.
- Do not demand exact percentages from the image model; use relative terms such as dominant, localized, narrow, or small accent.

## Skin And Subject Treatment

- Allow modest green, amber, cyan, or red contamination on the side facing the practical source.
- Preserve facial structure, eye sockets, and a readable skin plane when the person is the emotional anchor.
- Avoid porcelain skin, beauty-dish highlights, symmetric catchlights, skin smoothing, and perfect commercial color neutrality.
- Let one side of the face fall toward shadow when motivated, but retain enough information for identity-sensitive edits.

## Reflection And Rain

- Use rain only when requested or supported by the scene.
- Tie wet reflections to actual signs, lamps, headlights, and vehicle colors.
- Keep reflections broken by pavement texture, glass, wipers, condensation, or passing objects.
- Avoid full-street mirror reflections, constant rainfall, and neon fog as default shorthand for Hong Kong.

## Exposure And Film Response

- Favor underexposed or uneven exposure with a protected facial or object anchor.
- Permit small clipped practical highlights and soft halation around bulbs, signs, and headlights.
- Keep deep blacks while retaining selective texture on walls, clothing, hair, and architecture.
- Add high-speed color-film grain, slight chroma contamination, modest contrast roll-off, and occasional focus softness.
- Do not apply perfect HDR, global clarity, crisp digital edge enhancement, or an even teal/orange grade.
- Across visual families, palette may change substantially. Preserve family identity through source logic, time, camera, blocking, and film response rather than forcing green/red into every output.

## Prompt Language

Prefer:

```text
greenish fluorescent light from the snack-bar ceiling contaminates the tiled wall and one side of the face; a small amber cooker light warms the hands; a narrow red sign reflection touches the stainless counter; deep green-black shadows retain limited wall texture
```

Avoid:

```text
vibrant neon cinematic lighting, colorful cyberpunk city, teal and orange color grade
```

## Color Repair Map

| Failure | Repair |
| --- | --- |
| Rainbow neon | Remove all but one dominant source, one secondary source, and one accent. |
| Color looks like a LUT | Name where each light originates and which surfaces it reaches. |
| Skin looks commercial | Remove studio terms; add practical-source contamination and imperfect exposure. |
| Shadows are empty | Restore limited texture around face, hands, clothing, and architecture. |
| Scene is too clean | Add aged surface response, mixed white balance, grain, and localized reflection. |
| Hong Kong becomes cyberpunk | Remove future technology, purple-blue RGB, fog, holograms, and excessive wet reflection. |
