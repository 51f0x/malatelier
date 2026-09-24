<!--
Bug fix — Correct incorrect rendering or behavior
Suggested label: fix
Template: .github/PULL_REQUEST_TEMPLATE/bugfix.md

malatelier — bug fix PR. Show the bug, name the cause, prove the fix.
-->

## Summary

<!-- What was broken and what this changes, in 2-4 sentences. -->

- Issue: <!-- Fixes #NNN -->
- Severity: <!-- blocker / major / minor / cosmetic -->
- Introduced by: <!-- commit, release, or upstream Casper change, if known -->
- Affected: <!-- templates, browsers, Ghost versions, settings combinations -->

## Symptom

<!-- What readers or admins saw: broken layout, missing element, JS error, wrong colours. -->

## Reproduction

1.
2.
3.

Settings in effect: <!-- navigation layout, header style, feed layout, color scheme, fonts -->
Browser / viewport:

Expected: <!-- what should happen -->
Actual (before this PR): <!-- what happened -->

## Root cause

<!-- The actual defect, cited as file:line. Not "added a guard" — why it was missing. -->

## Fix

<!-- What changed and why this is the right place to fix it. Note alternatives you rejected. -->

-

## Blast radius

- Other templates / selectors with the same defect: <!-- checked and listed, or "none found" -->
- Settings combinations re-checked: <!-- list -->
- Dark mode / custom fonts / accent colour implicated: <!-- no / yes -->
- Also present upstream in TryGhost/Casper: <!-- no / yes + link -->

## Built assets

- [ ] `assets/built/` rebuilt with `npx gulp build` and committed (or no CSS/JS change)

## Screenshots / logs

<!-- Before/after for visual bugs; console output for JS bugs. -->

## Testing

```bash
yarn test
yarn test:ci
```

- [ ] `yarn test` and `yarn test:ci` pass
- [ ] Reproduction steps above verified fixed on a local Ghost instance
- [ ] Neighbouring templates and settings combinations checked for regressions

## Deployment

- Admin action required after upload: <!-- no / describe -->
- Rollback plan: <!-- re-upload the previous dist/casper.zip -->

## Author checklist

- [ ] Fix is minimal and scoped to the defect
- [ ] Root cause addressed, not just the symptom
- [ ] Commit message in repo style ("Fixed …")
