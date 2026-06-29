# HTML Slides — 自包含演示文稿生成器

> 从零开始或通过转换 PowerPoint 文件，生成精美、动画丰富、自包含的 HTML 演示文稿。

零依赖。单一 HTML 文件，CSS/JS 全部内联。浏览器打开即可演示。

## 特性

- **零依赖** — 单一 HTML 文件，CSS/JS 全部内联。无需 npm 或构建工具。
- **固定 16:9 舞台** — 1920×1080 幻灯片画布，整体缩放适配任意视口。移动端不重排。
- **样式发现** — 生成 3 个视觉预览，所见即所选，而非凭空描述。
- **动画丰富** — 交错渐显、缩放过渡、模糊效果、背景纹理等。
- **行内编辑** — 鼠标悬停左上角或按 E 键，直接在浏览器中编辑文本。
- **PPT 转换** — 将 PowerPoint 文件转换为 HTML，支持样式选择。
- **独特设计** — 12 套精选风格预设，拒绝千篇一律的"AI 稀烂美学"。

## 快速开始

本项目以 **WorkBuddy Skill** 形式组织，技能定义位于 `.workbuddy/skills/html-slides/`。

在 WorkBuddy 中使用时，进入本项目目录即可自动激活技能。

## 技能结构

```
.workbuddy/skills/html-slides/
├── SKILL.md                      # 主工作流程（渐进式披露）
├── references/
│   ├── viewport-base.css         # 强制性固定舞台 CSS
│   ├── html-template.md          # HTML 架构与 JS 功能
│   ├── animation-patterns.md     # 动画参考与效果-感觉对照
│   └── style-presets.md          # 12 套精选视觉风格定义
├── scripts/
│   └── extract-pptx.py           # PPT 内容提取脚本
└── assets/                       # （模板与素材，后续添加）
```

## 风格预设

| # | 名称 | 氛围 | 主题 |
|---|------|------|------|
| 1 | Bold Signal | 自信、高冲击力 | 深色 |
| 2 | Electric Studio | 干净、专业 | 深色 |
| 3 | Creative Voltage | 充满活力、复古现代 | 深色 |
| 4 | Dark Botanical | 优雅、精致 | 深色 |
| 5 | Notebook Tabs | 编辑感、触感 | 浅色 |
| 6 | Pastel Geometry | 友好、亲和 | 浅色 |
| 7 | Split Pastel | 俏皮、创意 | 浅色 |
| 8 | Vintage Editorial | 诙谐、个性鲜明 | 浅色 |
| 9 | Neon Cyber | 未来感、科技感 | 特色 |
| 10 | Terminal Green | 开发者、黑客美学 | 特色 |
| 11 | Swiss Modern | 精致、包豪斯 | 特色 |
| 12 | Paper & Ink | 文艺、沉思 | 特色 |

## 技术约束

- 幻灯片画布：固定 1920×1080，通过 JS transform 缩放
- 可见性控制：`.active`/`.visible` 类（绝不使用 `display: none/block`）
- CSS 函数取负：`calc(-1 * clamp(...))`（不可直接写 `-clamp()`）
- 字体：仅使用 Google Fonts 或 Fontshare（不使用系统字体）
- 必须支持 `prefers-reduced-motion`
- 幻灯片内部不允许滚动、溢出或面板重叠

## 工作流程

1. **阶段 0** — 模式检测（新建 / PPT 转换 / 增强）
2. **阶段 1** — 内容发现（用途、篇幅、密度、素材）
3. **阶段 2** — 样式发现（3 个视觉预览，选择其一）
4. **阶段 3** — 生成演示文稿（单一 HTML 文件）
5. **阶段 4** — PPT 转换（可选）
6. **阶段 5** — 交付与预览
7. **阶段 6** — 分享与导出（CloudStudio 部署 / PDF 导出）

## 当前状态

**框架已建立。** 风格预设与详细设计规则将在后续沟通中细化。

## 许可证

MIT
