# Eggtart

A Hugo theme extension built on PaperMod. System fonts by default; no bundled fonts,
personal articles, credentials, deployment scripts, or site-specific CDN addresses.

Features: restrained light/dark styling, article descriptions, ordered series,
selective archives, GitHub-style Markdown alerts, MathJax, and Mermaid.

## Install

Requires Hugo 0.146 or later. Developed with Hugo Extended 0.164.0.

From your Hugo site root:

```sh
git submodule add https://github.com/joechenrh/hugo-theme-eggtart.git themes/eggtart
git submodule add https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
git -C themes/PaperMod checkout 154d006e0182dfc7da38008323976b02e6bfab4a
```

Set `theme = ["eggtart", "PaperMod"]` in `hugo.toml`. Eggtart must come first.
Both dependencies are pinned by your site's Git submodule commits. See `exampleSite/`
for minimal configuration and fictional content. Do not use the extension without PaperMod.

## Content

- Add `series = ["example"]` and `series_part = 1` to a post. Add series metadata at
  `content/series/example/_index.md`. Series navigation uses the first assigned series.
- Set `archived = true` to hide a published post from the home page. Create
  `content/archive.md` with `layout = "archived"` and `url = "/archive/"`.
  An archive link appears first on the Tags page. Tags, RSS, and direct URLs remain accessible.
- Use `> [!NOTE]`, `> [!TIP]`, `> [!IMPORTANT]`, `> [!WARNING]`, or `> [!CAUTION]`.
  Custom titles are supported; folding signs are currently rendered as static callouts.
- Set `math = true` for dollar-delimited MathJax. Set `mermaid = true` for Mermaid fences.

## Site customization

Keep site overrides in your own `assets/css/extended/zz-custom.css`. Fonts, font-face
declarations, and preloads belong to the site. This extension uses PaperMod's system fonts.

For site-specific scripts or font preloads, override `layouts/_partials/extend_head.html`
and include `{{ partial "eggtart/head.html" . }}` before your own additions.

Optional `[params]` settings:

- `assetBase`: CDN base for Markdown images under `/images/` or legacy `/wp-content/uploads/`.
  Omit to keep local URLs. Uploading images is the site's responsibility.
- `mathjaxURL`: alternative MathJax `tex-chtml.js` URL. Defaults to jsDelivr MathJax 3.2.2.

Standard PaperMod settings still apply. Match `mainSections` to your article section.

## License and credits

MIT; original PaperMod copyright and permission notices are retained in `LICENSE`.
PaperMod: https://github.com/adityatelange/hugo-PaperMod
This is an independent extension, not an official PaperMod release.
