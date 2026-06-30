---
name: html-slides
description: Generate stunning, animation-rich, self-contained HTML presentations from scratch or by converting PowerPoint files. This skill should be used when the user wants to create slides, build a presentation, make a pitch deck, convert a PPT/PPTX to web format, or enhance an existing HTML deck. Helps users discover their aesthetic through visual previews rather than abstract choices.
agent_created: true
---

# HTML Slides — Self-Contained Presentation Generator

Create zero-dependency, animation-rich HTML presentations that run entirely in the browser. Single HTML file, all CSS/JS inline. No npm, no build tools. Open in any browser and present.

## Core Principles

1. **Zero Dependencies** — Single HTML files with inline CSS/JS. No npm, no build tools, no frameworks. The file works 10 years later.
2. **Show, Don't Tell** — Generate visual previews for style selection. People discover what they want by seeing it, not by describing it.
3. **Distinctive Design** — No generic "AI slop." Every presentation must feel custom-crafted. Avoid purple-gradient-on-white clichés, Inter/Roboto/Arial as display fonts, cookie-cutter card grids.
4. **Progressive Disclosure** — This SKILL.md is a workflow map. Read lightweight indexes first; load detailed references only at the appropriate phase.
5. **Fixed 16:9 Stage (NON-NEGOTIABLE)** — Every deck uses a 1920×1080 slide canvas scaled as a whole to the viewport. Slides stay 16:9 on every screen including phones. Do NOT reflow slide content.

## Design Aesthetics Guidance

When generating presentations, focus on:

- **Typography**: Choose distinctive, beautiful fonts. Avoid Inter, Roboto, Arial, system fonts. Use Google Fonts or Fontshare. Pair display + body fonts thoughtfully.
- **Color & Theme**: Commit to a cohesive aesthetic via CSS variables. Dominant colors with sharp accents. Draw from cultural aesthetics and IDE themes for inspiration.
- **Motion**: Use animations for high-impact moments. Staggered reveals (animation-delay) create more delight than scattered micro-interactions. Reference [animation-patterns.md](references/animation-patterns.md).
- **Backgrounds**: Layer CSS gradients, geometric patterns, or contextual effects. Never default to solid colors alone.

**Avoid these generic patterns:**
- Overused fonts (Inter, Roboto, Arial, Space Grotesk on every deck)
- Clichéd color schemes (purple gradients on white)
- Predictable layouts and identical card grids
- Gratuitous glassmorphism, drop shadows without purpose

---

## Workflow

### Phase 0: Detect Mode

Determine what the user wants:

| Mode | Trigger | Next Phase |
|------|---------|------------|
| **A: New Presentation** | "做一份演示文稿", "create slides", "pitch deck" | Phase 1 |
| **B: PPT Conversion** | User provides a .pptx/.ppt file | Phase 4 |
| **C: Enhancement** | User wants to modify an existing HTML deck | Modify directly, following Fixed Stage Rules |
| **D: Style Transfer** | "change to X style", "switch theme", "换成X风格" | Style Transfer Protocol |

### Phase 1: Content Discovery

Ask ALL questions together using AskUserQuestion tool. Do not ask one at a time.

**Question 1 — Purpose**: What is this presentation for? Options: Pitch deck / Teaching-Tutorial / Conference talk / Internal presentation

**Question 2 — Length**: Approximately how many slides? Options: Short 5-10 / Medium 10-20 / Long 20+

**Question 3 — Content**: Do you have content ready? Options: All content ready / Rough notes / Topic only

**Question 4 — Density**: How dense should the deck feel?
- "Low density / speaker-led" — Big ideas, fewer words, more visual breathing room. One idea per slide, 1-3 bullets max.
- "High density / reading-first" — More self-contained detail for async reading. 4-8 bullets or 4-6 cards per slide.

If user has content, ask them to share it. Do NOT ask about inline editing at this stage — include it by default after draft generation.

**Image handling (if user provides images):**
1. Scan all image files (.png, .jpg, .svg, .webp)
2. Inspect each image using Read tool (multimodal)
3. Evaluate: what it shows, usable or not, what concept it represents, dominant colors
4. Co-design the outline — images inform slide structure alongside text
5. Confirm the outline with user

### Phase 2: Style Discovery

**This is the "show, don't tell" phase.** Most people cannot articulate design preferences in words.

