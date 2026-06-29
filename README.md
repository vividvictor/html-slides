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
- **独特设计** — 10 套当代国际化风格预设，拒绝千篇一律的"AI 稀烂美学"。

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
│   └── style-presets.md          # 10 套当代国际化视觉风格定义
├── scripts/
│   └── extract-pptx.py           # PPT 内容提取脚本
└── assets/                       # （模板与素材，后续添加）
```

## 风格预设

| # | 名称 | 氛围 | 主题 |
|---|------|------|------|
| 1 | 建筑 Architect | 精准、克制、国际理性 | 浅色 |
| 2 | 熔岩 Lava | 电影感、沉稳叙事 | 深色 |
| 3 | 极光 Aurora | 流动、科技前沿 | 深色 |
| 4 | 赤金 Aureate | 奢华、权威、金融 | 深色 |
| 5 | 雾林 Mist Grove | 自然、可持续 | 深色 |
| 6 | 冰川 Glacier | 极简、纯净、可信 | 浅色 |
| 7 | 混凝土 Concrete | 粗犷、Neo-Brutalism | 浅色 |
| 8 | 纸墨 Ink Paper | 编辑感、沉思 | 浅色 |
| 9 | 电光 Volt | 快节奏、创业路演 | 深色 |
| 10 | 砂岩 Sandstone | 温暖、生活方式 | 浅色 |

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

**框架已建立，10 套当代国际化风格预设已定义。** 设计细节可按需求进一步调整。

## 许可证

MIT
