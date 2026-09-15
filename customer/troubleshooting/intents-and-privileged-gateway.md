---
title: Intents and privileged gateway
slug: intents
category: bot
keywords: [intents, disallowed intents, privileged, message content, gateway, members]
reviewed: 2026-09-15
---

# Intents and privileged gateway

## The error

```
Error [DisallowedIntents]: Privileged intent provided is not enabled or whitelisted.
```

Your code asked for an intent your application is not allowed to use. Discord
refuses the connection entirely — this is not a warning.

## The three privileged intents

| Intent | You need it to |
| --- | --- |
| **Message Content** | Read what messages say |
| **Server Members** | See members join, leave, or update |
| **Presence** | See who is online |

Everything else is unprivileged and needs no permission.

## Fixing it

Both halves have to agree:

1. **In the Discord developer portal** — your application → **Bot** → turn on
   the intents you need.
2. **In your code** — request the same ones.

```js
const client = new Client({
  intents: [
    GatewayIntentBits.Guilds,
    GatewayIntentBits.GuildMessages,
    GatewayIntentBits.MessageContent, // privileged
  ],
});
```

Enabling in the portal but not asking in code means your handlers never fire.
Asking in code without enabling means the error above. Both are common.

## Over 100 servers

Past 100 servers you must **apply** for privileged intents, with a written
justification, and wait for Discord to approve it.

Plan for that before you hit 100, not after — approval is not instant and your
bot breaks the moment you cross the line with intents you have not been
granted.

## Do you actually need Message Content?

Often not. Slash commands and interactions carry their own data and need no
privileged intent at all. Moving from prefix commands to slash commands
removes the whole problem, and Discord prefers it.

## Still stuck?

[Open a ticket](https://shardly.xyz/app/support/new) with the intents in your
code and a screenshot of the portal page.
