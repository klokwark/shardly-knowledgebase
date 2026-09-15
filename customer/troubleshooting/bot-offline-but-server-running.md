---
title: The server is running but my bot is offline
slug: bot-offline-but-server-running
category: bot
keywords: [offline, not responding, shows offline, connected but offline, presence]
reviewed: 2026-09-15
---

# The server is running but my bot shows offline

The console says running. Discord says offline. Both can be true.

## Is it actually logged in?

Look for your own "logged in as…" line in the console. If it is not there,
your process is alive but never connected — which is a
[will not start](bot-wont-start.md) problem wearing a different hat.

## Is it connected but idle?

Discord shows a bot as offline when the gateway connection is gone even if the
process lives on. Look for reconnect messages or `disconnected` in the log.

Discord.js reconnects on its own. Constant reconnecting usually means an
intent problem, a token used in two places at once, or a network issue at
their end.

## Two copies of the same bot

Running the same token locally and on Shardly at the same time makes them
fight. Each login kicks the other off, and both look unstable.

Use separate applications and tokens for development.

## Presence not set

If your bot works — commands respond — but shows offline or has no status, it
may simply never set a presence. That is cosmetic. `client.user.setPresence()`
fixes it.

## It responds to some servers but not others

Not a hosting problem. Check permissions in the server it ignores, and whether
commands were registered globally or per-guild. Global slash commands can take
up to an hour to appear.

## Check the platform

If several things are strange at once, look at
[the status page](../policies/uptime-and-status.md) and our Discord.

## Still stuck?

[Open a ticket](https://shardly.xyz/app/support/new) with the console output
around a reconnect, and say whether commands work.
