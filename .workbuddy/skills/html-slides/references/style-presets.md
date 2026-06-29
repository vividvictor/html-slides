# 风格预设参考

为 HTML Slides 精选的视觉风格。每一套预设都源自当代国际设计趋势——拒绝千篇一律的"AI 稀烂美学"。**仅用抽象形状——不用插画。**

**Viewport CSS：** 每份演示文稿必须包含 [viewport-base.css](viewport-base.css) 中的强制基础样式。

---

## 1. 建筑 Architect

**氛围：** 精准、克制、国际、理性——如建筑蓝图般的秩序感

**布局：** 网格可见，不对称排列。大标题偏左或偏右，刻意留白。红线点缀。

**设计灵感：** Bauhaus × 当代瑞士设计。参考：Dieter Rams、Lotta Nieminen、瑞士国际主义海报。

**Typography:**
- Display: `Archivo Black` (900) — 无衬线，厚重，工业感
- Body: `Nunito Sans` (400/600) — 柔和圆润，与厚重标题形成对话

**Font CDN:**
```html
<link href="https://fonts.googleapis.com/css2?family=Archivo+Black&family=Nunito+Sans:wght@400;600&display=swap" rel="stylesheet">
```

**Colors:**
```css
:root {
    --bg-primary: #ffffff;
    --bg-secondary: #f5f5f5;
    --text-primary: #1a1a1a;
    --text-secondary: #666666;
    --accent: #e63322;        /* 红线——建筑标注色 */
    --accent-light: #fce4e4;
    --grid-line: rgba(0,0,0,0.08);
    --stage-bg: #ffffff;
    --slide-bg: #ffffff;
}
```

**Signature Elements:**
- 可见网格线（0.08 透明度），贯穿全页
- 红色细线或红色数字标注（01 / 02 / 03）
- 不对称布局——标题占 2/3，留白占 1/3
- 刻意的空白区域，不做填充
- 无圆角，纯直角

---

## 2. 熔岩 Lava

**氛围：** 电影感、沉稳、叙事性——像 Netflix 原创纪录片的开场

**布局：** 全幅深色背景，中心内容区。底部暖光渐变，如熔岩透出的光。

**设计灵感：** 电影标题序列 × 深色品牌站。参考：Netflix、HBO、Apple TV+ 纪录片视觉。

**Typography:**
- Display: `Syne` (700/800) — 前卫无衬线，几何感强
- Body: `Space Grotesk` (400/500) — 当代科技感

**Font CDN:**
```html
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@700;800&family=Space+Grotesk:wght@400;500&display=swap" rel="stylesheet">
```

**Colors:**
```css
:root {
    --bg-primary: #0d0d0d;
    --bg-gradient: linear-gradient(180deg, #0d0d0d 0%, #1a1008 70%, #2d1a0a 100%);
    --text-primary: #f0ece6;
    --text-secondary: #8a8279;
    --accent: #ff6b35;         /* 熔岩橙 */
    --accent-warm: #d4a574;    /* 暖光 */
    --accent-glow: rgba(255,107,53,0.15);
    --stage-bg: #000;
    --slide-bg: #0d0d0d;
}
```

**Signature Elements:**
- 底部暖光渐变（从深色到暗橙）
- 熔岩橙色的强调色块或文字高亮
- 大面积留黑，中心聚焦
- 极细的垂直分割线（1px，低透明度）
- 缓慢 fade-in 动画（1-1.5s），营造电影节奏

---

## 3. 极光 Aurora

**氛围：** 流动、科技前沿、创意——如极光般的色彩流动

**布局：** 深色底板，mesh gradient 覆盖一角或边缘。内容偏向另一侧形成对比。

**设计灵感：** Stripe、Linear、Vercel 等当代科技品牌的视觉语言。mesh gradient 是 2025+ 最主流的背景趋势。

**Typography:**
- Display: `Clash Display` (600/700) — Fontshare，当代几何无衬线
- Body: `Satoshi` (400/500) — Fontshare，柔和功能型

**Font CDN:**
```html
<link rel="stylesheet" href="https://api.fontshare.com/v2/css?f[]=clash-display@600,700&f[]=satoshi@400,500,700&display=swap">
```

