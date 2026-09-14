# 梦屿 Dream Bank · AI 画布导入包

本包用于将「梦屿 Dream Bank」梦境记录与分析 App 的高保真原型导入 Trae Design / AI Canvas，生成可编辑的界面页面，再下载到 Figma 中微调。

## 包内文件说明

```
ai-canvas-package/
├── README.md                 # 本说明书
├── page-descriptions.md      # 每个页面的结构、内容与交互说明
├── design-tokens.md          # 色彩、字体、间距、圆角、阴影等设计系统
├── screenshot-notes.md       # 截图生成环境说明
├── import-prompt.txt         # 可直接复制给 AI 画布的 Prompt
└── screenshots/              # 截图资源
    ├── 01-home.png           # 首页 · 首屏截图
    ├── 02-record.png         # 记录页 · 首屏截图
    ├── 03-analyze.png        # 分析页 · 首屏截图
    ├── 04-community.png      # 社区页 · 首屏截图
    ├── 05-profile.png        # 我的页 · 首屏截图
    ├── 06-train.png          # 训练页 · 首屏截图
    └── long/                 # 长截图（完整滚动内容）
        ├── 01-home-long.png
        ├── 02-record-long.png
        ├── 03-analyze-long.png
        ├── 04-community-long.png
        ├── 05-profile-long.png
        └── 06-train-long.png
```

## 这套素材能做什么

1. **直接喂给 AI 画布**：把 `screenshots/` 里的图片 + `import-prompt.txt` 的提示词一起上传，AI 能识别出手机 App 的完整布局、组件层级与视觉风格。
2. **生成可编辑页面**：AI 画布会基于截图生成矢量或位图页面，你可以像截图里展示的那样，把多个页面平铺在画布上。
3. **Figma 微调**：下载画布后，在 Figma 中替换图标、调整文案、修改间距、补全状态页。

## 你需要给 AI 画布提供什么

根据 Trae Design / AI Canvas 的常规输入要求，建议一起上传：

| 素材 | 是否必须 | 本包是否提供 | 说明 |
|------|---------|------------|------|
| 每个核心界面的首屏高保真截图 | 必须 | ✅ screenshots/ | 6 张 PNG，375×812 比例 |
| 每个核心界面的完整长截图 | 强烈建议 | ✅ screenshots/long/ | 6 张 PNG，完整滚动内容 |
| 页面名称与功能说明 | 强烈建议 | ✅ page-descriptions.md | 帮助 AI 理解每个页面 |
| 设计系统（颜色/字体/间距） | 强烈建议 | ✅ design-tokens.md | 保证多页面风格一致 |
| 组件规范（按钮/卡片/标签） | 建议 | ✅ design-tokens.md | 减少 AI 自由发挥 |
| 交互/动效说明 | 可选 | ✅ page-descriptions.md | 截图是静态的，文字补充动态行为 |
| 启动页 / 空态 / 错误态 | 可选 | ❌ | 可自行补充或让 AI 根据风格推导 |

## 使用步骤

### 步骤 1：准备 Prompt
打开 `import-prompt.txt`，复制全部内容。把它作为你给 AI 画布的第一条指令。

### 步骤 2：上传截图
把 `screenshots/` 里的 6 张首屏截图 + `screenshots/long/` 里的 6 张长截图一次性上传到 AI 画布。

### 步骤 3：补充设计系统
把 `design-tokens.md` 的核心内容（尤其是色板和字体）复制到对话中，或在 AI 生成第一版后，用来校正颜色。

### 步骤 4：按页面校验
对照 `page-descriptions.md` 检查 AI 生成的每个页面：
- 首页是否有「梦境天气卡 + 情绪泡泡 + 最近梦境明信片」？
- 记录页是否有「捕梦网按钮 + 情绪标签 + 清晰度滑块」？
- 分析页是否有「情绪环图 + 周/月/年切换 + 词云/日历」？
- 社区页是否有「梦境盲盒 + 接龙 + 围观」？
- 我的页是否有「头像 + 统计 + 图鉴网格 + 设置入口」？
- 训练页是否有「意图卡 + 清醒率 + 挑战 + 徽章」？

### 步骤 5：下载到 Figma
AI 画布生成完成后，导出/下载为 Figma 可编辑格式，按需调整文案、间距和细节。

## 截图说明

1. **首屏截图**：`screenshots/` 根目录下的 6 张图，适合作为 AI 画布快速预览和布局参考。
2. **长截图**：`screenshots/long/` 目录下的 6 张图，完整展示了每个页面的全部滚动内容，包括完整列表、设置项等。建议一并上传给 AI 画布，让它看到更完整的信息架构。
3. **动态效果无法截图**：
   - 长按捕梦网的涟漪、拆盲盒动画、卡片翻转等是动态交互，截图中无法体现。
   - 已在 `page-descriptions.md` 中用文字描述。

## 如果你需要更高质量的截图

当前截图已经使用了本地嵌入的 Noto Color Emoji 字体，emoji 能正常显示。如果你希望在自己电脑上重新截图（例如更换设备尺寸、调整文案），可以：
1. 用 Chrome DevTools 打开 `case-3/capture.html`。
2. 按 `Cmd/Ctrl + Shift + M` 切换到设备模拟（iPhone 14 Pro / 375×812）。
3. 依次点击底部 Tab，截取每个页面。
4. 把截图覆盖 `ai-canvas-package/screenshots/` 中的文件。

## 技术信息

- 原型技术栈：HTML + Tailwind CSS + 原生 JavaScript（单文件）
- 入口文件：`case-3/prototype.html`
- 截图容器：`case-3/capture.html`（自动按 375:812 比例渲染 iframe）
- 设计系统：深空蓝 `#0B1026` + 极光紫 `#8B5CF6` + 星云粉 `#EC4899` + 梦境青 `#06B6D4`
