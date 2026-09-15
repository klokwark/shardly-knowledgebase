---
title: Rate limited by Discord
slug: rate-limited-by-discord
category: bot
keywords: [rate limit, 429, too many requests, discord api, cloudflare ban, throttled]
reviewed: 2026-09-15
---

# Rate limited by Discord

Discord limits how fast a bot can call its API. Past that it refuses, and past
that by a lot it bans the IP for an hour.

This is between your bot and Discord. It is not something Shardly does to you.

## What it looks like

- `429 Too Many Requests` in your log
- `You are being rate limited`
- Discord.js warning about a rate limit bucket
- In the worst case, a Cloudflare ban for an hour

## The usual causes

**A loop with no wait.** Editing a message every iteration, or sending to
every server in a `for` loop with nothing between.

**Editing too often.** A progress bar or countdown updating every second will
hit the limit on that channel. Every five seconds is usually plenty.

**Retrying immediately on failure.** A failed call retried in a tight loop
makes the problem worse, not better.

**Fetching what you already have.** `guild.members.fetch()` on every message
is a lot of requests. Use the cache.

## Fixing it

- Let discord.js queue for you. It respects the limits if you await properly —
  most trouble comes from firing requests without awaiting.
- Put a delay in bulk loops. A few hundred milliseconds between sends.
- Back off on failure: wait longer each time rather than retrying at once.
- Cache aggressively. The fastest request is the one you do not make.

## If you are banned for an hour

Wait. There is no appeal and no fix, and restarting your bot does not help —
the ban is on the address.

Fix the loop before you start it again, or you will be banned again
immediately.

## Is it our IP?

Your bot has its own connection to Discord. A rate limit your bot earns is
your bot's, and it does not affect other customers.

## Still stuck?

[Open a ticket](https://shardly.xyz/app/support/new) with the log showing the
429 and what your bot was doing.
