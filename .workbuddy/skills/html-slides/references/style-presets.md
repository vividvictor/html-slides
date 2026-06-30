# Style Presets — Complete `:root {}` Contracts

Each preset defines the COMPLETE CSS variable contract.
For style transfer, only the `:root {}` block and font `<link>` tags are replaced.

---

## 1. 建筑 Architect

**氛围：** Bauhaus × 瑞士国际主义 — 理性、网格、功能

**字体：**
- Display: `Archivo Black` (400) — Google Fonts
- Body: `Nunito Sans` (400/600) — Google Fonts

**Font CDN:**
```html
<link href="https://fonts.googleapis.com/css2?family=Archivo+Black&family=Nunito+Sans:wght@400;600&display=swap" rel="stylesheet">
```

**Colors:**
```css
:root {
    /* Identity */
    --theme-name: 'Architect';
    --theme-version: '1.0';

    /* Background */
    --bg-primary: #f8f8f8;
    --bg-secondary: #eeeeee;
    --bg-gradient: none;
    --stage-bg: #f0f0f0;
    --slide-bg: #f8f8f8;

    /* Text */
    --text-primary: #1a1a1a;
    --text-secondary: #555555;
    --text-muted: #999999;

    /* Accent */
    --accent: #e63322;
    --accent-secondary: #1a1a1a;
    --accent-tertiary: #ffc400;
    --accent-glow: rgba(230,51,34,0.1);
    --accent-text: #ffffff;

    /* Border & Divider */
    --border-color: rgba(0,0,0,0.1);
    --divider-color: rgba(0,0,0,0.08);
    --shadow-color: rgba(0,0,0,0.08);

    /* Special */
    --quote-border: var(--accent);
    --quote-bg: rgba(230,51,34,0.03);
    --tag-bg: rgba(230,51,34,0.08);
    --tag-text: var(--accent);

    /* Typography */
    --font-display: 'Archivo Black', sans-serif;
    --font-body: 'Nunito Sans', sans-serif;
    --font-mono: 'JetBrains Mono', monospace;
    --title-size: 96px;
    --body-size: 28px;
    --note-size: 18px;

    /* Spacing */
    --slide-padding: 80px;
    --content-gap: 32px;
    --col-gap: 64px;

    /* Animation */
    --ease-out-expo: cubic-bezier(0.16, 1, 0.3, 1);
    --duration-normal: 0.6s;
}
```

**Signature CSS (pseudo-elements, style transfer safe):**
```css
/* Signature: red grid line at top */
.slide::before {
    content: '';
    position: absolute;
    top: 80px; left: 80px; right: 80px;
    height: 1px;
    background: var(--accent);
    opacity: 0.3;
    pointer-events: none;
}
```

---

## 2. 熔岩 Lava

**氛围：** Netflix 纪录片感 — 暗底暖光、电影叙事

**字体：**
- Display: `Syne` (800) — Google Fonts
- Body: `Space Grotesk` (400/700) — Google Fonts

**Font CDN:**
```html
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@800&family=Space+Grotesk:wght@400;700&display=swap" rel="stylesheet">
```

**Colors:**
```css
:root {
    --theme-name: 'Lava';
    --theme-version: '1.0';
    --bg-primary: #0d0d0d;
    --bg-gradient: linear-gradient(180deg, #0d0d0d 0%, #1a1008 70%, #2d1a0a 100%);
    --stage-bg: #000;
    --slide-bg: #0d0d0d;
    --text-primary: #f0ece6;
    --text-secondary: #8a8279;
    --text-muted: #5a5a5a;
    --accent: #ff6b35;
    --accent-secondary: #d4a574;
    --accent-tertiary: #ff9f1a;
    --accent-glow: rgba(255,107,53,0.15);
    --accent-text: #000000;
    --border-color: rgba(255,255,255,0.08);
    --divider-color: rgba(255,107,53,0.15);
    --shadow-color: rgba(255,107,53,0.2);
    --quote-border: var(--accent);
    --quote-bg: rgba(255,107,53,0.05);
    --tag-bg: rgba(255,107,53,0.12);
    --tag-text: var(--accent);
    --font-display: 'Syne', sans-serif;
    --font-body: 'Space Grotesk', sans-serif;
    --font-mono: 'JetBrains Mono', monospace;
    --title-size: 88px;
    --body-size: 30px;
    --note-size: 20px;
    --slide-padding: 100px;
    --content-gap: 40px;
    --col-gap: 80px;
    --ease-out-expo: cubic-bezier(0.16, 1, 0.3, 1);
    --duration-normal: 0.7s;
}
```