Generate 3 distinct single-slide HTML previews showing typography, colors, animation, and overall aesthetic. Each preview must look like a real first slide from the user's deck, not a diagnostic card.

**Preview mix rules:**
- 1 safe preset from [style-presets.md](references/style-presets.md)
- 1 adventurous/wildcard option (another preset or custom design)
- 1 contextual option that best matches the user's purpose and mood

**Preview authenticity rules (NON-NEGOTIABLE):**
- Never render internal workflow text on a slide: no "preview", "Option A/B/C", "generated from", preset names, or file paths
- Never render user requirement notes as slide content (e.g. "bold and provocative")
- Use real deck chrome only: deck title, section title, date, author, page number, or genuine content phrases

Save previews to a temp directory (style-a.html, style-b.html, style-c.html). Open each preview via present_files for the user.

Ask user to pick: Style A / Style B / Style C / Mix elements.

### Phase 3: Generate Presentation

Generate the full presentation using content from Phase 1 and style from Phase 2.

**Before generating, read these reference files:**

| File | Purpose | When |
|------|---------|------|
| [references/viewport-base.css](references/viewport-base.css) | Mandatory fixed-stage CSS — include FULL contents in every presentation | Phase 3 (before generation) |
| [references/html-template.md](references/html-template.md) | HTML structure, JS features, code quality standards | Phase 3 (before generation) |
| [references/animation-patterns.md](references/animation-patterns.md) | Animation snippets and effect-to-feeling guide | Phase 3 (during generation) |
| [references/style-presets.md](references/style-presets.md) | Full preset definitions for the chosen style | Phase 2-3 (after user picks) |

**Key generation requirements:**

1. Single self-contained HTML file, all CSS/JS inline
2. Include FULL contents of viewport-base.css in the `<style>` block
3. Use fonts from Fontshare or Google Fonts — never system fonts
4. Add detailed comments explaining each section: `/* === SECTION NAME === */`
5. Include SlidePresentation class with keyboard/touch/wheel navigation
6. Include stage scaling JS (1920×1080 → viewport fit)
7. Include inline editing feature by default (hover hotzone + E key toggle)
8. **Include Speaker View** — press `S` key to open speaker window with BroadcastChannel sync (see [html-template.md](references/html-template.md) Speaker View section)
9. **Include Print/PDF styles** — `@media print` CSS for PDF export via browser print (see [html-template.md](references/html-template.md) Print/PDF section)
10. Support speaker notes via `.speaker-note` element or `data-speaker-note` attribute
11. Every element with animation uses `.reveal` class pattern
12. Support `prefers-reduced-motion`
13. Apply density choice throughout: speaker-led → fewer ideas per slide; reading-first → more self-contained detail
14. **NO style-specific classes in HTML content** — Decorations (gold lines, vertical signatures, brush decorations, wavy lines, etc.) must be implemented via CSS pseudo-elements (`::before`, `::after`) in the preset's Signature CSS (see `style-presets.md`). Never add style-specific divs/classes (e.g., `.gold-line-left`, `.vertical-sig`, `.brush-deco`) to the HTML content. This is CRITICAL for Style Transfer to work — the HTML must only use semantic classes from the system defined in `html-template.md`.

**Content overflow guardrails:**
- No scrolling, no overflow, no overlapping panels inside any slide
- No text below comfortable reading size at 1920×1080
- If content exceeds density limits, split into more slides instead of shrinking

### Phase 4: PPT Conversion

When converting PowerPoint files:

1. Run `python scripts/extract-pptx.py <input.pptx> <output_dir>` (install python-pptx if needed)
2. Present extracted slide titles, content summaries, image counts to user for confirmation
3. Proceed to Phase 2 for style discovery
4. Generate HTML preserving all text, images, slide order, and speaker notes (as HTML comments)


---

## Style Transfer Protocol

When user says: "change to X style", "switch to X theme", "换成X风格", "迁移到X风格"

### How it works

1. **Parse target style** — Identify which of the 12 presets the user wants
2. **Extract the contract** — Read the `:root {}` block and `<link>` font tags from `references/style-presets.md` for the target style
3. **Replace in HTML** — Only replace these parts in the existing HTML file:
   - The `:root {}` CSS block (the entire block)
   - The font `<link>` / `<style>` tags in `<head>`
   - The `var(--theme-name)` value (optional, for identification)
