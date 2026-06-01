# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Single-file static site: [index.html](index.html). A dark-themed landing page that showcases and links to four live AI apps (TraktApp, StoryVault, Skill-Memory Agent, AI Typing Tutor — all under `*.michaelsavastano.com`). No build system, no dependencies, no package manager, no tests, no backend. Everything — markup, CSS, JS — lives inline in `index.html`.

## Running

Open `index.html` directly in a browser, or serve the folder:

```powershell
python -m http.server 8000   # then open http://localhost:8000
```

## Architecture notes

- **All styling is inline** in a single `<style>` block driven by CSS custom properties under `:root` (colors, radius, fonts, `--max` page width). Change the theme by editing those variables, not scattered values.
- **One small inline `<script>`** at the bottom wires a pointer-follow glow on `.card` elements via the `--mx` CSS variable. No framework.
- **Page sections**: sticky `nav` → `header.hero` (grid + radial-glow background) → `#work` gallery (`.grid` of four `.card`s, each linking out to a live app URL) → `#contact` CTA band → `footer`. Anchor links (`#work`, `#contact`) drive in-page nav. To add/edit an app, edit the matching `.card` anchor in `#work` (href, `<h3>`, `<p>`, `.tag`s).
- Contact email `millhouse5000@gmail.com` appears in the CTA `mailto:` and footer.
