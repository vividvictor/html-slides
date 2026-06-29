# HTML Presentation Template

Reference architecture for generating slide presentations. Every presentation follows a fixed 16:9 stage model: slides are authored at 1920×1080 and the whole stage scales to fit the browser window.

## Base HTML Structure

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Presentation Title</title>

    <!-- Fonts: use Fontshare or Google Fonts — never system fonts -->
    <link rel="stylesheet" href="https://api.fontshare.com/v2/css?f[]=...">
    <!-- Or Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=..." rel="stylesheet">

    <style>
        /* ===========================================
           CSS CUSTOM PROPERTIES (THEME)
           Change these to change the whole look
           =========================================== */
        :root {
            /* Colors — from chosen style preset */
            --bg-primary: #0a0f1c;
            --bg-secondary: #111827;
            --text-primary: #ffffff;
            --text-secondary: #9ca3af;
            --accent: #00ffcc;
            --accent-glow: rgba(0, 255, 204, 0.3);
            --stage-bg: #000;
            --slide-bg: #fff;

            /* Typography — authored at 1920×1080 stage size */
            --font-display: 'Clash Display', sans-serif;
            --font-body: 'Satoshi', sans-serif;
            --title-size: 112px;
            --subtitle-size: 34px;
            --body-size: 28px;

            /* Spacing — authored at 1920×1080 stage size */
            --slide-padding: 72px;
            --content-gap: 32px;

            /* Animation */
            --ease-out-expo: cubic-bezier(0.16, 1, 0.3, 1);
            --duration-normal: 0.6s;
        }

        /* ===========================================
           BASE STYLES
           =========================================== */
        * { margin: 0; padding: 0; box-sizing: border-box; }

        /* --- PASTE viewport-base.css CONTENTS HERE --- */

        /* ===========================================
           ANIMATIONS
           Trigger via .visible class on the active slide
           =========================================== */
        .reveal {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity var(--duration-normal) var(--ease-out-expo),
                        transform var(--duration-normal) var(--ease-out-expo);
        }

        .slide.visible .reveal {
            opacity: 1;
            transform: translateY(0);
        }

        /* Stagger children for sequential reveal */
        .reveal:nth-child(1) { transition-delay: 0.1s; }
        .reveal:nth-child(2) { transition-delay: 0.2s; }
        .reveal:nth-child(3) { transition-delay: 0.3s; }
        .reveal:nth-child(4) { transition-delay: 0.4s; }
        .reveal:nth-child(5) { transition-delay: 0.5s; }
        .reveal:nth-child(6) { transition-delay: 0.6s; }

        /* ===========================================
           SLIDE CONTENT STYLES
           (Add preset-specific styles here)
           =========================================== */

        /* ... preset-specific styles ... */
    </style>