**Signature CSS:**
```css
/* Signature: warm glow gradient background (defined in --bg-gradient) */
/* No additional pseudo-elements needed — gradient is in --bg-gradient */
```

---

## 3. 极光 Aurora

**氛围：** Stripe/Linear 科技感 — mesh gradient 流动

**字体：**
- Display: `Clash Display` (600/700) — Fontshare
- Body: `Satoshi` (400/500/700) — Fontshare

**Font CDN:**
```html
<link rel="stylesheet" href="https://api.fontshare.com/v2/css?f[]=clash-display@600,700&f[]=satoshi@400,500,700&display=swap">
```

**Colors:**
```css
:root {
    --theme-name: 'Aurora';
    --theme-version: '1.0';
    --bg-primary: #0a0f1c;
    --bg-gradient: none;
    --stage-bg: #000;
    --slide-bg: #0a0f1c;
    --text-primary: #e8eaf0;
    --text-secondary: #6b7280;
    --text-muted: #4b5563;
    --accent-cyan: #00ffc8;
    --accent-violet: #a855f7;
    --accent-rose: #f43f5e;
    --accent: #00ffc8;
    --accent-glow: rgba(0,255,200,0.12);
    --accent-text: #000000;
    --mesh-1: rgba(168,85,247,0.2);
    --mesh-2: rgba(0,255,200,0.12);
    --mesh-3: rgba(244,63,94,0.1);
    --border-color: rgba(255,255,255,0.06);
    --divider-color: rgba(0,255,200,0.12);
    --shadow-color: rgba(0,255,200,0.15);
    --quote-border: var(--accent-cyan);
    --quote-bg: rgba(0,255,200,0.04);
    --tag-bg: rgba(0,255,200,0.1);
    --tag-text: var(--accent-cyan);
    --font-display: 'Clash Display', sans-serif;
    --font-body: 'Satoshi', sans-serif;
    --font-mono: 'JetBrains Mono', monospace;
    --title-size: 112px;
    --body-size: 28px;
    --note-size: 18px;
    --slide-padding: 72px;
    --content-gap: 32px;
    --col-gap: 64px;
    --ease-out-expo: cubic-bezier(0.16, 1, 0.3, 1);
    --duration-normal: 0.6s;
}
```

**Signature CSS:**
```css
/* Signature: mesh gradient background via pseudo-element */
.slide::before {
    content: '';
    position: absolute;
    top: 0; left: 0;
    width: 100%; height: 100%;
    background:
        radial-gradient(ellipse 600px 600px at 20% 30%, var(--mesh-1, rgba(168,85,247,0.2)) no-repeat,
        radial-gradient(ellipse 500px 500px at 70% 60%, var(--mesh-2, rgba(0,255,200,0.12)) no-repeat,
        radial-gradient(ellipse 400px 400px at 50% 80%, var(--mesh-3, rgba(244,63,94,0.1)) no-repeat;
    opacity: 1;
    pointer-events: none;
}
```

---

## 4. 赤金 Aureate

**氛围：** 投行路演 — 深蓝+金线、奢华权威

**字体：**
- Display: `Playfair Display` (700/900) — Google Fonts
- Body: `Source Sans 3` (400/600) — Google Fonts

**Font CDN:**
```html
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&family=Source+Sans+3:wght@400;600&display=swap" rel="stylesheet">
```

**Colors:**
```css
:root {
    --theme-name: 'Aureate';
    --theme-version: '1.0';
    --bg-primary: #0a1628;
    --bg-gradient: linear-gradient(135deg, #0a1628 0%, #132244 50%, #0a1628 100%);
    --stage-bg: #000;
    --slide-bg: #0a1628;
    --text-primary: #f5f0e8;
    --text-secondary: #8a9ab5;
    --text-muted: #5a6a7a;
    --accent-gold: #c9a96e;
    --accent-gold-light: #e8d4b0;
    --accent-gold-glow: rgba(201,169,110,0.12);
    --accent: var(--accent-gold);
    --accent-text: #000000;
    --border-color: rgba(201,169,110,0.15);
    --divider-color: rgba(201,169,110,0.12);
    --shadow-color: rgba(201,169,110,0.1);
    --quote-border: var(--accent-gold);
    --quote-bg: rgba(201,169,110,0.04);
    --tag-bg: rgba(201,169,110,0.1);
    --tag-text: var(--accent-gold);
    --font-display: 'Playfair Display', serif;
    --font-body: 'Source Sans 3', sans-serif;
    --font-mono: 'JetBrains Mono', monospace;
    --title-size: 80px;
    --body-size: 30px;
    --note-size: 20px;
    --slide-padding: 100px;
    --content-gap: 40px;
    --col-gap: 80px;
    --ease-out-expo: cubic-bezier(0.16, 1, 0.3, 1);
    --duration-normal: 0.8s;
}
```

