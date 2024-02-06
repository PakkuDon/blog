---
title: "Migrating From Yarn to npm"
date: 2024-02-06T21:11:52+11:00
tags:
  - software development
  - javascript
  - guide
---

There's probably multiple articles of this sort online. But I'm going to be doing these same steps for a few of my projects so I figured I might as well make a post about it 🦀

This guide covers how to switch from Yarn to npm to manage dependencies for a project. This guide assumes a non-complex setup (eg: no monorepos). This guide will **not** cover migrating away from specific features such as [Yarn workspaces](https://yarnpkg.com/features/workspaces).

To switch from Yarn to npm run the following steps in your project's folder:

1. Remove `yarn.lock` as this file will no longer be used.
2. Run `npm install`. This will generate a [`package-lock.json` file](https://docs.npmjs.com/cli/v10/configuring-npm/package-lock-json).
3. Use `git grep yarn` to find any remaining references to `yarn`. Replace these references either with an [equivalent from npm cli](https://docs.npmjs.com/cli/v10/commands) or other command as appropriate.
4. Try running and building your application to confirm that it still works.

Here's some other things that you may need to check:

- [Yarn's resolutions](https://yarnpkg.com/configuration/manifest#resolutions) can be replaced with [npm's overrides](https://docs.npmjs.com/cli/v8/configuring-npm/package-json#overrides) provided that you are using [npm v8.3.0](https://docs.npmjs.com/cli/v8/using-npm/changelog#v830-2021-12-09) or newer.
- I have not verified this yet, but [`.yarnrc` or `.yarnrc.yaml` files](https://yarnpkg.com/configuration/yarnrc) could potentially be replaced with an [.npmrc](https://docs.npmjs.com/cli/v10/configuring-npm/npmrc) file. Available config options can be found in [config | npm Docs](https://docs.npmjs.com/cli/v10/using-npm/config).
