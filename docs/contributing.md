---
title: "Contributing"
description: "Steps for easier development and debugging purposes of Vue.js Warehouse."
permalink: /docs/vue-warehouse/contributing
created: "2018-03-29T10:57:00Z"
published: "2018-03-30T23:28:40.392224Z"
modified: "2019-06-05T12:51:34.314Z"
---

# Contributing

Please make sure to read this **Contributing Guide** before making a contribution.

## Development setup

1. Fork and clone the repo
2. Run `npm install` to install dependencies
3. Run `npm test` to run validation
4. Create a branch for your PR with `git checkout -b pr/your-branch-name`

### Commonly used NPM scripts

**Watch and serve the examples with hot reload**
```shell
npm run start
```

**Lint source codes**
```shell
npm run lint
```

**Run unit tests**
```shell
npm run test
```

**Build all dist files**
```shell
npm run build
```

## Issue Reporting Guidelines

- The [issue list][issues-link] of this project is **exclusively** for bug reports and feature requests. Non-conforming issues will be closed immediately.

- Try to search for your issue, it may have already been answered or even fixed in the development branch.

- Check if the issue is reproducible with the latest stable version of Vue. If you are using a pre-release, please indicate the specific version you are using.

- It is **required** that you clearly describe the steps necessary to reproduce the issue you are running into. Issues with no clear repro steps will not be triaged. If an issue labeled "request-more-info" receives no further input from the issue author for more than 5 days, it will be closed.

- For bugs that involves build setups, you can create a reproduction repository with steps in the README.

- If your issue is resolved but still open, don't hesitate to close it. In case you found a solution by yourself, it could be helpful to explain how you fixed it.

## Pull Request Guidelines

- The `master` branch is basically just a snapshot of the latest stable release. All development should be done in dedicated branches. **Do not submit PRs against the `master` branch.**

- Checkout a topic branch from the relevant branch, e.g. `develop`, and merge back against that branch.

- Work in the `src` an `nuxt` folders and **DO NOT** checkin `dist` in the commits.

- It's OK to have multiple small commits as you work on the PR - we will let GitHub automatically squash it before merging.

- Make sure `npm run lint` and `npm run test` passes.

- If adding new feature:
  - Add accompanying test case.
  - Provide convincing reason to add this feature. Ideally you should open a suggestion issue first and have it greenlighted before working on it.

- If fixing a bug:
  - Provide detailed description of the bug in the PR. Live demo preferred.


[issues-link]: https://github.com/bazzite/vue-warehouse/issues