**Signature CSS:**
```css
/* Signature: gold diagonal line decoration */
.slide::before {
    content: '';
    position: absolute;
    top: 0; left: 0;
    width: 100%; height: 100%;
    background: linear-gradient(135deg, transparent 0%, transparent 48%, var(--accent-gold, #c9a96e) 48%, var(--accent-gold, #c9a96e) 48.5%, transparent 48.5%) no-repeat;
    opacity: 0.08;
    pointer-events: none;
}
```

---

## 5. 雾林 Mist Grove

**氛围：** Biophilic 可持续 — 深林+暖光斑

**字体：**
- Display: `DM Serif Display` (400/700) — Google Fonts
- Body: `DM Sans` (400/500) — Google Fonts

**Font CDN:**
```html
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:wght@400;700&family=DM+Sans:wght@400;500&display=swap" rel="stylesheet">
```

**Colors:**
```css
:root {
    --theme-name: 'Mist Grove';
    --theme-version: '1.0';
    --bg-primary: #0f1f17;
    --bg-gradient: linear-gradient(160deg, #0f1f17 0%, #1a3025 60%, #0f1f17 100%);
    --stage-bg: #0a0a0a;
    --slide-bg: #0f1f17;
    --text-primary: #e8e4d9;
    --text-secondary: #8a9a80;
    --text-muted: #5a6a50;
    --accent-light: #f0e6d0;
    --accent-moss: #7a9a6a;
    --accent-amber: #d4a056;
    --accent: var(--accent-light);
    --accent-glow: rgba(240,230,208,0.1);
    --accent-text: #0f1f17;
    --border-color: rgba(240,230,208,0.1);
    --divider-color: rgba(240,230,208,0.08);
    --shadow-color: rgba(240,230,208,0.08);
    --quote-border: var(--accent-moss);
    --quote-bg: rgba(122,154,106,0.06);
    --tag-bg: rgba(122,154,106,0.15);
    --tag-text: var(--accent-light);
    --font-display: 'DM Serif Display', serif;
    --font-body: 'DM Sans', sans-serif;
    --font-mono: 'JetBrains Mono', monospace;
    --title-size: 72px;
    --body-size: 30px;
    --note-size: 20px;
    --slide-padding: 100px;
    --content-gap: 40px;
    --col-gap: 80px;
    --ease-out-expo: cubic-bezier(0.16, 1, 0.3, 1);
    --duration-normal: 0.9s;
}
```

**Signature CSS:**
```css
/* Signature: forest light spots via radial-gradient */
.slide::before {
    content: '';
    position: absolute;
    top: 0; left: 0;
    width: 100%; height: 100%;
    background:
        radial-gradient(circle 80px at 20% 30%, rgba(240,230,208,0.06) no-repeat,
        radial-gradient(circle 120px at 75% 60%, rgba(240,230,208,0.04)) no-repeat;
    pointer-events: none;
}
```

---

## 6. 冰川 Glacier

**氛围：** Nordic 极简 — 冰蓝、纯净

**字体：**
- Display+Body: `Outfit` (300/400/600/700) — Google Fonts

**Font CDN:**
```html
<link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;600;700&display=swap" rel="stylesheet">
```

