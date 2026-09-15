---
title: My bot keeps crashing
slug: bot-keeps-crashing
category: bot
keywords: [crash, restart loop, keeps restarting, unhandled rejection, exits]
reviewed: 2026-09-15
---

# My bot keeps crashing

It starts, runs for a while, dies, starts again. We restart it because that is
what you are paying for — but a restart loop is a symptom, not a fix.

## Find the last words

Scroll up in the console to just before the restart. The last thing printed
before the death is the cause; everything after is the recovery.

## `UnhandledPromiseRejection`

An `async` call rejected and nothing caught it. Node kills the process.

Fix the specific one. As a safety net while you find it:

```js
process.on("unhandledRejection", (error) => {
  console.error("Unhandled rejection:", error);
});
```

That turns a crash into a log line. It is a net, not a repair.

## Out of memory

`JavaScript heap out of memory`, or a death with no error at all.
See [out of memory](out-of-memory.md).

## Crashes on a schedule

Every hour, every night, always at the same time? Something you run on a
timer. A cron-like job, a daily reset, a cache sweep.

Narrow it by logging at the start and end of each scheduled task.

## Crashes when a particular thing happens

A specific command, a particular server, a certain kind of message. Add
logging around the handler, then reproduce it deliberately.

## Crashes after a deploy

The change you just made. Restore a [backup](../servers/backups.md) or check
out the previous commit and confirm the crash goes away — that tells you
whether you are looking in the right place.

## It was fine for months

Something outside your code moved: a dependency you do not pin, a Discord API
change, a data set that grew past a threshold.

`npm ci` with a committed lockfile removes the first of those as a variable.

## Still stuck?

[Open a ticket](https://shardly.xyz/app/support/new) with the log from before
the crash and roughly how often it happens. "Every 20 minutes" and "twice a
week" lead to very different answers.
