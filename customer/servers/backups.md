---
title: Backups
slug: backups
category: server
keywords: [backup, restore, snapshot, download, recover, lost files]
reviewed: 2026-09-15
---

# Backups

A backup is a snapshot of your server's disk at a moment in time.

## What you get

**Two manual slots on every plan**, Starter included.

Scheduled backups depend on the plan:

| Plan | Schedule | Kept |
| --- | --- | --- |
| Starter | none | — |
| Pro | every 24 hours | 14 days |
| Shard | every hour | 30 days |

## Taking one

**Backups** on your server, then **Create backup**. It takes a moment,
depending on how much is on the disk.

Two slots means two. To take a third, delete one first — so keep the one from
before your last big change rather than the newest by reflex.

## When to take one

- Before a reinstall. Always.
- Before deleting anything you are not certain about.
- Before a dependency upgrade you expect to be awkward.
- Before you go away for a week.

## Restoring

Restoring replaces the current disk with the snapshot. Anything written since
is lost.

It asks for a confirmation code, for the same reason a reinstall does.

## Download them

A backup on the server is not a backup. If the account goes, so does it.

Download the ones that matter and keep them somewhere else. This is
particularly true before cancelling — when a subscription ends and the server
is removed, its backups go with it and we cannot get them back.

## What is in one

The disk: your code, your uploads, anything your bot wrote.

**Not** your variables or your token — those are configuration, not disk.
Write them down separately.

## Still stuck?

[Open a server ticket.](https://shardly.xyz/app/support/new)
