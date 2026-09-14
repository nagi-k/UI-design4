# 截图说明

## 生成环境

- 截图工具：无头浏览器自动截图
- 截图容器：`case-3/capture.html`
- 渲染比例：按 iPhone 375×812 逻辑分辨率，iframe 高度自适应 95vh
- 原文件：`case-3/prototype.html`（单文件 HTML + Tailwind CSS + 原生 JS）

## 截图清单

| 文件名 | 页面 | 状态 |
|--------|------|------|
| 01-home.png | 首页 · 梦境银行 | 首屏，包含天气卡、情绪泡泡、统计、明信片入口 |
| 02-record.png | 记录 · 捕梦网 | 默认态，中央捕梦网按钮 + 情绪标签 + 清晰度评分 |
| 03-analyze.png | 分析 · 潜意识的形状 | 周视图，情绪环图 |
| 04-community.png | 社区 · 梦屿广场 | 首屏，匿名梦境卡片流 |
| 05-profile.png | 我的 · 个人中心 | 首屏，头像、统计、图鉴网格 |
| 06-train.png | 训练 · 清醒梦实验室 | 首屏，意图卡 + 挑战 + 徽章 |

## 已知问题

### 1. emoji 显示为方框
**表现**：截图中所有 emoji（🏠、🎙️、📊、🌐、👤、🕸️、🌙、✨ 等）显示为 □ 方框。

**原因**：截图环境的 Linux 系统没有安装彩色 emoji 字体，Google Fonts 的 Noto Color Emoji 未能加载生效。

**影响**：不影响 AI 画布识别布局。AI 能从文字标签（首页、记录、分析、社区、我的）和上下文推断每个方框应该是什么图标。

**修复建议**：
- 在 Figma 中，把方框替换为对应 emoji 或图标。
- 如需更高质量截图，请在自己的电脑（Mac/Windows）上打开 `case-3/capture.html` 或 `case-3/prototype.html` 手动截图。

### 2. 部分列表/设置项未完整展示
**表现**：首页的「最近捕获的梦」只展示了前几项；我的页只展示了图鉴首屏。

**原因**：每个页面内容可滚动，截图只截取首屏。

**修复建议**：
- 在 Figma 中手动补全列表项。
- 或参考 `page-descriptions.md` 中「完整内容」段落，让 AI 画布补充。

### 3. 动态交互未体现
**表现**：截图无法展示长按、翻页、粒子、涟漪等动效。

**原因**：截图是静态的。

**修复建议**：
- 参考 `page-descriptions.md` 中的交互说明。
- 在 Figma 中通过组件状态或原型交互补充。

## 重新截图指南

如果你希望获得 emoji 正常显示的截图，建议按以下步骤操作：

1. 把 `case-3/` 文件夹放到任意本地静态服务器（如 VS Code Live Server、npx serve、python http.server）。
2. 用 Chrome 打开 `http://localhost:xxxx/capture.html`。
3. 按 `F12` 打开 DevTools → 按 `Cmd/Ctrl + Shift + M` 切换到设备模拟。
4. 选择设备：iPhone 14 Pro（393×852）或 iPhone 12 Pro（390×844）。
5. 等待启动页动画结束，首页内容加载完成。
6. 依次点击底部 Tab：首页 → 记录 → 分析 → 社区 → 我的。
7. 从「我的」页进入「清醒梦实验室」，截取训练页。
8. 保存截图，命名为 `01-home.png` 到 `06-train.png`，覆盖 `ai-canvas-package/screenshots/` 中的文件。
