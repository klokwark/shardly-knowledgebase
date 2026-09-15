---
title: Import from GitHub
slug: github-import
category: bot
keywords: [github, import, git, repository, clone, deploy, private repo]
reviewed: 2026-09-15
---

# Import from GitHub

Pull a repository straight onto your server.

## Connect GitHub

**Bot settings → Import from GitHub → Connect.** Authorise the app.

GitHub is a linked account, never a way to sign in to Shardly. It exists so we
can read your repositories on your behalf, and nothing else.

## Import

Pick the repository, pick the branch, import. We fetch the archive, unpack it
at the top level, and remove the wrapper folder GitHub wraps everything in.

Private repositories work — that is the point of connecting the account.

## What it does to what is already there

Files with the same names are **replaced**. Files that are only on the server
and not in the repository are **left alone**.

So a `.env` you created by hand survives an import. A `config.json` that
exists in both is overwritten by the repository's version.

## Anything in `.gitignore` is not imported

It is not in the repository, so we cannot fetch it. This catches people out
with `node_modules` (fine — it reinstalls) and with config files (not fine —
recreate them or use variables).

## Limits

| Plan | Imports per 30 minutes | Largest repository |
| --- | --- | --- |
| Starter | 5 | 60 MB |
| Pro | 10 | 60 MB |
| Shard | 20 | 120 MB |

An import unpacks an archive on a real machine, which is why it is rationed.
If you hit the limit, the message says how long to wait.

## Repository too large

The ceiling applies to the archive. If yours is over it, the usual cause is
committed `node_modules` or binary assets — both worth removing from the
repository anyway.

## After importing

Restart from the console. An import changes files on disk; it does not restart
your process.

## Still stuck?

[Open a server ticket](https://shardly.xyz/app/support/new) with the
repository name and what the error said.
