---
title: Startup file and variables
slug: startup-file-and-variables
category: bot
keywords: [startup, entry point, index.js, variables, environment, env, config]
reviewed: 2026-09-15
---

# Startup file and variables

Both live under **Bot settings**.

## Startup file

The file we run. It defaults to `index.js`.

If your entry point is `src/main.js` or `bot.mjs`, put that here — the whole
path from the top level of your server, and it must end in `.js`, `.mjs` or
`.cjs`.

Change it and restart for it to take effect.

## Variables

Key and value pairs handed to your process as environment variables. Read them
with `process.env.NAME`.

This is where your token goes:

```
DISCORD_TOKEN=...
```

And anything else you would otherwise be tempted to hardcode — an API key, a
database URL, a guild id for testing.

### Why not a `.env` file?

Because a `.env` file sits on the disk, gets copied into backups, and ends up
committed by accident. A variable set here is handed to the process and is not
in your code.

If your code already uses `dotenv`, it will happily read these too —
`process.env` is `process.env` either way.

### What you can set

The runtime exposes a fixed set of variables it understands, plus your own.
The panel refuses a variable the runtime has not marked as editable, which is
a guard rather than an inconvenience — it stops a typo breaking the way your
server starts.

## Changes need a restart

Neither takes effect until the process restarts. Change, then restart from the
console.

## Still stuck?

[Open a server ticket.](https://shardly.xyz/app/support/new)