**Colors:**
```css
:root {
    --theme-name: 'Glacier';
    --theme-version: '1.0';
    --bg-primary: #f8fafc;
    --bg-secondary: #e2e8f0;
    --bg-gradient: none;
    --stage-bg: #f0f4f8;
    --slide-bg: #f8fafc;
    --text-primary: #0f172a;
    --text-secondary: #64748b;
    --text-muted: #94a3b8;
    --accent: #0ea5e9;
    --accent-secondary: #6366f1;
    --accent-tertiary: #06b6d4;
    --accent-glow: rgba(14,165,233,0.1);
    --accent-text: #ffffff;
    --border-color: rgba(14,165,233,0.12);
    --divider-color: rgba(14,165,233,0.1);
    --shadow-color: rgba(14,165,233,0.08);
    --quote-border: var(--accent);
    --quote-bg: rgba(14,165,233,0.04);
    --tag-bg: rgba(14,165,233,0.1);
    --tag-text: var(--accent);
    --font-display: 'Outfit', sans-serif;
    --font-body: 'Outfit', sans-serif;
    --font-mono: 'JetBrains Mono', monospace;
    --title-size: 96px;
    --body-size: 28px;
    --note-size: 18px;
    --slide-padding: 80px;
    --content-gap: 32px;
    --col-gap: 64px;
    --ease-out-expo: cubic-bezier(0.16, 1, 0.3, 1);
    --duration-normal: 0.5s;
}
```

**Signature CSS:**
```css
/* Signature: thin ice-blue vertical line */
.slide::after {
    content: '';
    position: absolute;
    right: 120px;
    top: 60px; bottom: 60px;
    width: 1px;
    background: var(--accent);
    opacity: 0.15;
    pointer-events: none;
}
```

---

## 7. 混凝土 Concrete

**氛围：** Neo-Brutalism — 柏林设计、粗边框、硬阴影

**字体：**
- Display: `Space Grotesk` (700) — Google Fonts
- Body: `Space Mono` (400/700) — Google Fonts

**Font CDN:**
```html
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@700&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
```

**Colors:**
```css
:root {
    --theme-name: 'Concrete';
    --theme-version: '1.0';
    --bg-primary: #f0f0f0;
    --bg-secondary: #e0e0e0;
    --bg-gradient: none;
    --stage-bg: #e8e8e8;
    --slide-bg: #f0f0f0;
    --text-primary: #1a1a1a;
    --text-secondary: #555555;
    --text-muted: #888888;
    --accent-1: #ff3366;
    --accent-2: #00cc88;
    --accent-3: #ffcc00;
    --accent: var(--accent-1);
    --accent-glow: rgba(255,51,102,0.1);
    --accent-text: #ffffff;
    --border-bold: #1a1a1a;
    --border-color: #1a1a1a;
    --divider-color: rgba(0,0,0,0.12);
    --shadow-color: rgba(0,0,0,0.2);
    --quote-border: var(--border-bold);
    --quote-bg: #e8e8e8;
    --tag-bg: var(--accent-1);
    --tag-text: #ffffff;
    --font-display: 'Space Grotesk', sans-serif;
    --font-body: 'Space Mono', monospace;
    --font-mono: 'Space Mono', monospace;
    --title-size: 80px;
    --body-size: 26px;
    --note-size: 18px;
    --slide-padding: 72px;
    --content-gap: 32px;
    --col-gap: 64px;
    --ease-out-expo: cubic-bezier(0.16, 1, 0.3, 1);
    --duration-normal: 0.4s;
}
```

**Signature CSS:**
```css
/* Signature: hard shadow on .slide (Brutalist) */
.slide {
    border: 3px solid var(--border-bold, #1a1a1a);
    box-shadow: 4px 4px 0px var(--border-bold, #1a1a1a);
}
```

---

## 8. 纸墨 Ink Paper

**氛围：** 当代编辑设计 — 文人感、墨红标注

**字体：**
- Display: `Cormorant Garamond` (600/700) — Google Fonts
- Body: `IBM Plex Sans` (400/500) — Google Fonts

**Font CDN:**
```html
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@600;700&family=IBM+Plex+Sans:wght@400;500&display=swap" rel="stylesheet">
```

