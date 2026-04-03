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
- **3-column project grid** --- responsive layout (3 cols on desktop, 2 on tablet, 1 on mobile)
- **"Show more" toggle** --- display 6 featured projects up front, reveal extra projects with a button
- **Blog / Writing section** --- link to dedicated blog post pages with a 2-column card layout
- **Blog post template** --- `blog-template.html` with matching design, dark/light toggle, and article-ready typography
- **Dark / Light theme** --- toggle with localStorage persistence
- **4-language i18n** --- English, Chinese, French, Spanish out of the box (easily extensible)
- **Outfit + JetBrains Mono fonts** --- modern typography via Google Fonts
- **Animated counters** --- numbers count up with eased animation when scrolled into view
- **Staggered card reveals** --- project cards animate in one by one with scale + fade
- **Scroll reveal** --- sections fade in as you scroll
- **Timeline pulse** --- the last timeline dot pulses to draw attention to "Now"
- **Image lightbox** --- click any project screenshot to view full-size
- **Interactive timeline** --- tell your story with an animated vertical timeline (5 entries)
- **Responsive** --- looks great on mobile, tablet, and desktop
- **Fast** --- minimal external requests (only Google Fonts), loads instantly
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
  --bg: #0a0a14;       /* background */
  --card: #13132a;     /* card background */
  --accent: #8b7cf6;   /* accent / link color */
  --accent2: #f59e0b;  /* secondary accent */
  --text: #e8e8f0;     /* main text */
  --muted: #8888a8;    /* secondary text */
  --border: #22223a;   /* borders */
}
```

The light theme has its own set of variables under `body.light { ... }`.

### Add project screenshots

Each project card expects a specific image filename. Drop your screenshots into `screenshots/` using these exact names:

| Card | Expected filename |
|------|-------------------|
| Project One | `screenshots/project-one.jpg` |
| Project Two | `screenshots/project-two.jpg` |
| Project Three | `screenshots/project-three.jpg` |
| Project Four | `screenshots/project-four.jpg` |
| Project Five | `screenshots/project-five.jpg` |
| Project Six | `screenshots/project-six.jpg` |
| Project Seven | `screenshots/project-seven.jpg` |
| Project Eight | `screenshots/project-eight.jpg` |
| Project Nine | `screenshots/project-nine.jpg` |
| Project Ten | `screenshots/project-ten.jpg` |

No screenshot? No problem --- a fallback icon shows automatically, no broken images.

**Important:** The filenames are defined in the HTML `<img src="...">` tags, not by your project title. If you renamed "Project One" to "Thought Evolution", the expected filename is still `project-one.jpg` unless you also update the `src` attribute in the HTML:

```html
<!-- Find this line in your card -->
<img src="screenshots/project-one.jpg" ...>

<!-- Change it to match your file -->
<img src="screenshots/thought-evolution.jpg" ...>
```

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

### Add blog posts

1. Duplicate `blog-template.html` and rename it (e.g., `blog-my-project.html`)
2. Replace the placeholder content with your article
3. Update the Writing section in `index.html` to link to your new file
4. Add i18n keys (`w1t`, `w1d`, etc.) for each language

### Add more projects

The main grid shows 6 projects. Additional projects go inside the `<div class="more-projects">` section and are revealed by the "Show more" button.

To add a project to the main grid, duplicate a `<div class="card">` block inside the first `.projects` div. The three-column layout adjusts automatically.

To add a project to the hidden section, duplicate a card inside the `.more-projects` div and update the button text count.

### Add more timeline entries

Duplicate a `<div class="tl-item">` block inside the `.timeline` container.

## Project Structure

```
portfolio-template/
├── index.html          # Main portfolio page
├── blog-template.html  # Blog post template (duplicate for each post)
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
| Typography | Outfit + JetBrains Mono via Google Fonts |
| Theme toggle | `classList.toggle('light')` + `localStorage` |
| i18n | `data-i18n` attributes + JS object lookup |
| Animations | CSS `@keyframes` + `IntersectionObserver` |
| Card reveals | Staggered `animation-delay` with scale + fade |
| Show more | `toggleProjects()` with display toggle |
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
- **三列项目网格** --- 响应式布局（桌面三列、平板两列、手机一列）
- **"显示更多"切换** --- 首屏展示 6 个项目，按钮展开更多
- **博客/写作板块** --- 链接到独立博客文章页，双列卡片布局
- **博客文章模板** --- `blog-template.html`，配套设计，支持深浅主题
- **深色/浅色主题** --- 一键切换，自动记忆偏好
- **四语言 i18n** --- 内置英/中/法/西，轻松扩展
- **Outfit + JetBrains Mono 字体** --- 通过 Google Fonts 加载现代排版
- **数字动画** --- 滚动到视图时数字缓动递增
- **卡片交错渐现** --- 项目卡片逐个缩放淡入
- **滚动渐现** --- 各区域滚动进入时渐显
- **时间线脉冲** --- 最后一个时间点脉动闪烁，突出"现在"
- **图片灯箱** --- 点击项目截图查看大图
- **交互时间线** --- 用动画时间线讲述你的故事（5 个节点）
- **响应式** --- 手机、平板、桌面都好看
- **极速** --- 仅加载 Google Fonts，瞬间加载
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

每个项目卡片对应一个固定的图片文件名，把截图按以下名称放入 `screenshots/` 即可：

| 卡片 | 对应文件名 |
|------|-----------|
| Project One | `screenshots/project-one.jpg` |
| Project Two | `screenshots/project-two.jpg` |
| Project Three | `screenshots/project-three.jpg` |
| Project Four | `screenshots/project-four.jpg` |
| Project Five | `screenshots/project-five.jpg` |
| Project Six | `screenshots/project-six.jpg` |
| Project Seven | `screenshots/project-seven.jpg` |
| Project Eight | `screenshots/project-eight.jpg` |
| Project Nine | `screenshots/project-nine.jpg` |
| Project Ten | `screenshots/project-ten.jpg` |

没有截图？没关系——自动显示图标，不会出现破图。

**注意：** 文件名由 HTML 中的 `<img src="...">` 决定，不是由你的项目标题决定。如果你把"Project One"改名为"思维进化"，图片文件名仍然要叫 `project-one.jpg`，除非你同时修改 HTML 中的 src 属性：

```html
<!-- 找到卡片中的这行 -->
<img src="screenshots/project-one.jpg" ...>

<!-- 改成你的文件名 -->
<img src="screenshots/thought-evolution.jpg" ...>
```

### 添加语言

在 `<script>` 中的 `i18n` 对象里添加新语言键，然后在菜单中加入对应选项即可。

## 项目结构

```
portfolio-template/
├── index.html          # 主作品集页面
├── blog-template.html  # 博客文章模板（每篇文章复制一份）
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
