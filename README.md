# Portfolio Template

**Single-file, zero-dependency developer portfolio.**

One HTML file. No build tools. No frameworks. No npm install.
Fork it, edit it, deploy to GitHub Pages in 60 seconds.

> Live example: [geraldya.github.io](https://geraldya.github.io)

---

![Screenshot placeholder](https://via.placeholder.com/800x450/0f0f1a/4a9eff?text=Your+Portfolio+Screenshot)

---

## Features

- **Single file** --- everything in one `index.html`, no build step
- **Zero dependencies** --- no frameworks, no CDN links, no package.json
- **Dark / Light theme** --- toggle with localStorage persistence
- **4-language i18n** --- English, Chinese, French, Spanish out of the box (easily extensible)
- **Animated counters** --- numbers count up with eased animation when scrolled into view
- **Scroll reveal** --- sections fade in as you scroll
- **Image lightbox** --- click any project screenshot to view full-size
- **Interactive timeline** --- tell your story with an animated vertical timeline
- **Responsive** --- looks great on mobile, tablet, and desktop
- **Fast** --- no external requests, loads instantly
- **SEO-ready** --- Open Graph and Twitter Card meta tags included
- **Accessible** --- semantic HTML, proper contrast ratios

## Quick Start

### 1. Fork this repo

Click the **Fork** button at the top right, or use the GitHub CLI:

```bash
gh repo fork GeraldYa/portfolio-template --clone
```

### 2. Edit `index.html`

Open the file and replace the placeholder content:

- **Your name** in the `<h1>` tag and `<title>`
- **Your tagline** in the `.tagline` div
- **Your links** --- GitHub, LinkedIn, email, resume
- **Your projects** --- title, tech stack, description, links
- **Your timeline** --- key moments in your career
- **Your experience** --- jobs, dates, descriptions
- **Your skills** --- add/remove skill tags
- **Your stats** --- update the numbers

### 3. Deploy to GitHub Pages

1. Go to **Settings > Pages**
2. Set source to **Deploy from a branch**
3. Select **main** branch, **/ (root)** folder
4. Click **Save**

Your portfolio is live at `https://yourusername.github.io/portfolio-template`

> To use a custom domain or deploy to your root `yourusername.github.io`, rename the repo accordingly.

## Customization

### Change colors

Edit the CSS variables at the top of the `<style>` block:

```css
:root {
  --bg: #0f0f1a;       /* background */
  --card: #1a1a2e;     /* card background */
  --accent: #4a9eff;   /* accent / link color */
  --text: #e0e0e0;     /* main text */
  --muted: #888;       /* secondary text */
  --border: #2a2a40;   /* borders */
}
```

The light theme has its own set of variables under `body.light { ... }`.

### Add project screenshots

Just drop your images into the `screenshots/` folder with the matching filename:

```
screenshots/
├── project-one.jpg
├── project-two.jpg
├── project-three.jpg
└── project-four.jpg
```

That's it. No HTML editing needed. Each card already has an `<img>` tag pointing to the expected filename. If the image exists, it shows up with lightbox support. If not, a fallback icon displays automatically --- no broken images, no manual toggling.

To change the filename convention, edit the `src` attribute in the `<img>` tag inside each card.

### Add / remove languages

Find the `i18n` object in the `<script>` section and add a new language key:

```javascript
const i18n = {
  en: { /* ... */ },
  zh: { /* ... */ },
  // Add your language:
  ja: {
    tagline: "あなたの役割 / 専門 / 焦点",
    // ... translate all keys
  }
};
```

Then add a menu item in the HTML:

```html
<a onclick="setLang('ja')">日本語</a>
```

### Change the logo

The logo is an inline SVG in both `index.html` (top-left corner) and `favicon.svg`. Search for the `<text>` element and change the initials:

```xml
<text x="50" y="68" ... >YN</text>  <!-- Change to your initials -->
```

### Add more projects

Duplicate a `<div class="card">` block inside the `.projects` grid. The two-column layout adjusts automatically.

### Add more timeline entries

Duplicate a `<div class="tl-item">` block inside the `.timeline` container.

## Project Structure

```
portfolio-template/
├── index.html          # Everything lives here
├── favicon.svg         # Browser tab icon (editable SVG)
├── screenshots/        # Project screenshots (optional)
│   └── .gitkeep
├── LICENSE             # MIT
└── README.md
```

## Tech Stack

Just HTML, CSS, and vanilla JavaScript. That's it.

| Feature | Implementation |
|---------|---------------|
| Styling | CSS custom properties + media queries |
| Theme toggle | `classList.toggle('light')` + `localStorage` |
| i18n | `data-i18n` attributes + JS object lookup |
| Animations | CSS `@keyframes` + `IntersectionObserver` |
| Lightbox | 15 lines of vanilla JS |
| Counter | `setInterval` with cubic easing |

---

# 中文说明

**单文件、零依赖的开发者作品集模板。**

一个 HTML 文件，不需要构建工具、框架或 npm。
Fork、编辑、60 秒部署到 GitHub Pages。

> 在线示例: [geraldya.github.io](https://geraldya.github.io)

## 功能特性

- **单文件** --- 所有内容在一个 `index.html` 中，无需构建
- **零依赖** --- 没有框架、没有 CDN、没有 package.json
- **深色/浅色主题** --- 一键切换，自动记忆偏好
- **四语言 i18n** --- 内置英/中/法/西，轻松扩展
- **数字动画** --- 滚动到视图时数字缓动递增
- **滚动渐现** --- 各区域滚动进入时渐显
- **图片灯箱** --- 点击项目截图查看大图
- **交互时间线** --- 用动画时间线讲述你的故事
- **响应式** --- 手机、平板、桌面都好看
- **极速** --- 无外部请求，瞬间加载
- **SEO 就绪** --- 包含 Open Graph 和 Twitter Card 标签

## 快速开始

### 1. Fork 本仓库

点击右上角 **Fork** 按钮，或使用命令行：

```bash
gh repo fork GeraldYa/portfolio-template --clone
```

### 2. 编辑 `index.html`

打开文件，替换占位内容：

- `<h1>` 和 `<title>` 中的**你的名字**
- `.tagline` 中的**你的头衔**
- **链接** --- GitHub、LinkedIn、邮箱、简历
- **项目** --- 标题、技术栈、描述、链接
- **时间线** --- 你的职业关键时刻
- **工作经历** --- 公司、时间、描述
- **技能标签** --- 增删自如
- **统计数字** --- 更新为你的数据

### 3. 部署到 GitHub Pages

1. 进入 **Settings > Pages**
2. Source 选 **Deploy from a branch**
3. 选 **main** 分支，**/ (root)** 目录
4. 点 **Save**

你的作品集将在 `https://yourusername.github.io/portfolio-template` 上线。

## 自定义

### 修改配色

编辑 `<style>` 顶部的 CSS 变量：

```css
:root {
  --bg: #0f0f1a;       /* 背景色 */
  --card: #1a1a2e;     /* 卡片背景 */
  --accent: #4a9eff;   /* 强调色 / 链接色 */
  --text: #e0e0e0;     /* 主文字 */
  --muted: #888;       /* 次要文字 */
  --border: #2a2a40;   /* 边框 */
}
```

### 添加项目截图

只需将图片放入 `screenshots/` 目录，文件名对应即可：

```
screenshots/
├── project-one.jpg
├── project-two.jpg
├── project-three.jpg
└── project-four.jpg
```

不需要改 HTML。每个卡片已经有指向对应文件名的 `<img>` 标签。图片存在就自动显示（带灯箱放大），不存在就自动显示图标——不会出现破图。

### 添加语言

在 `<script>` 中的 `i18n` 对象里添加新语言键，然后在菜单中加入对应选项即可。

## 项目结构

```
portfolio-template/
├── index.html          # 一切都在这里
├── favicon.svg         # 浏览器标签图标（可编辑 SVG）
├── screenshots/        # 项目截图（可选）
│   └── .gitkeep
├── LICENSE             # MIT 开源协议
└── README.md
```

---

## Credits

Created by [Gerald Yang](https://github.com/GeraldYa)

## License

[MIT](LICENSE) --- free for personal and commercial use.
