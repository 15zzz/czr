# AGENTS.md

Static HTML/CSS coursework portfolio ("高级网页设计" by 陈卓然). Flat repo, no build system.

## No tooling
- No `package.json`, bundler, tests, lint, or formatter. Do not look for/lose time on npm/vite/etc.
- To preview: open the `.html` file directly, or run a static server from repo root, e.g. `python -m http.server`.
- Git repo initialized (`git init`); do not commit unless explicitly asked.

## Hard constraints
- Native HTML/CSS only. **No CDN / external libraries / external assets.** All styling lives inline in `<style>` (as in `index.html`) or in local files.
- All page content is Simplified Chinese. Match the tone; keep `<title>` in the `1012 陈卓然` style.
- Pages live at repo root; images in `img/` (`1.jpg`…`6.jpg`, `5.jpeg`).

## Project mandatory rules (enforced)
- **`chen_` prefix**: every new CSS class name, `id`, and JS variable must start with `chen_`.
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