4. **Do NOT touch** — Any `.slide` content, `.reveal` classes, or semantic class names

### Why this works

The semantic class system (see `references/html-template.md`) ensures that HTML content is decoupled from visual style. The `:root {}` CSS variables are the contract:
- `.slide-title` maps to `var(--title-size)`, `var(--font-display)`, `var(--text-primary)`
- `.highlight` maps to `var(--accent)`
- `.quote-block` maps to `var(--quote-border)`, `var(--quote-bg)`
- `.col-2` uses `var(--col-2-gap)`

### Step-by-step

```
1. IDENTIFY target style preset (from user input)
2. READ references/style-presets.md → extract the `:root {}` block for that preset
3. READ the existing HTML file
4. FIND the current `:root {}` block in the HTML's `<style>` tag
5. REPLACE the `:root {}` block with the new one from the preset
6. FIND and REPLACE any font `<link>` tags in `<head>`
7. SAVE the updated HTML file
8. PREVIEW to verify
```

### Important notes

- **Font loading**: If the target style uses different fonts (Google Fonts vs Fontshare), update the `<link>` tags accordingly
- **Background gradient**: Some styles define `--bg-gradient` (e.g., Aurora, Lava). Make sure to include it
- **Print styles**: The `@media print {}` block should be preserved as-is (it's style-agnostic)
- **Speaker View**: The speaker view CSS is also style-agnostic and should be preserved
- **Verify**: After transfer, open the HTML and check that:
  - Colors changed to target style
  - Fonts changed to target style
  - Content is untouched (same text, same layout)

### Example

User says: "把这个演示文稿换成芭乐风格" (Change this presentation to Guava style)

```
1. Target style: 芭乐 Guava
2. Extract from style-presets.md:
   :root {
       --bg-primary: #fef5f0;
       --text-primary: #2a2a2a;
       --accent: #ff8fa3;
       ...
   }
   Font link: <link href="https://fonts.googleapis.com/css2?family=Caveat:wght@400;700&family=Nunito:wght@400;700&display=swap" rel="stylesheet">
3. In the HTML file, find and replace:
   - OLD `:root {}` → NEW `:root {}` (Guava version)
   - OLD font link → NEW font link (Caveat + Nunito)
4. Save and preview
```


### Phase 5: Delivery

1. Save the final HTML file to the project directory
2. Open via present_files for browser preview
3. Summarize: file location, style name, slide count, navigation controls (Arrow keys, Space, swipe), CSS variable customization, inline editing (hover top-left or press E)
4. **Tell user about Speaker View**: press `S` key to open speaker window (current slide + next slide + timer + notes)
5. **Tell user about PDF export**: press `Ctrl+P` → "另存为 PDF"，speaker notes print below each slide

### Phase 6: Share & Export (Optional)

After delivery, ask: _"Would you like to share this presentation? I can deploy it to a live URL or export it as a PDF."_

Options: Deploy to URL / Export to PDF / Both / No thanks

- **Deploy**: Use CloudStudio deploy tool (workbuddy_cloudstudio_deploy) for instant live URL
- **PDF**: User prints from browser (`Ctrl+P` → "另存为 PDF"), `@media print` styles included automatically

---

## Fixed Stage Rules (Reference)

For detailed CSS and implementation, read [references/viewport-base.css](references/viewport-base.css) before generating. Key invariants:

- Every slide is authored at fixed 1920×1080 inside `.deck-stage`
- The stage scales uniformly via JS transform — letterbox/pillarbox is acceptable, reflow is NOT
- Slide visibility controlled by `.active` / `.visible` classes — **never** use `display: none/block`
- No responsive breakpoints for slide content
- Use `calc(-1 * ...)` to negate CSS functions — browsers silently ignore `-clamp()`, `-min()`
- Include `prefers-reduced-motion` support

## Supporting Files Index

| File | Purpose | Load When |
|------|---------|-----------|
| references/viewport-base.css | Mandatory fixed-stage CSS | Phase 3 |
| references/html-template.md | HTML architecture, JS features, editing system | Phase 3 |
| references/animation-patterns.md | Animation snippets and feeling guide | Phase 3 |
| references/style-presets.md | Visual style definitions | Phase 2-3 |
| scripts/extract-pptx.py | PPT content extraction | Phase 4 |
