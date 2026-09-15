# Playbook: bot will not start

The most common ticket by a wide margin. Ninety percent are one of five
things.

## Your first reply, always

Ask for the log. Every time.

> Could you paste the last 50 lines from your console? That normally shows
> exactly what is stopping it, and saves us both a round trip.

Do not diagnose without it. Do not guess from a description of the error —
customers paraphrase, and the paraphrase loses the detail that matters.

## Reading the log

| Log says | Cause | Fix |
| --- | --- | --- |
| `Cannot find module '/home/container/index.js'` | Startup file wrong, or files in a wrapper folder | Set the startup file, or move contents up a level |
| `Cannot find module 'discord.js'` | No `package.json` at top level, or install failed | Check location, restart |
| `An invalid token was provided` | Token missing, wrong, or reset | Set `DISCORD_TOKEN`, reset in Discord's portal if it leaked |
| `Used disallowed intents` | Privileged intent not enabled | Developer portal → Bot → enable |
| `SyntaxError` | Their code | Point at file and line |
| Exits, no error | `client.login()` never reached | Ask them to log at the top and at login |
| `ENOSPC` | Disk full | See disk playbook |
| `heap out of memory` | Memory | See memory article |

## The wrapper folder

Worth knowing on sight. A zip of a folder extracts as `my-bot/index.js`, so
the startup file at the top level does not exist.

You can see it in their file list from the staff panel. Fixing it is moving
files up one level.

## What you can check yourself

With `server: ["read"]` you can see their server and its live state. Use it —
"I can see your server is up but the process is stopped" saves a round trip.

You **cannot** restart it without manager. If a restart is all it needs, ask a
manager rather than talking the customer through it — it is faster and less
error-prone.

## When it is their code

Say so kindly, and help anyway.

> That is a syntax error in `commands/ban.js` on line 40 — a missing closing
> brace. Not a hosting problem, but here is the line…

We are not obliged to debug their bot. We generally do anyway when it is quick,
because it takes five minutes and buys a lot of goodwill. Draw the line at
writing features for them.

## Escalate when

- The log shows a platform error, not their code.
- The server will not start and the panel reports something odd.
- You have been round twice and it is not converging.
