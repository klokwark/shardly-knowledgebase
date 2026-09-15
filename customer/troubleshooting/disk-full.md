---
title: Disk full
slug: disk-full
category: server
keywords: [disk, storage, full, enospc, no space, cleanup, space left]
reviewed: 2026-09-15
---

# Disk full

Writes fail, installs fail, the log says `ENOSPC` or `no space left on
device`.

## What you have

| Plan | Disk |
| --- | --- |
| Starter | 5 GB |
| Pro | 20 GB |
| Shard | 80 GB |

## Find what is using it

Open the file manager and look at the top level, biggest first. In practice it
is one of four things:

1. **Log files.** Written forever, never rotated. The most common cause by a
   distance.
2. **Downloaded media.** Images, audio, attachments your bot fetched and never
   deleted.
3. **Backups kept on the server.** Download them and delete the local copies.
4. **`node_modules` in several folders** from abandoned experiments.

## Clean it up

Delete what you do not need, then restart.

Deleting still works when a disk is full — it is writing that fails — so you
are not stuck.

## Stop it happening again

**Rotate your logs.** If you write your own, cap them:

```js
// Keep the last 10,000 lines rather than an ever-growing file.
```

Or simply use `console.log` and read the live console, which does not touch
your disk at all.

**Clean up temporary files.** If you download something to process it, delete
it afterwards — including when the processing throws. `try/finally`.

## npm cache

`npm` keeps a cache that can grow surprisingly large. If you are stuck for
room, clearing it is safe — it repopulates.

## Still stuck?

[Open a server ticket.](https://shardly.xyz/app/support/new) We can see the
disk from our side and tell you what is taking it.