**Colors:**
```css
:root {
    --theme-name: 'Ink Paper';
    --theme-version: '1.0';
    --bg-primary: #faf8f3;
    --bg-secondary: #f0ece4;
    --bg-gradient: none;
    --stage-bg: #f5f0e8;
    --slide-bg: #faf8f3;
    --text-primary: #1a1a1a;
    --text-secondary: #555555;
    --text-muted: #888888;
    --accent: #c41e3a;
    --accent-light: #f8e8ec;
    --accent-glow: rgba(196,30,58,0.08);
    --accent-text: #ffffff;
    --border-color: rgba(0,0,0,0.08);
    --divider-color: #d4d0c8;
    --shadow-color: rgba(0,0,0,0.06);
    --quote-border: var(--accent);
    --quote-bg: rgba(196,30,58,0.03);
    --tag-bg: rgba(196,30,58,0.08);
    --tag-text: var(--accent);
    --font-display: 'Cormorant Garamond', serif;
    --font-body: 'IBM Plex Sans', sans-serif;
    --font-mono: 'IBM Plex Mono', monospace;
    --title-size: 88px;
    --body-size: 30px;
    --note-size: 20px;
    --slide-padding: 80px;
    --content-gap: 36px;
    --col-gap: 64px;
    --ease-out-expo: cubic-bezier(0.16, 1, 0.3, 1);
    --duration-normal: 0.6s;
}
```

**Signature CSS:**
```css
/* Signature: elegant horizontal divider line */
.slide-title::after {
    content: '';
    display: block;
    width: 80px;
    height: 1px;
    background: var(--divider-color, #d4d0c8);
    margin: 24px auto 0;
    opacity: 0.5;
}
```

---

## 9. 电光 Volt

**氛围：** 创业路演 — 电光青+热粉红、高能量

**字体：**
- Display: `Clash Display` (600/700) — Fontshare
- Body: `Satoshi` (400/500/700) — Fontshare

**Font CDN:**
```html
<link rel="stylesheet" href="https://api.fontshare.com/v2/css?f[]=clash-display@600,700&f[]=satoshi@400,500,700&display=swap">
```

**Colors:**
```css
:root {
    --theme-name: 'Volt';
    --theme-version: '1.0';
    --bg-primary: #0a0a0a;
    --bg-secondary: #141414;
    --bg-gradient: none;
    --stage-bg: #000;
    --slide-bg: #0a0a0a;
    --text-primary: #ffffff;
    --text-secondary: #888888;
    --text-muted: #555555;
    --accent-electric: #00e5ff;
    --accent-hot: #ff2d55;
    --accent: var(--accent-electric);
    --accent-glow: rgba(0,229,255,0.2);
    --accent-text: #000000;
    --border-color: rgba(0,229,255,0.15);
    --divider-color: rgba(0,229,255,0.1);
    --shadow-color: rgba(0,229,255,0.15);
    --quote-border: var(--accent-electric);
    --quote-bg: rgba(0,229,255,0.04);
    --tag-bg: rgba(0,229,255,0.12);
    --tag-text: var(--accent-electric);
    --font-display: 'Clash Display', sans-serif;
    --font-body: 'Satoshi', sans-serif;
    --font-mono: 'JetBrains Mono', monospace;
    --title-size: 120px;
    --body-size: 28px;
    --note-size: 18px;
    --slide-padding: 80px;
    --content-gap: 32px;
    --col-gap: 64px;
    --ease-out-expo: cubic-bezier(0.16, 1, 0.3, 1);
    --duration-normal: 0.4s;
}
```

**Signature CSS:**
```css
/* Signature: electric glow on .slide-title */
.slide-title {
    text-shadow: 0 0 20px var(--accent-glow, rgba(0,229,255,0.2));
}
```

---

## 10. 砂岩 Sandstone

**氛围：** 地中海生活方式 — 赤陶+橄榄、温暖

**字体：**
- Display: `Fraunces` (400/700) — Google Fonts
- Body: `Work Sans` (400/500) — Google Fonts

**Font CDN:**
```html
<link href="https://fonts.googleapis.com/css2?family=Fraunces:wght@400;700&family=Work+Sans:wght@400;500&display=swap" rel="stylesheet">
```