</head>
<body>
    <!-- Edit hotzone + toggle -->
    <div class="edit-hotzone"></div>
    <button class="edit-toggle" id="editToggle" title="Edit mode (E)">✏️</button>

    <div class="deck-viewport">
        <main class="deck-stage" id="deckStage">
            <section class="slide title-slide active">
                <h1 class="reveal">演示文稿标题</h1>
                <p class="reveal">副标题或作者</p>
            </section>

            <section class="slide">
                <div class="slide-content">
                    <h2 class="reveal">幻灯片标题</h2>
                    <p class="reveal">内容...</p>
                </div>
            </section>

            <!-- More slides... -->
        </main>
    </div>

    <script>
        /* ===========================================
           SLIDE PRESENTATION CONTROLLER
           =========================================== */
        class SlidePresentation {
            constructor() {
                this.slides = document.querySelectorAll('.slide');
                this.currentSlide = 0;
                this.totalSlides = this.slides.length;
                this.stage = document.getElementById('deckStage');
                this.setupStageScale();
                this.setupKeyboardNav();
                this.setupTouchNav();
                this.setupWheelNav();
                this.showSlide(0);
            }

            /* === Stage Scaling: Fit 1920×1080 to viewport === */
            setupStageScale() {
                const scale = () => {
                    const vw = window.innerWidth;
                    const vh = window.innerHeight;
                    const factor = Math.min(vw / 1920, vh / 1080);
                    const x = (vw - 1920 * factor) / 2;
                    const y = (vh - 1080 * factor) / 2;
                    this.stage.style.transform = `translate(${x}px, ${y}px) scale(${factor})`;
                };
                scale();
                window.addEventListener('resize', scale);
            }

            /* === Keyboard Navigation === */
            setupKeyboardNav() {
                document.addEventListener('keydown', (e) => {
                    if (this.editMode) return; // Don't navigate while editing
                    switch (e.key) {
                        case 'ArrowRight': case 'ArrowDown': case ' ': case 'PageDown':
                            this.next(); break;
                        case 'ArrowLeft': case 'ArrowUp': case 'PageUp':
                            this.prev(); break;
                        case 'Home': this.showSlide(0); break;
                        case 'End': this.showSlide(this.totalSlides - 1); break;
                    }
                });
            }

            /* === Touch/Swipe Navigation === */
            setupTouchNav() {
                let startX = 0;
                let startY = 0;
                document.addEventListener('touchstart', (e) => {
                    startX = e.touches[0].clientX;
                    startY = e.touches[0].clientY;
                });
                document.addEventListener('touchend', (e) => {
                    const dx = e.changedTouches[0].clientX - startX;
                    const dy = e.changedTouches[0].clientY - startY;
                    if (Math.abs(dx) > Math.abs(dy) && Math.abs(dx) > 50) {
                        dx < 0 ? this.next() : this.prev();
                    }
                });
            }

            /* === Mouse Wheel Navigation === */
            setupWheelNav() {
                let wheelTimeout = null;
                document.addEventListener('wheel', (e) => {
                    e.preventDefault();
                    if (wheelTimeout) return;
                    wheelTimeout = setTimeout(() => { wheelTimeout = null; }, 300);
                    e.deltaY > 0 ? this.next() : this.prev();
                }, { passive: false });
            }

            /* === Slide Switching === */
            showSlide(index) {
                this.currentSlide = Math.max(0, Math.min(index, this.totalSlides - 1));
                this.slides.forEach((slide, i) => {
                    slide.classList.toggle('active', i === this.currentSlide);
                    slide.classList.toggle('visible', i === this.currentSlide);
                });
            }

            next() { this.showSlide(this.currentSlide + 1); }
            prev() { this.showSlide(this.currentSlide - 1); }
        }

        /* ===========================================
           INLINE EDITING SYSTEM
           Hover top-left hotzone or press E to toggle
           =========================================== */
        class InlineEditor {
            constructor() {
                this.isActive = false;
                this.hotzone = document.querySelector('.edit-hotzone');
                this.toggle = document.getElementById('editToggle');
                this.hideTimeout = null;
                this.setupHotzone();
                this.setupKeyboard();
                this.setupToggle();
            }

            toggleEditMode() {
                this.isActive = !this.isActive;
                document.body.classList.toggle('edit-mode', this.isActive);
                this.toggle.classList.toggle('active', this.isActive);

                const editables = document.querySelectorAll('.slide.active h1, .slide.active h2, .slide.active h3, .slide.active p, .slide.active li');
                editables.forEach(el => {
                    el.contentEditable = this.isActive;
                    if (this.isActive) {
                        el.style.outline = '2px dashed rgba(0,255,204,0.4)';
                        el.style.cursor = 'text';
                    } else {
                        el.style.outline = '';
                        el.style.cursor = '';
                    }
                });
            }

            setupHotzone() {
                // Mouse enter hotzone → show toggle
                this.hotzone.addEventListener('mouseenter', () => {
                    clearTimeout(this.hideTimeout);
                    this.toggle.classList.add('show');
                });
                // Mouse leave hotzone → hide after 400ms grace
                this.hotzone.addEventListener('mouseleave', () => {
                    this.hideTimeout = setTimeout(() => {
                        if (!this.isActive) this.toggle.classList.remove('show');
                    }, 400);
                });
                // Click hotzone → toggle edit mode
                this.hotzone.addEventListener('click', () => {
                    this.toggleEditMode();
                });
            }

            setupToggle() {
                this.toggle.addEventListener('click', () => {
                    this.toggleEditMode();
                });
                this.toggle.addEventListener('mouseenter', () => {
                    clearTimeout(this.hideTimeout);
                });
                this.toggle.addEventListener('mouseleave', () => {
                    this.hideTimeout = setTimeout(() => {
                        if (!this.isActive) this.toggle.classList.remove('show');
                    }, 400);
                });
            }

            setupKeyboard() {
                document.addEventListener('keydown', (e) => {
                    if ((e.key === 'e' || e.key === 'E') && !e.target.getAttribute('contenteditable')) {
                        this.toggleEditMode();
                    }
                });
            }
        }

        /* ===========================================
           INITIALIZATION
           =========================================== */
        const presentation = new SlidePresentation();
        const editor = new InlineEditor();
    </script>
