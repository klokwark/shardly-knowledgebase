---
title: Dependencies will not install
slug: dependency-install-fails
category: bot
keywords: [npm, install, dependencies, package.json, node_modules, build failed]
reviewed: 2026-09-15
---

# Dependencies will not install

Installation runs when your server starts. When it fails, the console says so
before your code ever runs.

## `ENOENT: package.json`

There is no `package.json` at the top level.

Either it is missing, or it is inside a wrapper folder. Move it up in the file
manager.

## `ERESOLVE unable to resolve dependency tree`

Two of your dependencies disagree about a shared version.

- Update the older one.
- Or remove the pin that causes the conflict.
- `--legacy-peer-deps` will force it through but leaves you with a
  combination nobody tested. Last resort.

## `EACCES` or permission errors

Usually a `node_modules` uploaded from your own machine, carrying ownership
that means nothing here.

Delete `node_modules` entirely and restart. Let it install fresh — and do not
upload `node_modules` in the first place; it is slower than installing and
frequently breaks.

## `node-gyp` / `python` / `make` errors

A dependency wants to compile native code. The build tools for that are not
available on a bot host.

Look for a pure-JavaScript alternative. For the common ones:

- `bcrypt` → `bcryptjs`
- `canvas` → do the rendering elsewhere
- `sqlite3` → `better-sqlite3` sometimes works, often does not

If you genuinely need a native module, open a ticket and say which — we would
rather know which ones people need.

## Runs out of disk halfway

`node_modules` is bigger than people expect. See [disk
full](disk-full.md).

## It worked yesterday

You are probably not pinning versions. Commit your `package-lock.json` and the
same versions install every time.

## Still stuck?

[Open a ticket](https://shardly.xyz/app/support/new) with the install output —
all of it, from the first npm line.
