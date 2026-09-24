<!--
Upstream sync — Pull changes from TryGhost/Casper into this fork
Suggested label: upstream
Template: .github/PULL_REQUEST_TEMPLATE/upstream-sync.md

malatelier — upstream sync PR. Upstream changes land on top of our
customisations; every conflict is a decision that should be visible here.
-->

## Summary

<!-- What is being brought in from upstream and why now, in 2-4 sentences. -->

## Upstream range

- Upstream: `TryGhost/Casper` <!-- branch or tag -->
- From: <!-- last synced commit/tag -->
- To: <!-- commit/tag being synced -->
- Method: <!-- merge / cherry-pick of listed commits -->

| Upstream commit / PR | Change | Taken? |
| --- | --- | --- |
| | | yes / no / partial |

Commits skipped and why: <!-- or "none" -->

## Conflicts & local customisations

<!-- Every file where upstream touched something we have customised. -->

| File | Conflict | Resolution |
| --- | --- | --- |
| | | kept ours / took theirs / merged |

- [ ] No local customisation silently lost
- [ ] Release scripts (`yarn ship`, `gulp release`) still not pointed at our fork by accident

## Settings & compatibility

- `config.custom` changes from upstream: <!-- none / list — see theme-settings.md for admin impact -->
- `engines.ghost` change: <!-- none / old → new -->
- Dependency changes (`package.json`, `yarn.lock`): <!-- none / summary -->

## Built assets

- [ ] `assets/built/` rebuilt locally after resolving conflicts (never take built files from either side as-is)
- [ ] `yarn.lock` regenerated with `yarn install`, not hand-merged

## Screenshots

<!-- Only where upstream changes something visible. Light and dark, desktop and mobile. -->

## Testing

```bash
yarn install
yarn test
yarn test:ci
```

- [ ] `yarn test` and `yarn test:ci` pass
- [ ] Home, post, page, tag, author and 404 checked on a local Ghost instance
- [ ] Our customised templates and settings still behave as before

## Deployment

- Admin action required after upload: <!-- none / describe -->
- Rollback plan: <!-- re-upload the previous dist/casper.zip -->

## Author checklist

- [ ] Upstream commit messages / authorship preserved (merge or cherry-pick, not copy-paste)
- [ ] CLAUDE.md updated if upstream changed build or structure
