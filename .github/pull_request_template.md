<!--
malatelier — default pull request template.

Need a more specific form? Append a template query to the PR URL, e.g.
  ?expand=1&template=feature.md
Available: feature.md · bugfix.md · theme-settings.md · upstream-sync.md ·
           chore-build.md · docs.md · release.md
See .github/PULL_REQUEST_TEMPLATE/README.md

Delete sections that do not apply — do not leave empty headings.
-->

## Summary

<!-- What changes and why, in 2-4 sentences. Lead with what a reader or a site admin sees. -->

## Type of change

- [ ] `feature` — new template, layout or theme behavior
- [ ] `fix` — bug fix
- [ ] `settings` — `package.json` → `config` (custom settings, image sizes, posts per page)
- [ ] `style` — CSS only (`assets/css`)
- [ ] `upstream` — changes pulled in from TryGhost/Casper
- [ ] `docs` — README, CLAUDE.md, guides
- [ ] `chore` — dependencies, gulp build, tooling

## Related work

- Issue: <!-- Closes #NNN, or "none" -->
- Upstream reference: <!-- TryGhost/Casper commit/PR, Ghost docs link, or "none" -->

## Changes

<!-- Bullet the substantive changes, grouped by area (templates, partials, CSS, JS, config).
     Cite file:line for anything a reviewer would otherwise have to hunt for. -->

-
-

## Theme impact

<!-- Delete rows that do not apply. -->

| Area | Affected? | Notes |
| --- | --- | --- |
| Layout (`default.hbs`: head, header/nav, footer, scripts) | no | |
| Home / feed (`index.hbs`, `partials/post-card.hbs`, infinite scroll) | no | |
| Post / page (`post.hbs`, `page.hbs`, lightbox) | no | |
| Tag / author archives | no | |
| Error pages (`error.hbs`, `error-404.hbs`) | no | |
| Custom settings (`@custom.*`) | no | |
| Dark mode (`html.dark-mode`, `html.auto-color`) | no | |
| Custom fonts (`gh-font-*`, `--gh-font-*`) | no | |
| Members / subscribe / comments | no | |

## Built assets

<!-- Required if anything under assets/css or assets/js changed; otherwise "No asset change". -->

- [ ] `assets/built/` rebuilt with `npx gulp build` and committed in this PR
- [ ] Built files match the sources (no stale or hand-edited output)

## Screenshots / recordings

<!-- Required for any visible change. Before / after, light and dark, desktop and mobile.
     Note which settings combination each shot uses (navigation layout, header style, feed layout). -->

## Testing

Commands run locally (paste results):

```bash
yarn test       # gulp build + gscan
yarn test:ci    # gscan --fatal --verbose
```

- [ ] `yarn test` passes with no errors
- [ ] `yarn test:ci` passes (no gscan warnings)
- [ ] Verified on a local Ghost instance (`yarn dev` with the theme symlinked, or `yarn zip` uploaded)
- [ ] Checked in at least one Chromium browser and one of Firefox / Safari
- [ ] Checked at mobile, tablet and desktop widths

## Ghost compatibility

- [ ] Only helpers and data available on Ghost ≥ 5.0 (`engines.ghost`) are used, or the minimum was raised on purpose
- [ ] `{{ghost_head}}` is still the last thing in `<head>` and `{{ghost_foot}}` the last thing before `</body>`
- [ ] `.post-feed` / `.post-card` markup still works with `assets/js/infinite-scroll.js`

## Accessibility

- [ ] Interactive elements are keyboard reachable with a visible focus state
- [ ] Images have meaningful `alt` text; icons that carry meaning have labels
- [ ] Colour contrast holds in light and dark mode, including with a custom `--ghost-accent-color`

## Deployment

- Settings a site admin must set or re-check after upload: <!-- none / list -->
- Rollback plan: <!-- re-upload the previous dist/casper.zip, or describe -->

## Breaking changes

- [ ] None
- [ ] Yes — described below (renamed/removed settings, removed templates, raised Ghost minimum)

<!-- Details -->

## Reviewer notes

<!-- Where to start, what you are unsure about, what is intentionally out of scope,
     and any follow-up tasks you propose. -->

## Author checklist

- [ ] Scope limited to the task — no drive-by refactors or unsolicited files
- [ ] Follows existing patterns (template structure, CSS section order in `screen.css`, class naming)
- [ ] Commit messages follow the repo style (short, past tense: "Added …", "Fixed …")
- [ ] Branch is up to date with `main` and has no conflicts
- [ ] No new dependency added, or the addition was agreed and justified below
