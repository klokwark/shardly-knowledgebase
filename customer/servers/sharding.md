---
title: Sharding
slug: sharding
category: bot
keywords: [shard, sharding, shards, scale, 2500 guilds, sharding manager]
reviewed: 2026-09-15
---

# Sharding

## What a shard is

A shard is one connection to Discord's gateway, handling a slice of your
servers. Past roughly 2,000 Discord servers, Discord requires you to shard;
below that, it is optional and usually not worth it.

## What you get

| Plan | Shards included |
| --- | --- |
| Starter | 1 |
| Pro | 3 |
| Shard | 10 |

More come in packs of five for €5 a week from **Add-ons**.

## Do you need more?

Ask: **how many Discord servers is your bot in?** Divide by 2,000 and round
up. That is your answer.

If your bot is in 400 servers and feels slow, more shards will not help — it
will use more memory for the same work. The problem is somewhere in your code
or your plan's memory. Open a ticket and we will look at it with you.

## Sharding in your code

Discord.js has `ShardingManager`. Your startup file becomes the manager, which
spawns your bot file.

The count usually comes from the environment rather than being hardcoded, so
that adding shards does not mean editing code:

```js
import { ShardingManager } from "discord.js";

const manager = new ShardingManager("./bot.js", {
  token: process.env.DISCORD_TOKEN,
  totalShards: Number(process.env.SHARD_COUNT) || "auto",
});

manager.on("shardCreate", (shard) => console.log(`Launched shard ${shard.id}`));
manager.spawn();
```

`"auto"` asks Discord how many you need, which is usually the right answer.

## Memory

Each shard is a process with its own copy of your bot in memory. Ten shards on
512 MB will not fit. If you are adding shards, look at memory at the same time.

## Still stuck?

[Open a server ticket](https://shardly.xyz/app/support/new) with your server
count and your current plan.
