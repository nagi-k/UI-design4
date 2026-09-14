# 截图说明

## 生成环境

- 截图工具：无头浏览器自动截图
- 截图容器：`case-3/capture.html`（首屏截图） / `case-3/prototype.html`（长截图）
- 渲染比例：按 iPhone 375×812 逻辑分辨率
- 字体：本地嵌入 Noto Color Emoji（`case-3/fonts/NotoColorEmoji-Regular.ttf`）
- 原文件：`case-3/prototype.html`（单文件 HTML + Tailwind CSS + 原生 JS）

## 截图清单

### 首屏截图（screenshots/）

| 文件名 | 页面 | 内容 |
|--------|------|------|
| 01-home.png | 首页 · 梦境银行 | 天气卡、情绪泡泡、统计、明信片入口 |
| 02-record.png | 记录 · 捕梦网 | 捕梦网按钮、情绪标签、清晰度评分 |
| 03-analyze.png | 分析 · 潜意识的形状 | 周期切换、情绪环图 |
| 04-community.png | 社区 · 梦屿广场 | 匿名梦境卡片流 |
| 05-profile.png | 我的 · 个人中心 | 头像、统计、图鉴网格 |
| 06-train.png | 训练 · 清醒梦实验室 | 意图卡、挑战、徽章 |

### 长截图（screenshots/long/）

| 文件名 | 页面 | 说明 |
|--------|------|------|
| 01-home-long.png | 首页 | 完整首页，包含所有最近梦境卡片 |
| 02-record-long.png | 记录页 | 完整记录表单 |
| 03-analyze-long.png | 分析页 | 环图、折线图、重复符号、着色日历等 |
| 04-community-long.png | 社区页 | 完整社区卡片流 |
| 05-profile-long.png | 我的页 | 完整个人中心、图鉴、徽章、设置 |
| 06-train-long.png | 训练页 | 完整训练内容 |

## 字体处理

为了让截图中的 emoji 正常显示，已在 `prototype.html` 中通过 `@font-face` 嵌入本地 Noto Color Emoji 字体：

```css
@font-face {
  font-family: 'NotoColorEmoji';
  src: url('./fonts/NotoColorEmoji-Regular.ttf') format('truetype');
  font-display: swap;
}
```

字体文件位于 `case-3/fonts/NotoColorEmoji-Regular.ttf`（约 10MB），随包一起提供。

## 动态交互说明

截图是静态的，以下动态效果无法体现：
- 启动页流星动画
- 长按捕梦网时的涟漪与旋转
- 拆梦境盲盒的 shake + 打开动画
- 情绪泡泡的漂浮与戳破粒子效果
- 梦境卡片的 3D 翻转
- 天气卡片的切换翻转

这些交互已在 `page-descriptions.md` 中用文字描述，可在 Figma 中用组件状态或原型交互补充。

## 重新截图指南

如果你希望在自己电脑上重新截图：

1. 确保 `case-3/fonts/NotoColorEmoji-Regular.ttf` 存在。
2. 把 `case-3/` 放到任意本地静态服务器。
3. 用 Chrome 打开 `http://localhost:xxxx/capture.html`。
4. 按 `F12` 打开 DevTools → 按 `Cmd/Ctrl + Shift + M` 切换到设备模拟。
5. 选择设备：iPhone 14 Pro（393×852）或 iPhone 12 Pro（390×844）。
6. 依次点击底部 Tab 截取每个页面。
