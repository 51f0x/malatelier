# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A Ghost (≥5.0) theme forked from [Casper](https://github.com/TryGhost/Casper), Ghost's default theme. The package is still named `casper` in `package.json`, so the zip is `dist/casper.zip`. There is no application server here: Ghost renders the Handlebars templates, and this repo only provides templates, CSS, and client JS.

## Commands

Requires Node and Yarn (v1, `yarn.lock`).

```bash
yarn install        # install dev dependencies
yarn dev            # gulp: build, then watch css/js/hbs with livereload
yarn test           # runs `gulp build` (pretest), then `gscan .` theme validation
yarn test:ci        # gscan --fatal --verbose (fails on warnings too)
yarn zip            # build + package theme into dist/casper.zip for upload to Ghost
npx gulp build      # build css + js only
```

There are no unit tests. `gscan` (Ghost's theme validator) is the only check. Run `yarn test` after changing templates, `package.json` `config`, or helper usage.

`yarn ship` / `gulp release` are upstream Casper release scripts: they bump the version, push tags, and draft a GitHub release against `TryGhost/Casper` using `GST_TOKEN`. They are not set up for this fork.

## Build pipeline (gulpfile.js)

- **CSS:** each top-level file in `assets/css/*.css` (`screen.css`, `global.css`) goes through PostCSS (`postcss-easy-import` for `@import`, `postcss-color-mod-function`, autoprefixer, cssnano) and is written to `assets/built/` with sourcemaps. `screen.css` imports `global.css` (reset/base styles).
- **JS:** `assets/js/lib/*.js` (vendored libraries) are concatenated first, then `assets/js/*.js`, then uglified into a single `assets/built/casper.js`. Load order matters because the theme's own scripts depend on the libraries.
- **`assets/built/` is committed.** Rebuild and commit the built files together with any source change in `assets/css` or `assets/js`. Ghost serves the built files, never the sources.
- jQuery 3.5.1 is loaded from a CDN in `default.hbs`, not bundled. `fitVids` and the mobile menu toggle are initialized inline there.

## Template architecture

- `default.hbs` is the layout: `<head>`, the site header/nav, the footer, and scripts. Every other template starts with `{{!< default}}` and is injected at `{{{body}}}`.
- Routing templates: `index.hbs` (home/feed), `post.hbs`, `page.hbs`, `tag.hbs`, `author.hbs`, `error.hbs`, `error-404.hbs`. Slug-specific overrides such as `page-about.hbs`, `tag-news.hbs`, and `author-ali.hbs` are picked up automatically by Ghost.
- `partials/post-card.hbs` is the shared feed item. It is used by index, tag, author, 404, and post (related posts), and `infinite-scroll.js` depends on its `.post-card` class and on the `.post-feed` container.
- SVG icons are partials in `partials/icons/` and are included with `{{> "icons/<name>"}}`.
- `partials/lightbox.hbs` (PhotoSwipe markup) is included only on posts/pages and works with `assets/js/lightbox.js`.
- `{{ghost_head}}` must remain the last thing in `<head>`, and `{{ghost_foot}}` the last thing before `</body>`.

## Theme settings (`package.json` → `config`)

- `config.custom` defines the settings that appear in Ghost Admin → Design, such as `navigation_layout`, `title_font`, `body_font`, `color_scheme`, `feed_layout`, `header_style`, and `post_image_style`. Templates read them as `@custom.<key>`, usually with `{{#match}}`.
- Most settings take effect by adding **body/html classes** in `default.hbs` (for example `is-head-left-logo`, `has-serif-title`, `has-sans-body`, `has-cover`, `dark-mode`, `auto-color`). The CSS then keys off those classes. To add a new setting, you usually need to change `config.custom`, the class logic in `default.hbs` (or the relevant template), and the selectors in `screen.css`.
- `color_scheme` maps to `html.dark-mode` / `html.auto-color`, and the dark mode styles live in section 11 of `screen.css`.
- Ghost's custom fonts feature adds `gh-font-heading*` / `gh-font-body*` classes and the `--gh-font-heading` / `--gh-font-body` variables. The CSS uses these variables and falls back to the theme's own serif/sans choice with `:not([class*="gh-font-heading"])` guards.
- `--ghost-accent-color` is injected by Ghost (Admin → Brand) and is used throughout the CSS.
- `config.image_sizes` defines the responsive image widths used with the `{{img_url ... size="..."}}` helper, and `posts_per_page` sets the feed page size.

## CSS layout

`assets/css/screen.css` is one large file organized by a numbered table of contents at the top: Global, Layout, Site Header, Site Navigation, Post Feed, Single Post (byline, subscribe, read more, comments), Author, Tag, Error, Footer, Dark Mode, Lightbox. Add new styles to the matching section instead of creating new files. Any new top-level file in `assets/css/` would be built as a separate stylesheet.