**Colors:**
```css
:root {
    --bg-primary: #0a0f1c;
    --text-primary: #e8eaf0;
    --text-secondary: #6b7280;
    --accent-cyan: #00ffc8;
    --accent-violet: #a855f7;
    --accent-rose: #f43f5e;
    --mesh-1: rgba(168,85,247,0.25);   /* 紫色 mesh */
    --mesh-2: rgba(0,255,200,0.15);    /* 青色 mesh */
    --mesh-3: rgba(244,63,94,0.10);    /* 玫红 mesh */
    --stage-bg: #000;
    --slide-bg: #0a0f1c;
}
```

**Signature Elements:**
- Mesh gradient——多层 radial-gradient 叠加，边缘模糊流动
- 青色 + 紫色 + 玫红三色交汇
- 内容偏移（避开 gradient 区域），形成视觉焦点
- 微妙的 glow 效果（box-shadow: 0 0 40px accent）
- 快速、有节奏的 stagger reveal（0.15s 间隔）

---

## 4. 赤金 Aureate

**氛围：** 奢华、权威、国际——投行路演、CEO 战略汇报的视觉语言

**布局：** 深蓝底板，金色线条与点缀。经典对称或左侧标题+右侧数据。

**设计灵感：** 国际金融品牌视觉。参考：Goldman Sachs、JP Morgan 年报、高端腕表品牌站。

**Typography:**
- Display: `Playfair Display` (700/900) — 经典衬线，权威与优雅
- Body: `Source Sans 3` (400/600) — 清晰功能型，高可读性

**Font CDN:**
```html
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&family=Source+Sans+3:wght@400;600&display=swap" rel="stylesheet">
```

**Colors:**
```css
:root {
    --bg-primary: #0a1628;     /* 深蓝——权威感 */
    --bg-gradient: linear-gradient(135deg, #0a1628 0%, #132244 50%, #0a1628 100%);
    --text-primary: #f5f0e8;
    --text-secondary: #8a9ab5;
    --accent-gold: #c9a96e;    /* 金——不是廉价黄 */
    --accent-gold-light: #e8d4b0;
    --accent-gold-glow: rgba(201,169,110,0.2);
    --border-gold: rgba(201,169,110,0.3);
    --stage-bg: #000;
    --slide-bg: #0a1628;
}
```

**Signature Elements:**
- 金色细线（1-2px）作为分割或边框
- 金色标题或金色数字强调
- 深蓝底板上的低透明度菱形/条纹纹理（如纹章暗纹）
- 经典对称布局，或左标题 + 右内容双栏
- 衬线标题的大写 + tracking 加宽（letter-spacing: 0.08em）

---

## 5. 雾林 Mist Grove

**氛围：** 自然、沉稳、可持续——森林深处有光透入的宁静

**布局：** 深绿底板，一角有柔和的暖光圆（如林间光斑）。内容居中或偏移。

**设计灵感：** Biophilic Design × 当代可持续品牌。参考：Patagonia、Allbirds、北欧生态建筑事务所。

**Typography:**
- Display: `DM Serif Display` (400) — 温暖衬线，不张扬
- Body: `DM Sans` (400/500) — 干净、友好

**Font CDN:**
```html
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display&family=DM+Sans:wght@400;500&display=swap" rel="stylesheet">
```

**Colors:**
```css
:root {
    --bg-primary: #0f1f17;     /* 深林绿 */
    --bg-gradient: linear-gradient(160deg, #0f1f17 0%, #1a3025 60%, #0f1f17 100%);
    --text-primary: #e8e4d9;
    --text-secondary: #8a9a80;
    --accent-light: #f0e6d0;   /* 暖光——林间穿透的阳光 */
    --accent-moss: #7a9a6a;    /* 苔藓绿 */
    --accent-amber: #d4a06a;   /* 琥珀 */
    --glow-warm: radial-gradient(ellipse at 75% 25%, rgba(240,230,208,0.12) 0%, transparent 50%);
    --stage-bg: #000;
    --slide-bg: #0f1f17;
}
```

**Signature Elements:**
- 一角暖光径向渐变（林间光斑）
- 苔藓绿 + 琥珀的低调搭配
- 细竖线或水平线（自然"茎线"隐喻）
- 衬线标题的 italic 变体作为签名元素
- 极慢的 fade-in（0.8-1.2s），呼吸般的节奏

