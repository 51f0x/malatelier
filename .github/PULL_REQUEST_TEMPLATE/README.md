# Pull request templates

`.github/pull_request_template.md` is the **default** template: GitHub loads it automatically
for every new pull request in this repository. It is deliberately broad — delete the sections
that do not apply to your change.

The files in this directory are **additional, type-specific templates**. GitHub does not offer a
picker for pull requests, so they are selected with a `template` query parameter on the compare
URL.

## Using a specific template

Append `?expand=1&template=<file>` to the compare URL:

```
https://github.com/51f0x/malatelier/compare/main...<your-branch>?expand=1&template=feature.md
```

| Template | Use for |
| --- | --- |
| [`feature.md`](feature.md) | New templates, partials, layouts or theme behavior |
| [`bugfix.md`](bugfix.md) | Bug fixes — root cause plus how it was verified |
| [`theme-settings.md`](theme-settings.md) | `package.json` → `config` changes: custom settings, image sizes, posts per page |
| [`upstream-sync.md`](upstream-sync.md) | Pulling changes from [TryGhost/Casper](https://github.com/TryGhost/Casper) into this fork |
| [`chore-build.md`](chore-build.md) | Dependencies, gulp/PostCSS pipeline, tooling, CI |
| [`docs.md`](docs.md) | README, CLAUDE.md and other documentation |
| [`release.md`](release.md) | Cutting a release — version bump, zip, deploy to Ghost |

If your change spans several categories (a feature that also adds a custom setting, for example),
use the closest template and fill in the extra sections from the default template rather than
opening separate PRs for parts of the same change.

## Conventions these templates assume

- **gscan is the gate:** `yarn test` (build + `gscan .`) must pass before review; `yarn test:ci`
  (fatal on warnings) is the bar for merging. There are no unit tests.
- **Built assets are committed:** any change in `assets/css` or `assets/js` ships with the
  rebuilt `assets/built/` files in the same PR. Ghost serves only the built files.
- **Settings are a contract with site admins:** renaming or removing a `config.custom` key or
  option drops the value an admin already chose. Treat it as a breaking change.
- **Visible changes need screenshots:** light and dark, desktop and mobile.
- **Commits:** short, past-tense subjects in the upstream Casper style ("Added …", "Fixed …",
  "Updated …").

Full contributor guidance lives in [`CLAUDE.md`](../../CLAUDE.md).