**Colors:**
```css
:root {
    --theme-name: 'Sandstone';
    --theme-version: '1.0';
    --bg-primary: #f5efe6;
    --bg-secondary: #e8dcc8;
    --bg-gradient: none;
    --stage-bg: #f0e8d8;
    --slide-bg: #f5efe6;
    --text-primary: #2d1f14;
    --text-secondary: #6b5344;
    --text-muted: #8a7a6a;
    --accent-terra: #c4654a;
    --accent-sand: #d4b896;
    --accent-olive: #7a8a5a;
    --accent: var(--accent-terra);
    --accent-glow: rgba(196,101,74,0.12);
    --accent-text: #ffffff;
    --border-color: rgba(45,31,20,0.1);
    --divider-color: rgba(196,101,74,0.15);
    --shadow-color: rgba(45,31,20,0.08);
    --quote-border: var(--accent-terra);
    --quote-bg: rgba(196,101,74,0.04);
    --tag-bg: rgba(196,101,74,0.12);
    --tag-text: var(--accent-terra);
    --font-display: 'Fraunces', serif;
    --font-body: 'Work Sans', sans-serif;
    --font-mono: 'JetBrains Mono', monospace;
    --title-size: 80px;
    --body-size: 30px;
    --note-size: 20px;
    --slide-padding: 80px;
    --content-gap: 36px;
    --col-gap: 64px;
    --ease-out-expo: cubic-bezier(0.16, 1, 0.3, 1);
    --duration-normal: 0.5s;
}
```

**Signature CSS:**
```css
/* Signature: warm terra cotta rounded corner on .slide */
.slide {
    border-radius: 16px;
    background: var(--slide-bg);
}
```

---

## 11. 芭乐 Guava

**氛围：** 温暖手绘 — 芭乐粉+皮绿、有机圆润

**字体：**
- Display: `Caveat` (700) — Google Fonts (handwriting)
- Body: `Nunito` (400/600) — Google Fonts

**Font CDN:**
```html
<link href="https://fonts.googleapis.com/css2?family=Caveat:wght@700&family=Nunito:wght@400;600&display=swap" rel="stylesheet">
```

**Colors:**
```css
:root {
    --theme-name: 'Guava';
    --theme-version: '1.0';
    --bg-primary: #fef5f0;
    --bg-secondary: #fce8e0;
    --bg-warm: #faf0e8;
    --bg-gradient: none;
    --stage-bg: #fef5f0;
    --slide-bg: #fef5f0;
    --text-primary: #3d2b1f;
    --text-secondary: #7a5c4a;
    --text-muted: #a08060;
    --accent-pink: #ff8fa3;
    --accent-pink-light: #ffd4db;
    --accent-green: #5a8a6a;
    --accent: var(--accent-pink);
    --accent-glow: rgba(255,143,163,0.15);
    --accent-text: #3d2b1f;
    --wavy-opacity: 0.12;
    --border-color: rgba(255,143,163,0.2);
    --divider-color: rgba(90,138,106,0.15);
    --shadow-color: rgba(255,143,163,0.1);
    --quote-border: var(--accent-pink);
    --quote-bg: rgba(255,143,163,0.05);
    --tag-bg: rgba(255,143,163,0.15);
    --tag-text: var(--accent-pink);
    --font-display: 'Caveat', cursive;
    --font-body: 'Nunito', sans-serif;
    --font-mono: 'JetBrains Mono', monospace;
    --title-size: 72px;
    --body-size: 30px;
    --note-size: 20px;
    --slide-padding: 80px;
    --content-gap: 36px;
    --col-gap: 64px;
    --ease-out-expo: cubic-bezier(0.34, 1.56, 0.64, 1);
    --duration-normal: 0.5s;
}
```

**Signature CSS:**
```css
/* Signature: wavy organic decoration via pseudo-element */
.slide::before {
    content: '';
    position: absolute;
    bottom: 40px; left: 40px; right: 40px;
    height: 20px;
    background: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 200 20'%3E%3Cpath d='M0 10 Q50 0 100 10 T200 10' stroke='%23ff8fa3' fill='none' stroke-width='2' opacity='0.3'/%3E%3C/svg%3E") repeat-x;
    opacity: var(--wavy-opacity, 0.12);
    pointer-events: none;
}
```

---

## 12. 玄金 Obsidian

**氛围：** 冷静沉着中国风 — 漆器+描金

**字体：**
- Display: `Noto Serif SC` (700/900) — Google Fonts
- Accent: `Ma Shan Zheng` (400) — Google Fonts (brush calligraphy)
- Body: `Noto Sans SC` (400/500) — Google Fonts

**Font CDN:**
```html
<link href="https://fonts.googleapis.com/css2?family=Noto+Serif+SC:wght@700;900&family=Ma+Shan+Zheng&family=Noto+Sans+SC:wght@400;500&display=swap" rel="stylesheet">
```