---

## 6. 冰川 Glacier

**氛围：** 极简、纯净、可信——冰川般的冷静与透明

**布局：** 纯白或极浅蓝底板。内容居中或微偏左。极细的蓝色线条点缀。

**设计灵感：** Nordic minimal × 当代 SaaS 品牌。参考：Figma、Notion、Spotify Design。

**Typography:**
- Display: `Outfit` (700/800) — 几何无衬线，冷感但不冷漠
- Body: `Outfit` (400/500) — 同族字体保持一致性

**Font CDN:**
```html
<link href="https://fonts.googleapis.com/css2?family=Outfit:wght@400;500;700;800&display=swap" rel="stylesheet">
```

**Colors:**
```css
:root {
    --bg-primary: #f8fafc;     /* 极浅蓝灰——冰面反光 */
    --bg-secondary: #e2e8f0;
    --text-primary: #0f172a;   /* 深蓝黑——冰下深水 */
    --text-secondary: #64748b;
    --accent: #0ea5e9;         /* 冰蓝 */
    --accent-light: #e0f2fe;
    --accent-deep: #0369a1;
    --line-thin: rgba(14,165,233,0.15);
    --stage-bg: #f8fafc;
    --slide-bg: #f8fafc;
}
```

**Signature Elements:**
- 极细冰蓝线条（0.15 透明度），如冰裂纹
- 大面积留白，中心聚焦
- 数字或关键词用冰蓝高亮
- 无阴影、无渐变、无纹理——纯净表面
- 快速干脆的动画（0.3-0.4s），不拖泥带水

---

## 7. 混凝土 Concrete

**氛围：** 粗犷、坚定、反叛——柏林设计工作室的 Neo-Brutalism

**布局：** 大色块拼接，粗边框，不对称。文字和图形互相穿插。

**设计灵感：** Neo-Brutalism × 当代街头设计。参考：Figma Config 2023 视觉、Gumroad、Berlin design studios。

**Typography:**
- Display: `Space Grotesk` (700) — 几何感，不妥协
- Mono: `Space Mono` (400/700) — 代码感，穿插在标题中

**Font CDN:**
```html
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@700&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
```

**Colors:**
```css
:root {
    --bg-primary: #f0f0f0;     /* 浅灰——混凝土表面 */
    --bg-dark: #1a1a1a;
    --text-primary: #1a1a1a;
    --text-on-dark: #f0f0f0;
    --accent-1: #ff3366;       /* 鲜红粉——高饱和 */
    --accent-2: #00cc88;       /* 绿——对比冲击 */
    --accent-3: #ffcc00;       /* 黄——第三色 */
    --border-bold: #1a1a1a;    /* 3px 粗边框 */
    --shadow-hard: 4px 4px 0px #1a1a1a;  /* 硬阴影 */
    --stage-bg: #f0f0f0;
    --slide-bg: #f0f0f0;
}
```

**Signature Elements:**
- 3-4px 粗黑边框（Neo-Brutalism 标志）
- 硬阴影（4px 4px 0px），无模糊
- 大色块拼接（红/绿/黄饱和色）
- Mono 字体穿插在标题中（如 "THE `CODE` IS LAW"）
- 无圆角（border-radius: 0），或极少圆角（4px）

---

## 8. 纸墨 Ink Paper

**氛围：** 编辑感、沉思、文字至上——当代杂志的数字版本

**布局：** 暖米色底板，居中或左对齐内容。强字体层级。pull quote 作为视觉焦点。

**设计灵感：** 当代编辑设计 × 数字出版。参考：The New York Times 数字版、Monocle、Medium Featured。

**Typography:**
- Display: `Cormorant Garamond` (600/700) — 优雅衬线，不老气
- Body: `IBM Plex Sans` (400/500) — 功能型，高可读

**Font CDN:**
```html
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@600;700&family=IBM+Plex+Sans:wght@400;500&display=swap" rel="stylesheet">
```

