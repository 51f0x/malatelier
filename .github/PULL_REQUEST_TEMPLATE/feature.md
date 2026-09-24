<!--
Feature — New templates, partials, layouts or theme behavior
Suggested label: feature
Template: .github/PULL_REQUEST_TEMPLATE/feature.md

malatelier — feature PR. Ghost renders the templates; this theme only ships
Handlebars, CSS and client JS.
-->

## Summary

<!-- What this adds and who it is for (readers, members, site admins), in 2-4 sentences. -->

## Related work

- Issue: <!-- Closes #NNN, or "none" -->
- Reference: <!-- Ghost theme docs, upstream Casper, design mock, or "none" -->
- Depends on: <!-- PRs or issues that must land first, or "none" -->

## Acceptance criteria

<!-- List the criteria from the issue and check each one you verified. -->

- [ ]
- [ ]

## Implementation

| Area | Changes |
| --- | --- |
| Templates (`*.hbs`) | |
| Partials (`partials/`) | |
| CSS (`assets/css/screen.css` section) | |
| JS (`assets/js/`) | |
| Config (`package.json` → `config`) | |

Design decisions worth reviewing: <!-- trade-offs, alternatives rejected -->

## Theme impact

<!-- Delete rows that do not apply. -->

| Area | Affected? | Notes |
| --- | --- | --- |
| Layout (`default.hbs`) | no | |
| Home / feed + infinite scroll | no | |
| Post / page + lightbox | no | |
| Tag / author archives | no | |
| Error pages | no | |
| Custom settings (`@custom.*`) | no | |
| Dark mode | no | |
| Custom fonts | no | |
| Members / subscribe / comments | no | |

## Settings & data

- New or changed custom settings: <!-- keys + defaults, or "none" — use theme-settings.md sections if any -->
- New Ghost helpers or data used: <!-- e.g. {{#get}}, @site.*, or "none" -->
- New `{{img_url}}` sizes: <!-- or "none" -->
- Slug-specific templates added (`page-*.hbs`, `tag-*.hbs`, `author-*.hbs`): <!-- or "none" -->

## Built assets

- [ ] `assets/built/` rebuilt with `npx gulp build` and committed (or no CSS/JS change)
- [ ] New JS placed correctly for the concat order (`assets/js/lib/` before `assets/js/`)

## Screenshots / recordings

| | Before | After |
| --- | --- | --- |
| Desktop light | | |
| Desktop dark | | |
| Mobile | | |

<!-- Name the settings combination used (navigation layout, header style, feed layout, post image style). -->

## Testing

```bash
yarn test
yarn test:ci
```

- [ ] `yarn test` and `yarn test:ci` pass
- [ ] Verified on a local Ghost instance with realistic content (long titles, no feature image, many tags)
- [ ] Verified with each relevant setting option, not only the default
- [ ] Checked at mobile, tablet and desktop widths
- [ ] Keyboard navigation and focus states checked

## Ghost compatibility

- [ ] Works on Ghost ≥ 5.0 (`engines.ghost`), or the minimum was raised on purpose
- [ ] `{{ghost_head}}` / `{{ghost_foot}}` positions unchanged
- [ ] No hardcoded site URLs, colours that ignore `--ghost-accent-color`, or fonts that bypass `--gh-font-*`

## Rollout

- Settings a site admin must set after upload: <!-- none / list -->
- Rollback plan: <!-- re-upload the previous dist/casper.zip -->

## Breaking changes

- Breaking: <!-- none, or what changes for existing sites and how to adapt -->

## Follow-ups proposed

<!-- Out-of-scope work you noticed. -->

-

## Author checklist

- [ ] Scope limited to the task; no drive-by refactors
- [ ] New styles added to the matching numbered section of `screen.css`
- [ ] README / CLAUDE.md updated where theme structure or settings changed
- [ ] No new dependency added without prior agreement