</body>
</html>
```

## Required JavaScript Features

Every presentation must include:

1. **SlidePresentation Class** — Main controller with:
   - Keyboard navigation (arrows, space, page up/down, Home/End)
   - Touch/swipe support for mobile
   - Mouse wheel navigation with debounce
   - Stage scaling (1920×1080 → viewport fit, letterbox/pillarbox acceptable)

2. **InlineEditor Class** — Post-draft editing affordance:
   - Hotzone hover detection with 400ms grace period
   - E key toggle (skip when editing text)
   - Click-to-edit on headings, paragraphs, and list items
   - Visual feedback (dashed outline on editable elements)

3. **Optional Enhancements** (match to chosen style):
   - Custom cursor with trail
   - Particle system background (canvas)
   - Parallax effects
   - 3D tilt on hover
   - Counter animations
   - Progress indicator / slide counter

## Inline Editing CSS

```css
/* Edit hotzone — top-left corner, invisible but hoverable */
.edit-hotzone {
    position: fixed;
    top: 0;
    left: 0;
    width: 80px;
    height: 80px;
    z-index: 10000;
    cursor: pointer;
}

/* Edit toggle button — hidden by default, revealed by hotzone hover */
.edit-toggle {
    position: fixed;
    top: 16px;
    left: 16px;
    opacity: 0;
    pointer-events: none;
    transition: opacity 0.3s ease;
    z-index: 10001;
    background: rgba(0, 0, 0, 0.6);
    border: 1px solid rgba(255, 255, 255, 0.2);
    border-radius: 8px;
    padding: 8px 12px;
    font-size: 14px;
    color: #fff;
}

.edit-toggle.show,
.edit-toggle.active {
    opacity: 1;
    pointer-events: auto;
}

.edit-toggle.active {
    background: rgba(0, 255, 204, 0.2);
    border-color: rgba(0, 255, 204, 0.5);
}

/* Edit mode body styles */
.edit-mode .slide.active {
    cursor: text;
}
```

**IMPORTANT: Do NOT use CSS `~` sibling selector for hover-based show/hide.** `pointer-events: none` breaks the hover chain. Must use JS with delay timeout.

## Image Pipeline (Skip If No Images)

If user provides images, process them before generating HTML:

| Situation | Operation |
|-----------|-----------|
| Square logo on rounded aesthetic | Crop circle (PIL) |
| Image > 1MB | Resize to max 1200px |
| Wrong aspect ratio | Manual crop |

Use direct file paths (not base64). Images go in an `assets/` folder alongside the HTML.

## Code Quality Standards

- **Comments**: Every section needs `/* === SECTION NAME === */` comment blocks
- **Accessibility**: Semantic HTML (`<section>`, `<main>`, `<nav>`), keyboard navigation, ARIA labels
- **`prefers-reduced-motion`**: Included in viewport-base.css
- **CSS variables**: All colors, fonts, spacing defined in `:root` for easy customization
- **No `display: none/block`** for slide switching — use `.active`/`.visible` with `visibility`, `opacity`, `pointer-events`

## File Structure

```
presentation.html    # Self-contained, all CSS/JS inline
assets/              # Images only, if any
```
