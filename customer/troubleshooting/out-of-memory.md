---
title: Out of memory
slug: out-of-memory
category: server
keywords: [memory, oom, heap, killed, ram, out of memory, leak]
reviewed: 2026-09-15
---

# Out of memory

Your process exceeded the memory your plan allows and was killed.

## What it looks like

- `JavaScript heap out of memory`
- `FATAL ERROR: Reached heap limit`
- Or a sudden death with no error at all — the kernel does not ask politely.

## How much do you have?

| Plan | Memory |
| --- | --- |
| Starter | 512 MB |
| Pro | 2 GB |
| Shard | 8 GB |

512 MB is enough for a normal bot in a few hundred servers. It is not enough
for several shards, a large cache, or image processing.

## Find out whether it is a leak

Log it every minute:

```js
setInterval(() => {
  const mb = process.memoryUsage().heapUsed / 1024 / 1024;
  console.log(`heap ${mb.toFixed(1)} MB`);
}, 60_000);
```

- **Climbs and never comes down** → a leak.
- **Spikes then recovers** → a single expensive operation.
- **High and flat from the start** → you have simply outgrown the plan.

## The usual leak

A collection that only ever grows.

```js
// Leaks: nothing is ever removed.
const cooldowns = new Map();
cooldowns.set(userId, Date.now());
```

Delete entries when you are done with them, or use a structure that expires
them.

## Shards

Every shard is a full copy of your bot in memory. Three shards on Starter is
three copies of everything in 512 MB. See [sharding](../servers/sharding.md).

## Caching everything Discord sends

Discord.js caches aggressively by default. A bot in many servers caching every
member will use a great deal of memory. Configure `makeCache` to keep only
what you use.

## Just need more?

Move up a tier. Pro is four times Starter's memory for €3 a week more, and
that is often the right answer rather than a week of optimisation.

## Still stuck?

[Open a ticket](https://shardly.xyz/app/support/new) with the memory log above
over about an hour.
