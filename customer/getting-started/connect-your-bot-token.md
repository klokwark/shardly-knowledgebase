---
title: Set your bot token
slug: connect-your-bot-token
category: bot
keywords: [token, discord_token, invalid token, credentials, secret]
reviewed: 2026-09-15
---

# Set your bot token

Your token is the password to your bot. Treat it like one.

## Where it goes

**Bot settings → Variables → `DISCORD_TOKEN`**.

Not in your code. Not in a `.env` you commit. Not in a Discord message where
somebody can screenshot it.

## Where to get one

1. Open the [Discord developer portal](https://discord.com/developers/applications).
2. Pick your application, then **Bot**.
3. **Reset Token**, then copy the new one immediately — it is shown once.

Resetting invalidates the old token. Anything still using it stops working,
which is the point if you are resetting because it leaked.

## Intents

If your bot reads message content, sees members join, or tracks presence, you
must enable the matching **privileged gateway intent** in the same developer
portal page — and request it in your code.

A mismatch between the two is the single most common reason a bot connects
and then immediately exits. See
[intents and privileged gateway](../troubleshooting/intents-and-privileged-gateway.md).

## If your token leaked

1. Reset it in the developer portal. Now, before anything else.
2. Set the new one in Bot settings.
3. Restart your server.
4. If it was in a Git repository, understand that removing the commit does
   not help — the token is compromised from the moment it is pushed. The reset
   is the fix; nothing else is.

## Does Shardly see my token?

It is stored so we can start your process with it, the same way any host must.
It is not shown in the dashboard after you save it, it is not in your data
export, and support cannot read it back to you — if you have lost it, reset
it.

## Still stuck?

Open a ticket. Do not paste your token into it. Say what the log line says
instead.