**Colors:**
```css
:root {
    --theme-name: 'Obsidian';
    --theme-version: '1.0';
    --bg-primary: #0d0d0d;
    --bg-gradient: linear-gradient(135deg, #0d0d0d 0%, #1a1510 50%, #0d0d0d 100%);
    --stage-bg: #000;
    --slide-bg: #0d0d0d;
    --text-primary: #f5efe6;
    --text-secondary: #8a7e6a;
    --text-muted: #5a5a4a;
    --accent-gold: #c49b3a;
    --accent-gold-light: #e8d4b0;
    --accent-gold-glow: rgba(196,155,58,0.15);
    --accent-red: #8b2500;
    --accent: var(--accent-gold);
    --accent-text: #0d0d0d;
    --border-gold: rgba(196,155,58,0.3);
    --pattern-opacity: 0.04;
    --border-color: rgba(196,155,58,0.2);
    --divider-color: rgba(196,155,58,0.15);
    --shadow-color: rgba(196,155,58,0.1);
    --quote-border: var(--accent-gold);
    --quote-bg: rgba(196,155,58,0.04);
    --tag-bg: rgba(196,155,58,0.12);
    --tag-text: var(--accent-gold);
    --font-display: 'Noto Serif SC', serif;
    --font-body: 'Noto Sans SC', sans-serif;
    --font-mono: 'Noto Sans SC', sans-serif;
    --font-brush: 'Ma Shan Zheng', cursive;
    --title-size: 64px;
    --body-size: 32px;
    --note-size: 20px;
    --slide-padding: 100px;
    --content-gap: 32px;
    --col-gap: 80px;
    --ease-out-expo: cubic-bezier(0.16, 1, 0.3, 1);
    --duration-normal: 0.8s;
}
```

**Signature CSS:**
```css
/* Signature: fret/cloud pattern background + gold vertical line */
.slide::before {
    content: '';
    position: absolute;
    top: 0; left: 0;
    width: 100%; height: 100%;
    background-image:
        repeating-linear-gradient(0deg, transparent, transparent 79px, var(--border-color, rgba(196,155,58,0.2)) 79px, var(--border-color, rgba(196,155,58,0.2)) 80px),
        repeating-linear-gradient(90deg, transparent, transparent 79px, var(--border-color, rgba(196,155,58,0.2)) 79px, var(--border-color, rgba(196,155,58,0.2)) 80px);
    background-size: 80px 80px;
    opacity: var(--pattern-opacity, 0.04);
    pointer-events: none;
}
.slide::after {
    content: '';
    position: absolute;
    left: 120px;
    top: 80px; bottom: 80px;
    width: 1px;
    background: var(--accent-gold, var(--accent));
    opacity: 0.25;
    pointer-events: none;
}
```

---

## 字体配对速查

| 预设 | 展示字体 | 正文字体 | 来源 |
|------|----------|----------|------|
| 建筑 Architect | Archivo Black | Nunito Sans | Google |
| 熔岩 Lava | Syne | Space Grotesk | Google |
| 极光 Aurora | Clash Display | Satoshi | Fontshare |
| 赤金 Aureate | Playfair Display | Source Sans 3 | Google |
| 雾林 Mist Grove | DM Serif Display | DM Sans | Google |
| 冰川 Glacier | Outfit | Outfit | Google |
| 混凝土 Concrete | Space Grotesk | Space Mono | Google |
| 纸墨 Ink Paper | Cormorant Garamond | IBM Plex Sans | Google |
| 电光 Volt | Clash Display | Satoshi | Fontshare |
| 砂岩 Sandstone | Fraunces | Work Sans | Google |
| 芭乐 Guava | Caveat | Nunito | Google |
| 玄金 Obsidian | Noto Serif SC + Ma Shan Zheng | Noto Sans SC | Google |

---

## CSS 陷阱

### CSS 函数取负

**错误——浏览器静默忽略（无报错）：**
```css
right: -clamp(28px, 3.5vw, 44px);   /* 浏览器忽略 */
margin-left: -min(10vw, 100px);      /* 浏览器忽略 */
```

**正确——用 `calc()` 包装：**
```css
right: calc(-1 * clamp(28px, 3.5vw, 44px));  /* 有效 */
margin-left: calc(-1 * min(10vw, 100px));     /* 有效 */
```

CSS 不允许函数名前直接加 `-`。浏览器会静默丢弃整条声明——无报错，只是位置错误。**始终使用 `calc(-1 * ...)` 来取负 CSS 函数值。**
