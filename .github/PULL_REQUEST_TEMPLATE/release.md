<!--
Release — Version bump, theme zip and deployment to Ghost
Suggested label: release
Template: .github/PULL_REQUEST_TEMPLATE/release.md

malatelier — release PR. Note: `yarn ship` / `gulp release` target upstream
TryGhost/Casper and are not set up for this fork — do not run them.
-->

## Release

- Version: <!-- e.g. 5.10.0 -->
- Previous version: <!-- e.g. 5.9.0 -->
- Type: <!-- major / minor / patch -->
- Target date:

## Scope

Merged since the previous release:

| Area | Change | PR |
| --- | --- | --- |
| | | #NNN |

## Version & notes

- [ ] `version` bumped in `package.json`
- [ ] Release notes written (user-visible changes, settings changes, fixes)
- [ ] Every user-visible change in scope is listed

## Breaking changes

- [ ] None
- [ ] Yes — listed below with what site admins must do

<!-- Renamed/removed settings, removed templates, raised Ghost minimum version. -->

## Settings

- New or changed custom settings admins should review: <!-- none / list -->
- `engines.ghost` minimum: <!-- unchanged / old → new -->

## Release verification

```bash
yarn install
yarn test
yarn test:ci
yarn zip
```

- [ ] `assets/built/` up to date with the sources
- [ ] `yarn test:ci` clean
- [ ] `dist/casper.zip` uploaded to a staging / local Ghost and activated without errors
- [ ] Home, post, page, tag, author, 404 and members pages smoke-tested, light and dark
- [ ] Theme settings in Ghost Admin → Design reviewed after upload

## Deployment plan

1. <!-- download the current theme zip from Ghost Admin as a backup -->
2. <!-- upload dist/casper.zip in Ghost Admin → Settings → Design → Change theme -->
3. <!-- activate and re-check theme settings -->
4. <!-- smoke-test the live site -->

Rollback plan: <!-- re-upload and activate the backup zip -->

## Known issues

<!-- Shipping-with-known-issues list, or "none". -->

## Sign-off

- [ ] Visual review sign-off
- [ ] Technical sign-off
