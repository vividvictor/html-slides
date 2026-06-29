# HTML Slides — Self-Contained Presentation Generator

> Generate stunning, animation-rich, self-contained HTML presentations from scratch or by converting PowerPoint files.

Zero dependencies. Single HTML file with inline CSS/JS. Open in any browser and present.

## Features

- **Zero Dependencies** — Single HTML file, all CSS/JS inline. No npm, no build tools.
- **Fixed 16:9 Stage** — 1920×1080 slide canvas that scales uniformly to any viewport. No reflow on mobile.
- **Style Discovery** — Generate 3 visual previews, pick by seeing not describing.
- **Animation-Rich** — Staggered reveals, scale transitions, blur effects, background patterns.
- **Inline Editing** — Hover top-left corner or press E to edit text directly in the browser.
- **PPT Conversion** — Convert PowerPoint files to HTML with style selection.
- **Distinctive Design** — 12 curated style presets, no generic "AI slop" aesthetics.

## Quick Start

This project is structured as a **WorkBuddy Skill**. The skill definition lives in `.workbuddy/skills/html-slides/`.

To use with WorkBuddy, the skill is automatically available when working in this project directory.

## Skill Structure

```
.workbuddy/skills/html-slides/
├── SKILL.md                      # Main workflow (progressive disclosure)
├── references/
│   ├── viewport-base.css         # Mandatory fixed-stage CSS
│   ├── html-template.md          # HTML architecture & JS features
│   ├── animation-patterns.md     # Animation reference & feeling guide
│   └── style-presets.md          # 12 curated visual style definitions
├── scripts/
│   └── extract-pptx.py           # PPT content extraction script
└── assets/                       # (Templates and assets, to be added)
```

## Style Presets

| # | Name | Vibe | Theme |
|---|------|------|-------|
| 1 | Bold Signal | Confident, high-impact | Dark |
| 2 | Electric Studio | Clean, professional | Dark |
| 3 | Creative Voltage | Energetic, retro-modern | Dark |
| 4 | Dark Botanical | Elegant, premium | Dark |
| 5 | Notebook Tabs | Editorial, tactile | Light |
| 6 | Pastel Geometry | Friendly, approachable | Light |
| 7 | Split Pastel | Playful, creative | Light |
| 8 | Vintage Editorial | Witty, personality-driven | Light |
| 9 | Neon Cyber | Futuristic, techy | Specialty |
| 10 | Terminal Green | Developer, hacker | Specialty |
| 11 | Swiss Modern | Clean, Bauhaus | Specialty |
| 12 | Paper & Ink | Literary, thoughtful | Specialty |

## Technical Constraints

- Slide canvas: fixed 1920×1080, scaled via JS transform
- Visibility control: `.active`/`.visible` classes (never `display: none/block`)
- CSS function negation: `calc(-1 * clamp(...))` (never `-clamp()`)
- Fonts: Google Fonts or Fontshare only (never system fonts)
- `prefers-reduced-motion` support required
- No scrolling, overflow, or overlapping panels inside slides

## Workflow

1. **Phase 0** — Detect mode (new / PPT conversion / enhancement)
2. **Phase 1** — Content discovery (purpose, length, density, content)
3. **Phase 2** — Style discovery (3 visual previews, pick one)
4. **Phase 3** — Generate presentation (single HTML file)
4. **Phase 4** — PPT conversion (optional)
5. **Phase 5** — Delivery & preview
6. **Phase 6** — Share & export (CloudStudio deploy / PDF export)

## Status

**Framework established.** Style presets and detailed design rules will be refined based on user preference discussions.

## License

MIT
