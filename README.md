# HK Neon Slow-Shutter Cinema

[简体中文](README.zh-CN.md) · [Installation and downloads](INSTALL.md)

A Codex Visual Skill for generating, transforming, and analyzing lived-in late-1980s-to-around-2000 Hong Kong urban cinema frames, plus poster design when explicitly requested. It routes short requests, photographs, film stills, and poster references into an executable visual family, scene, relative-time, camera-subject, lighting, composition, and film/print-reproduction system.

The Skill does **not** depend on a fixed prompt or a filmmaker name. Its visual family is built from:

- scene grammar;
- motion and temporal grammar;
- visual-family and relative-clock routing;
- camera-subject-world relationships;
- practical-light and color grammar;
- composition and spatial grammar;
- character-preservation rules;
- imperfect color-film reproduction;
- variation and actual-raster quality control.
- separate poster evidence and design routing.

## Suitable Inputs

- A short scene: “A woman waits at a street corner before dawn.”
- An action or emotion: “A man crosses a crowd while his own time feels stopped.”
- A supplied portrait or product that must remain recognizable.
- Screenshots used only for selected motion, color, lighting, composition, or texture traits.
- A request to analyze why a reference set shares a visual family.
- A prompt-only request or a multi-image batch.

## Visual Characteristics

The fixed identity combines lived-in Hong Kong urban space, people embedded in working environments, selective directional motion, layered foreground and background, mixed practical lighting, emotional distance, and imperfect film response. Slow shutter is never treated as uniform blur: the Skill distinguishes continuous shutter smear, suspended slow-motion feeling, and discontinuous step-printed time; it declares the stable anchor, second apparent clock, camera relationship, direction, cadence, edge residue, and source-linked light traces.

Hong Kong night is not treated as generic cyberpunk. The anti-identity rules reject futuristic cities, clean purple-blue RGB neon, rainbow lighting, gaming aesthetics, synthetic fog, sterile malls, commercial beauty portraits, studio lighting, modern glossy advertising, and perfect digital sharpness.

## Install

### Download the source

- Release package: open [Releases](https://github.com/Drian836/hk-neon-slow-shutter-cinema/releases) and download `hk-neon-slow-shutter-cinema-v0.3.0.zip`.
- GitHub source archive: choose **Code → Download ZIP** on the repository page.
- Git clone:

```bash
git clone https://github.com/Drian836/hk-neon-slow-shutter-cinema.git
```

See [`INSTALL.md`](INSTALL.md) for Windows, macOS/Linux, update, verification, and uninstall instructions.

Copy the complete folder into the Codex skills directory:

```text
~/.codex/skills/hk-neon-slow-shutter-cinema/
```

No database, RAG system, Obsidian vault, external API, Python runtime script, or third-party dependency is required. Restart or open a new Codex task if the newly installed Skill is not immediately listed.

## Use

Invoke it explicitly when desired:

```text
Use $hk-neon-slow-shutter-cinema to make a woman waiting at a Hong Kong street corner before dawn.
```

It may also trigger from matching requests such as 港风电影感, 90年代香港, slow-shutter Hong Kong, temporal smear, or a request to analyze related reference stills.

### Modes

- **Generate Mode:** interprets content, compiles a prompt, generates an image, inspects the actual raster, and performs at most one targeted regeneration.
- **Photo Input Mode:** assigns image roles and preservation levels, passes the actual source to generation, and checks identity or product invariants.
- **Reference Analysis Mode:** inspects supplied images and separates reusable grammar from sample-specific residue.
- **Prompt-only Mode:** returns a directly usable three- or four-paragraph prompt without claiming image generation.
- **Analyze + Generate Mode:** learns requested traits from references, then creates a new scene without copying a source shot.
- **Poster Mode:** classifies frames/photos, official key art, fan/editorial redesigns, and uncertain sources before creating a new image hierarchy, title system, and print behavior.

## Workflow

```text
Input
→ Route Mode
→ Parse Intent
→ Select One Primary Visual Family
→ Interpret Scene and Emotion
→ Select Relative Clocks, Camera Relation, Composition, Light, and Film Strategy
→ Select Variation Recipe
→ Compile Renderable Prompt
→ Generate
→ Inspect Actual Raster
→ Quality Gate
→ At Most One Targeted Regeneration
→ Return Image, Prompt, Recipe, and Inspection Note
```

## Directory Structure

```text
hk-neon-slow-shutter-cinema/
├── SKILL.md
├── README.md
├── README.zh-CN.md
├── agents/
│   └── openai.yaml
├── evals/
│   └── evals.json
├── examples/
│   ├── night-restaurant-still-tension.md
│   ├── taxi-window-memory.md
│   └── waiting-at-street-corner.md
└── references/
    ├── character-system.md
    ├── composition-system.md
    ├── lighting-color-system.md
    ├── motion-system.md
    ├── prompt-compiler.md
    ├── quality-gate.md
    ├── reference-analysis.md
    ├── poster-system.md
    ├── scene-system.md
    ├── style-system.md
    ├── visual-families.md
    └── variation-engine.md
```

`SKILL.md` is the router and workflow kernel. The references own specialist knowledge so they can be loaded progressively. The examples demonstrate compiled behavior without bundling copyrighted movie stills. Evals cover routing, scene and motion reasoning, variation, prompt compilation, photo preservation, reference separation, anti-cyberpunk control, and quality gating.

## Example Recipe

```text
[Urban Temporal Flux / street corner / pre-dawn / one woman waiting / Step-Printed Drift with a faster crowd clock / camera locked near subject / Foreground Occlusion / Green Fluorescent + Amber Tungsten / moderate-wide environmental intimacy / coarse color-film grain / restless longing]
```

See `examples/waiting-at-street-corner.md` for the compiled prompt and QA focus.

## Limitations

- A single generated still can approximate frame echoes and step-print-like temporal discontinuity, but it does not reproduce a real multi-frame optical process.
- Image models often produce continuous slow-shutter blur more reliably than truly discontinuous step-printed residues; explicit step-print requests therefore have a separate hard gate and cannot pass on grading alone.
- Model output may still drift in identity, anatomy, text, vehicle geometry, period details, or motion causality; the bounded repair policy reduces but cannot eliminate these failures.
- Online screenshots and restorations can differ in crop, hue, contrast, and grain. Reference analysis therefore labels observation, inference, reported context, and transfer uncertainty separately.
- The Skill generates an abstract visual grammar. It does not copy actors, exact movie frames, protected characters, subtitles, logos, or source-specific compositions.
- Period authenticity is directional rather than archival. If exact year, route, brand, uniform, or vehicle specification matters, provide evidence and request explicit verification.

## License status

No open-source license has been selected yet. The public repository may be viewed and downloaded, but no additional reuse permission is granted beyond applicable law until a license is added by the repository owner.
