---
title: Resource limits
slug: resource-limits
category: server
keywords: [memory, ram, cpu, disk, storage, limit, out of memory, oom, full]
reviewed: 2026-09-15
---

# Resource limits

## What your plan gives you

| | Starter | Pro | Shard |
| --- | --- | --- | --- |
| Memory | 512 MB | 2 GB | 8 GB |
| CPU | shared vCPU | 1 dedicated core | 2 dedicated cores |
| Disk | 5 GB | 20 GB | 80 GB |

These are real. We do not oversell — a dedicated core is a core.

## Memory

Your process is killed if it exceeds its memory. In the log this looks like a
sudden death with no error from your own code, often
`JavaScript heap out of memory`.

Common causes, in the order we actually find them:

1. **A cache that only grows.** A `Map` you add to and never remove from.
2. **Too many shards for the plan.** Each shard is a full copy in memory.
3. **A large file read into memory** instead of streamed.
4. **Genuinely outgrowing the plan.** Fine — move up a tier.

See [out of memory](../troubleshooting/out-of-memory.md).

## CPU

Shared on Starter, which means you share it with other tenants and a busy
neighbour can be felt. Pro and Shard give you dedicated cores.

Sustained 100% CPU is nearly always a loop that should be awaiting something.

## Disk

Fills up faster than people expect. Usual suspects:

- Log files written and never rotated.
- Downloaded media that is never cleaned up.
- Old backups **on** the server.
- `node_modules` from several abandoned experiments.

See [disk full](../troubleshooting/disk-full.md).

## API limits

The dashboard and any tooling you point at us are rate limited per account.
The allowance scales with the plan, and a refusal tells you what the limit was
and when to try again.

You will not hit it by using the dashboard normally. You can hit it with a
script in a loop.

## Need more?

Move up a tier, or open a ticket. If your case is unusual — a lot of disk but
little memory, say — we can sometimes raise a specific limit on your account
rather than sell you a tier you do not need.

## Still stuck?

[Open a server ticket.](https://shardly.xyz/app/support/new)
