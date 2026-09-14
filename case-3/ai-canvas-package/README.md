# 梦屿 Dream Bank · AI 画布导入包

本包用于将「梦屿 Dream Bank」梦境记录与分析 App 的高保真原型导入 Trae Design / AI Canvas，生成可编辑的界面页面，再下载到 Figma 中微调。

## 包内文件说明

```
ai-canvas-package/
├── README.md                 # 本说明书
├── page-descriptions.md      # 每个页面的结构、内容与交互说明
├── design-tokens.md          # 色彩、字体、间距、圆角、阴影等设计系统
├── screenshot-notes.md       # 截图生成环境与已知问题说明
├── import-prompt.txt         # 可直接复制给 AI 画布的 Prompt
└── screenshots/              # 6 张核心页面高保真截图
    ├── 01-home.png           # 首页 · 梦境银行
    ├── 02-record.png         # 记录 · 捕梦网
    ├── 03-analyze.png        # 分析 · 潜意识的形状
    ├── 04-community.png      # 社区 · 梦屿广场
    ├── 05-profile.png        # 我的 · 个人中心 / 图鉴
    └── 06-train.png          # 训练 · 清醒梦实验室
```

## 这套素材能做什么

1. **直接喂给 AI 画布**：把 `screenshots/` 里的图片 + `import-prompt.txt` 的提示词一起上传，AI 能识别出手机 App 的完整布局、组件层级与视觉风格。
2. **生成可编辑页面**：AI 画布会基于截图生成矢量或位图页面，你可以像截图里展示的那样，把多个页面平铺在画布上。
3. **Figma 微调**：下载画布后，在 Figma 中替换图标、调整文案、修改间距、补全状态页。

## 你需要给 AI 画布提供什么

根据 Trae Design / AI Canvas 的常规输入要求，建议一起上传：

| 素材 | 是否必须 | 本包是否提供 | 说明 |
|------|---------|------------|------|
| 每个核心界面的高保真截图 | 必须 | ✅ screenshots/ | 6 张 PNG，375×812 比例 |
| 页面名称与功能说明 | 强烈建议 | ✅ page-descriptions.md | 帮助 AI 理解每个页面 |
| 设计系统（颜色/字体/间距） | 强烈建议 | ✅ design-tokens.md | 保证多页面风格一致 |
| 组件规范（按钮/卡片/标签） | 建议 | ✅ design-tokens.md | 减少 AI 自由发挥 |
| 交互/动效说明 | 可选 | ✅ page-descriptions.md | 截图是静态的，文字补充动态行为 |
| 启动页 / 空态 / 错误态 | 可选 | ❌ | 可自行补充或让 AI 根据风格推导 |

## 使用步骤

### 步骤 1：准备 Prompt
打开 `import-prompt.txt`，复制全部内容。把它作为你给 AI 画布的第一条指令。

### 步骤 2：上传截图
把 `screenshots/` 里的 6 张图片一次性上传到 AI 画布。

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
AI 画布生成完成后，导出/下载为 Figma 可编辑格式，替换 emoji 图标、调整细节。

## 已知问题与处理建议

1. **截图中的 emoji 显示为方框**：
   - 原因：截图环境的系统字体缺少彩色 emoji。
   - 不影响 AI 识别布局，AI 能从上下文知道这里是「🏠 首页」「🎙️ 记录」等图标。
   - 在 Figma 中替换为对应 emoji 或图标即可。

2. **部分页面内容需要滚动才能看全**：
   - 截图只截取了首屏。AI 画布生成后，你可能需要手动补全列表项、展开设置项等。
   - 参考 `page-descriptions.md` 中的「完整内容」段落。

3. **动态效果无法截图**：
   - 长按捕梦网的涟漪、拆盲盒动画、卡片翻转等是动态交互，截图中无法体现。
   - 已在 `page-descriptions.md` 中用文字描述。

## 如果你需要更高质量的截图

当前截图是在无头浏览器中自动截取的。如果你在自己的电脑（Mac/Windows）上打开 `case-3/capture.html` 或 `case-3/prototype.html`，系统自带 emoji 字体，截图效果会更好。

推荐手动截图流程：
1. 用 Chrome DevTools 打开 `capture.html`。
2. 按 `Cmd/Ctrl + Shift + M` 切换到设备模拟（iPhone 14 Pro / 375×812）。
3. 依次点击底部 Tab，截取每个页面。
4. 把截图覆盖 `ai-canvas-package/screenshots/` 中的文件。

## 技术信息

- 原型技术栈：HTML + Tailwind CSS + 原生 JavaScript（单文件）
- 入口文件：`case-3/prototype.html`
- 截图容器：`case-3/capture.html`（自动按 375:812 比例渲染 iframe）
- 设计系统：深空蓝 `#0B1026` + 极光紫 `#8B5CF6` + 星云粉 `#EC4899` + 梦境青 `#06B6D4`
