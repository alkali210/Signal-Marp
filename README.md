# Signal Atelier Marp

## [示例](examples/signal-atelier-example.pdf)

## 使用

### VS Code
安装 [Marp for VS Code](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode)扩展，
在 `Signal-Marp/` 下启动VS Code，打开 `examples/signal-atelier-example.md` 查看预览和导出。

### marp(npm)

安装 `marp` ：

```bash
npm install
npm run html
npm run pdf
```
在 `Signal-Marp/` 中打开示例：

```bash
marp examples/signal-atelier-example.md --theme themes/signal-atelier.css --html --output dist/signal-atelier-example.html
```

在某些 Windows 环境中，如果 PDF 导出报 `spawn UNKNOWN`，说明 Marp 没能自动启动浏览器。可以指定 Edge：

```bash
npm run pdf:edge
```

## 设计方向

- 编辑部式网格：稳定边框、细网格背景、清晰标题层级。
- 数据型表达：指标卡、时间线、对照面板和紧凑表格优先服务真实内容。
- 多色但克制：graphite、teal、coral、amber、blue、mint 共同构成识别系统。
- 离线可用：不依赖远程字体、图标 CDN 或外部图片。
- 字体分层：标题使用本地衬线字体栈，正文使用 `MiSans` / `Noto Sans SC`，代码和标签使用等宽字体，引用使用偏书写感的中文字体栈。

## 常用页面类

| 类名 | 用途 |
| --- | --- |
| `cover` | 封面页 |
| `cover cover-side` | 侧图封面页 |
| `cover cover-band` | 色带封面页 |
| `toc` | 目录页 |
| `toc toc-rail` | 纵向 rail 目录 |
| `toc toc-dense` | 高密度目录 |
| `divider` | 章节过渡页 |
| `divider divider-center` | 居中章节页 |
| `divider divider-band` | 横带章节页 |
| `inverse` | 深色重点页 |
| `dashboard` | 数据仪表盘页 |
| `compact` | 信息密度更高的页面 |
| `end` | 结束页 |
| `full-bleed` | 全出血页面 |

## 常用组件

| 类名 | 用途 |
| --- | --- |
| `columns` / `ratio-60` / `ratio-40` | 两栏布局 |
| `grid-3` / `tiles` | 三栏内容组 |
| `metric-grid` / `metric` | 数据指标卡 |
| `panel` / `panel dark` | 内容面板 |
| `quote-panel` / `quote-mark` | 大引用版式 |
| `comparison` | 左右对照页 |
| `statement` | 单句结论页 |
| `note-list` | 编号说明块 |
| `timeline` | 四段式时间线 |
| `swatches` | 色板展示 |
| `kicker` / `lead` / `micro` | 文本层级辅助 |

## 字体策略

主题不加载远程字体，优先使用当前环境中已有字体：

- `--sa-display`：`Apple Garamond` / `Latin Modern Roman` / `Source Han Serif CN`，用于封面大标题。
- `--sa-heading`：`Source Han Serif CN` / `Noto Serif SC`，用于章节标题和页面标题。
- `--sa-body`：`MiSans` / `Noto Sans SC` / `Microsoft YaHei UI`，用于正文。
- `--sa-ui`：`Bahnschrift` / `Ubuntu Sans` / `MiSans`，用于数字、短标签和强调信息。
- `--sa-literary`：`UD Digi Kyokasho N-R` / `FZSTK` / `LXGW WenKai`，用于引用和单句 statement。
- `--sa-mono`：`AtkinsonMono Nerd Font` / `UbuntuSansMono Nerd Font` / `Cascadia Code`，用于代码和页眉页脚。

## Frontmatter 示例

```yaml
---
marp: true
theme: signal-atelier
size: 16:9
paginate: true
header: "Signal Atelier"
footer: "Marp template"
---
```

## Todo
- [ ] 解决在`pdf.js`上的渲染一致性问题
