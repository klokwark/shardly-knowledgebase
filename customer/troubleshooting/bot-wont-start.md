---
title: My bot will not start
slug: server-wont-start
category: bot
keywords: [wont start, not starting, exits immediately, cannot find module, crash on boot]
reviewed: 2026-09-15
---

# My bot will not start

Press Start, watch the console, and read the error. Then find it below.

## `Cannot find module '/home/container/index.js'`

The startup file does not exist at that path.

- Your entry point is somewhere else — set it in **Bot settings → Startup
  file**.
- Or your upload created a wrapper folder, so everything is in `my-bot/`
  rather than at the top. Move the contents up a level in the file manager.

## `Cannot find module 'discord.js'`

Dependencies are not installed.

- Is `package.json` at the top level?
- Is `discord.js` actually in its `dependencies`?
- Restart — installation runs at start.

If installation is failing rather than being skipped, see
[dependencies will not install](dependency-install-fails.md).

## `An invalid token was provided`

Set `DISCORD_TOKEN` in **Bot settings → Variables**, and make sure it is
current. A token that has ever been pushed to a public repository is dead —
reset it in the Discord developer portal.

See [set your bot token](../getting-started/connect-your-bot-token.md).

## `Used disallowed intents`

Your code asks for a privileged intent your application has not been granted.
See [intents](intents-and-privileged-gateway.md).

## `SyntaxError` / `Unexpected token`

A syntax error in your code, with the file and line in the message.

Very common: mixing `import` and `require`. If your `package.json` has
`"type": "module"`, use `import` everywhere.

## `EADDRINUSE`

Something in your code is binding a port that is taken. Bots rarely need to
listen at all — if this is an Express server you added for a dashboard, check
what port it wants.

## It starts and exits with no error

Your process finished. Node exits when it has nothing left to do.

Usually means `client.login()` was never reached — an early `return`, a
promise that rejected silently, or a config check that quietly gave up. Add a
`console.log` at the top and at the login call and see which prints.

## Nothing above matches

[Open a ticket](https://shardly.xyz/app/support/new) with **the last 50 lines
of the console**. Not a description of the error — the actual text.
