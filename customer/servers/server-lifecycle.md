---
title: The life of a server
slug: server-lifecycle
category: server
keywords: [status, building, queued, provisioning, active, failed, suspended]
reviewed: 2026-09-15
---

# The life of a server

The status on your dashboard describes where the server is in its life. It
does **not** say whether your bot process is running — that is the console.

## The states

| State | What it means |
| --- | --- |
| **Awaiting setup** | Paid for, not yet building. Normally a few seconds. |
| **Queued** | The build is written down and waiting for a worker. |
| **Building** | We are talking to the panel and allocating it. |
| **Active** | Built. Yours. |
| **Setup failed** | We tried several times and stopped. |
| **Expired** | The subscription lapsed. Suspended, not deleted. |

## Queued and Building

Both mean "we are making it". The difference matters to us and not to you.

It normally takes under a minute. It carries on whether or not you keep the
page open, and we email you when it is done.

## If it stays in Building

Give it five minutes. Builds retry on their own when the panel is briefly
busy, and a retry looks identical from outside.

Past that, see [server stuck
building](../troubleshooting/server-stuck-building.md).

## Setup failed

This means we genuinely stopped trying, not that one attempt failed. Our team
is told automatically when it happens — you do not have to report it.

The page shows what went wrong and a **Try again** button. Press it: a good
number of these are a node that was briefly out of room and is not any more.

**Your plan is unaffected.** You have still paid for it and still have it; it
is the build that failed.

## Expired

The subscription lapsed. The server is suspended — files intact, process
stopped. Fix the payment and it comes back. See
[a payment failed](../billing/failed-payments.md).

Suspended servers are eventually removed. Do not sit on it.

## Still stuck?

[Open a server ticket.](https://shardly.xyz/app/support/new)
