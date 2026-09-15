---
title: Is the platform down?
slug: platform-status
category: other
keywords: [status, down, outage, uptime, incident, maintenance, offline]
reviewed: 2026-09-15
---

# Is the platform down?

## Where to look, in order

1. **[Our Discord](https://discord.gg/shardly).** This is the real answer.
   Incidents are announced there first, and you can see whether other people
   are having the same problem right now.
2. **[shardly.xyz/api/health](https://shardly.xyz/api/health).** A plain
   machine-readable check. `"status": "alive"` and HTTP 200 means the platform
   is answering.
3. **[The status page](https://shardly.xyz/status).** Honest warning: it does
   not yet have a live feed behind it. It is being built. Until then it will
   tell you it could not load rather than pretend — use Discord.

## Is it me or you?

**Probably you** — and that is not a criticism, it is just the arithmetic.
Most "is Shardly down" questions turn out to be one bot, and the console log
says why.

**Probably us** if:

- The dashboard itself will not load.
- Several of your servers stopped at the same moment.
- Other people in Discord are saying the same thing in the last few minutes.

## During an incident

We post in Discord when we know, again when we understand it, and again when
it is fixed. We would rather post "we are looking at it" early than a polished
explanation an hour later.

You do not need to open a ticket during a known incident — though you are
welcome to, and it does not slow anything down.

## Maintenance

Announced in advance in Discord and by announcement notification, unless it is
a security fix that cannot wait.

## The uptime figure on the site

The landing page quotes an uptime number. Be aware that we do not yet have
automated uptime measurement behind it — building that is on our list. Until
it exists, treat the figure as a statement of intent rather than a measured
SLA, and hold us to the Discord record of actual incidents.

## Still stuck?

[Open a ticket.](https://shardly.xyz/app/support/new) Or ask in Discord, which
during an incident is faster.