**Colors:**
```css
:root {
    --bg-primary: #faf8f3;     /* 暖米——纸张色 */
    --bg-secondary: #f0ece4;
    --text-primary: #1a1a1a;
    --text-secondary: #555555;
    --accent: #c41e3a;         /* 墨红——编辑标注色 */
    --accent-light: #f8e8ec;
    --hr-color: #d4d0c8;       /* 水平分割线 */
    --stage-bg: #faf8f3;
    --slide-bg: #faf8f3;
}
```

**Signature Elements:**
- Drop cap（首字母大写放大，2-3 行高）
- Pull quote（独立引用块，大字号 italic）
- 优雅的水平分割线（细线，暖灰）
- 墨红用于引用、标注、强调
- 长文本的舒适行高（line-height: 1.6-1.8）

---

## 9. 电光 Volt

**氛围：** 快节奏、高能量、创业——创业路演的视觉冲击力

**布局：** 深色底板，高对比度强调色。大标题居左，数据/图表居右。

**设计灵感：** 当代创业路演 × 科技发布会。参考：Apple Keynote 暗色模式、Tesla 发布会、Y Combinator Demo Day。

**Typography:**
- Display: `Clash Display` (600/700) — Fontshare，硬朗几何
- Body: `Satoshi` (400/500/700) — Fontshare，多功能

**Font CDN:**
```html
<link rel="stylesheet" href="https://api.fontshare.com/v2/css?f[]=clash-display@600,700&f[]=satoshi@400,500,700&display=swap">
```

**Colors:**
```css
:root {
    --bg-primary: #0a0a0a;
    --bg-secondary: #141414;
    --text-primary: #ffffff;
    --text-secondary: #888888;
    --accent-electric: #00e5ff;  /* 电光青 */
    --accent-hot: #ff2d55;      /* 热粉红 */
    --accent-electric-glow: rgba(0,229,255,0.2);
    --accent-hot-glow: rgba(255,45,85,0.2);
    --grid-subtle: rgba(255,255,255,0.03);
    --stage-bg: #000;
    --slide-bg: #0a0a0a;
}
```

**Signature Elements:**
- 电光青 + 热粉红双强调色
- 微妙网格背景（0.03 透明度）
- 数据/数字用 accent 超大字号展示
- glow 效果（box-shadow 大范围发光）
- 快速 stagger reveal（0.1s 间隔），节奏紧凑

---

## 10. 砂岩 Sandstone

**氛围：** 温暖、自然、生活方式——地中海阳光下的当代品牌叙事

**布局：** 温暖米色底板，不对称排列。大标题偏一侧，图片/卡片偏另一侧。

**设计灵感：** 当代生活方式品牌 × 地中海美学。参考：Aesop、COS、Kinfolk Magazine、墨西哥/西班牙当代设计。

**Typography:**
- Display: `Fraunces` (700/900) — 独特可变衬线，温暖有个性
- Body: `Work Sans` (400/500) — 干洁功能型

**Font CDN:**
```html
<link href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,700;9..144,900&family=Work+Sans:wght@400;500&display=swap" rel="stylesheet">
```

**Colors:**
```css
:root {
    --bg-primary: #f5efe6;     /* 砂岩米——温暖底色 */
    --bg-secondary: #e8dcc8;
    --text-primary: #2d1f14;   /* 深棕——大地色 */
    --text-secondary: #6b5344;
    --accent-terra: #c4654a;   /* 赭红——赤陶色 */
    --accent-sand: #d4b896;    /* 沙色 */
    --accent-olive: #7a8a5a;   /* 橄榄绿点缀 */
    --accent-terra-light: #f5d8d0;
    --stage-bg: #f5efe6;
    --slide-bg: #f5efe6;
}
```

**Signature Elements:**
- 赭红赤陶色作为强调（标题、标注、按钮）
- 橄榄绿作为第二点缀（小标签、图标）
- 圆角卡片（border-radius: 16px），柔和不锐利
- 抽象几何装饰（圆环 + 短线 + 小点），不用插画
- 缓慢优雅的动画（0.6-0.8s），如阳光移动的节奏

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

---

## 禁用清单（通用 AI 稀烂模式）

**字体：** Inter、Roboto、Arial、系统字体作为展示字体

**颜色：** `#6366f1`（通用靛蓝）、白底紫渐变

**布局：** 万物居中、通用 hero section、千篇一律的卡片网格

**装饰：** 写实插画、无意义的 glassmorphism、没有目的的阴影

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
