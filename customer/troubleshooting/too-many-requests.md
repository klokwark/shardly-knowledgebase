---
title: Too many requests (429)
slug: too-many-requests
category: other
keywords: [429, rate limit, too many requests, slow down, retry after, throttled]
reviewed: 2026-09-15
---

# Too many requests (429)

Shardly limits how often one account can call its API. Past the limit you get
a 429 and a message saying what the limit was and when to come back.

**This is about calls to Shardly**, not to Discord. For that, see
[rate limited by Discord](rate-limited-by-discord.md).

## The allowances

They scale with the plan, and reads and writes are counted separately. Reads
are generous; writes — anything that changes something, provisions, or reaches
the panel — cost more.

You will not reach them using the dashboard normally. People reach them with a
script in a loop.

## What to do

**Wait.** The window is a minute, and the response tells you how long is left.

**Then find the loop.** A 429 from a browser tab is nearly always something
polling far faster than it needs to.

## Specific limits with their own messages

- **GitHub imports** are rationed per half hour, because each one unpacks an
  archive on a real machine.
- **Sign-in links** are limited per email address per hour.
- **Attachment size and count** depend on the plan.

Each refusal names the limit it hit rather than just saying no.

## Need it raised?

Open a ticket and say what you are doing. We can raise a specific limit on
your account — it does not require moving up a tier, and if your use is
legitimate we would rather raise it than have you work around it.

## Still stuck?

[Open a ticket](https://shardly.xyz/app/support/new) with the exact message,
which names the limit.
