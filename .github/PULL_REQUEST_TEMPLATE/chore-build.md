<!--
Chore / build — Dependencies, gulp/PostCSS pipeline, tooling or CI
Suggested label: chore
Template: .github/PULL_REQUEST_TEMPLATE/chore-build.md

malatelier — chore PR. The build output (assets/built/) is committed and served
by Ghost as-is, so tooling changes can change what readers get.
-->

## Summary

<!-- What changes in the toolchain and why, in 2-4 sentences. -->

## Category

- [ ] Dependencies (add, remove, upgrade — incl. Renovate PRs)
- [ ] Build pipeline (`gulpfile.js`: PostCSS plugins, JS concat/uglify, zip)
- [ ] Browser support (`browserslist`)
- [ ] Theme validation (`gscan` version, `test` scripts)
- [ ] CI / GitHub config (`.github/`)
- [ ] Agent tooling (`.claude/`, `CLAUDE.md`)

## Changes

-
-

## Dependencies

<!-- Required if package.json / yarn.lock changed; otherwise "no dependency change". -->

| Package | From → To | Reason |
| --- | --- | --- |

- [ ] Addition was agreed before it was made
- [ ] `yarn.lock` updated with `yarn install` (Yarn v1), not hand-edited
- [ ] Licence acceptable for an MIT-licensed theme
- [ ] Breaking changes in upgraded packages reviewed against our usage

## Build output

- [ ] `npx gulp build` run and `assets/built/` committed
- [ ] Diff of `assets/built/` reviewed — changes are explained by this PR (e.g. new autoprefixer rules), not unexpected
- [ ] `yarn zip` still produces a working `dist/casper.zip`

## Verification

```bash
yarn install
yarn test
yarn test:ci
yarn zip
```

- [ ] Clean install works from scratch (`rm -rf node_modules && yarn install`)
- [ ] `yarn dev` still builds and livereloads
- [ ] `yarn test:ci` passes; any new gscan warnings are addressed

Output worth quoting:

```
```

## Deployment

- Needs a theme re-upload: <!-- no (tooling only) / yes (built output changed) -->
- Rollback: <!-- revert commit -->

## Author checklist

- [ ] Change is scoped to the stated category; no unrelated template or style changes
