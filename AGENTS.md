# AGENTS.md

Static HTML/CSS coursework portfolio ("高级网页设计" by 陈卓然). Flat repo, no build system.

## No tooling
- No `package.json`, bundler, tests, lint, or formatter. Do not look for/lose time on npm/vite/etc.
- To preview: open the `.html` file directly, or run a static server from repo root, e.g. `python -m http.server`.
- Git repo initialized (`git init`); do not commit unless explicitly asked.

## Hard constraints
- **Native HTML/CSS/JS only.** 不使用任何第三方库或 CDN（包括 Font Awesome、Lucide、CDN 资源等）。
- **图标使用 `font/` 目录下的 iconfont 字体图标**（`iconfont.css` + `iconfont.js` + `iconfont.ttf/woff2`）。通过 `<link>` 引入本地 `iconfont.css`，用 `class="iconfont icon-xxx"` 方式使用。
- **数据请求使用原生 `fetch()`** 获取服务器端数据，不使用 axios/jQuery 等。
- All page content is Simplified Chinese. Match the tone; keep `<title>` in the `1012 陈卓然` style.
- Pages live at repo root; images in `img/` (`1.jpg`…`6.jpg`, `5.jpeg`); iconfont assets in `font/`.

## Project mandatory rules (enforced)
- **`czr_` 前缀**: every new CSS class name, `id`, and JS variable must start with `czr_`（陈卓然首字母缩写）。示例：`.czr_container`、`#czr_main`、`let czr_count = 0`。
- **HTML 文件头注释**: every `.html` file must contain at the top of `<body>` a comment block in this exact format:
  ```html
  <!-- 姓名：陈卓然，日期：YYYY-MM-DD，功能名称：XXX -->
  ```
  日期用任务执行当天的实际日期，功能名称写页面的核心用途（一句话）。
- **Prompt logging**: *before* executing any task, append (never overwrite) to `chen_prompt.md` an entry with the execution time, the model used, and the verbatim prompt text.
- **CSS length units + 3D**: pages must use explicit CSS length units and include a CSS3 3D animation.
- **Back-link**: every newly created `.html` file must contain a hyperlink back to the homepage `index.html`（新建的 html 文件必须加入超链接，链接到首页 index.html）。

## `index.html` is the homepage
- `index.html` is a CSS3 3D-animation homepage with a "本目录全部网页" nav grid (`a.chen_link`) linking every root `.html` page.
- **When you add a new `.html` page, also add a matching `chen_link` entry to that nav grid**, encoding spaces in the `href` as `%20`.
- Pages typically carry a fixed "← 返回首页" button (`class="chen_home"`) linking back to `index.html`.

## Filename gotchas
- Several filenames contain spaces and Chinese characters: `3.1 form.html`, `3.2 css.html`, `5.2 盒模型.html`, `7.1上图下文.html`, `7.2左图右文.html`, `8.1css选择器.html`.
- In `href`/`src`, URL-encode spaces as `%20` (see the links in `index.html`).
- In shell commands, quote these paths (PowerShell `-LiteralPath`).

## Shared/external stylesheet
- `css.css` at root is linked only by `5.1.html` (cascade/priority demo). It is not a global stylesheet; most pages use their own inline `<style>`.
