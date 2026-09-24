<!--
Theme settings — package.json → config (custom settings, image sizes, posts per page)
Suggested label: settings
Template: .github/PULL_REQUEST_TEMPLATE/theme-settings.md

malatelier — settings PR. config.custom is a contract with every site admin:
the keys and option labels are what Ghost stores their choices under.
-->

## Summary

<!-- What admins can now configure, or what changes about an existing setting, in 2-4 sentences. -->

## Related work

- Issue: <!-- Closes #NNN, or "none" -->
- Reference: <!-- Ghost custom settings docs, upstream Casper, or "none" -->

## Settings changes

| Key | Type | Options / default | Group | Change |
| --- | --- | --- | --- | --- |
| | select / boolean / text / color / image | | site-wide / homepage / post | added / changed / removed |

Other `config` changes:

- `image_sizes`: <!-- none / sizes added or changed -->
- `posts_per_page`: <!-- none / old → new -->
- `card_assets`: <!-- none / change -->

## Wiring

<!-- Most settings take effect through a class in default.hbs plus matching CSS. -->

| Setting | Read in (`@custom.<key>`) | Class / markup produced | CSS selectors |
| --- | --- | --- | --- |
| | `default.hbs:NN` | | `screen.css` section |

- [ ] Every option of every changed setting renders correctly, not only the default
- [ ] Settings combine sensibly (e.g. navigation layout × header style × cover image on/off)
- [ ] Dark mode (`color_scheme`) and custom fonts still apply on top of the new classes

## Compatibility for existing sites

- [ ] Change is additive — no existing key or option label renamed or removed
- [ ] Renames/removals present — described below with what admins must re-select

Renamed or removed keys/options and admin impact:

- Default for sites that never touched the setting: <!-- how it looks after upload -->

## Built assets

- [ ] `assets/built/` rebuilt with `npx gulp build` and committed (or no CSS change)

## Screenshots

<!-- One shot per option (or per meaningful combination), light and dark. -->

## Testing

```bash
yarn test
yarn test:ci
```

- [ ] `yarn test` and `yarn test:ci` pass (gscan validates `config.custom`)
- [ ] Settings appear as expected in Ghost Admin → Design → Theme settings, in the right group
- [ ] Switching each option in Admin updates the site without errors

## Deployment

- Admin action required after upload: <!-- none / re-check settings X, Y -->
- Rollback plan: <!-- re-upload the previous zip; note whether admins lose any choice made in between -->

## Author checklist

- [ ] Setting labels and option text read well in Ghost Admin
- [ ] README / CLAUDE.md updated if the settings list changed
- [ ] Commit message in repo style ("Added … setting")
