---
title: Deploy your first bot
slug: deploy-your-first-bot
category: bot
keywords: [deploy, first bot, setup, getting started, upload, start]
reviewed: 2026-09-15
---

# Deploy your first bot

From a paid plan to a running bot. About five minutes.

## 1. Let the server build

After checkout the server builds itself. You will see **Queued** and then
**Building** on the dashboard. It normally takes under a minute.

You can close the tab. The build carries on without you and we email you when
it is ready.

## 2. Get your code onto it

Three ways, pick one:

- **Drag and drop.** Open **Files** and drop a folder or a zip in.
- **Import from GitHub.** Open **Bot settings → Import from GitHub**, connect
  your account, pick the repository. See
  [importing from GitHub](../servers/github-import.md).
- **Write it here.** Create files directly in the editor. Fine for a small
  bot, painful for a large one.

Whichever you choose, the server needs your entry point and your
`package.json` at the top level — not inside a nested folder.

## 3. Set your token

Your bot token goes in **Bot settings**, as `DISCORD_TOKEN`. Not in your code,
and never in a file you commit.

If you have ever pushed a token to a public repository, Discord has already
invalidated it. Generate a new one in the Discord developer portal.

## 4. Check the startup file

**Bot settings → Startup file** is the file we run. It defaults to `index.js`.
If your entry point is `src/main.js`, say so here.

## 5. Start it

Press **Start** on the console. Watch the log.

A healthy start looks like npm installing your dependencies, then your own
"logged in as…" line. If it does not get that far, the log says why — and
[bot won't start](../troubleshooting/bot-wont-start.md) covers the usual
causes.

## What now?

- [Console and logs](../servers/console-and-logs.md)
- [Sharding](../servers/sharding.md)
- [Backups](../servers/backups.md)

## Still stuck?

Open a ticket with the last 50 lines of your console log pasted in. That one
detail is usually the difference between an answer in an hour and three
messages of back and forth.
