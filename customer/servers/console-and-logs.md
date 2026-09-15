---
title: Console and logs
slug: console-and-logs
category: server
keywords: [console, logs, output, stdout, command, start, stop, restart, kill]
reviewed: 2026-09-15
---

# Console and logs

The console is your bot's standard output, live, plus the buttons that control
the process.

## The buttons

- **Start** — begin the process.
- **Stop** — ask it to stop politely. It gets a chance to close connections.
- **Restart** — stop then start. What you want after changing a file.
- **Kill** — stop it now, without asking. For a process that has hung.

Prefer Stop to Kill. Kill does not let your bot finish what it is doing.

## Sending a command

The input at the bottom writes to your process's stdin. Useful if your bot
reads commands there; useless if it does not.

## Reading the log

Everything your bot writes with `console.log` shows up here, as it happens,
plus what the runtime says when it starts and stops.

The most useful reflex in all of bot hosting: **when something is wrong, read
the last twenty lines of the log before doing anything else.** The answer is
in there far more often than not.

## The log does not go back forever

The console shows recent output. It is not a searchable archive — if you close
the tab, earlier output is gone.

If you need a real history, write your own log file to disk and read it in the
file manager. Longer retention and search are on our list but are not built
today.

## "Running" versus your plan status

The console shows whether the **process** is running. The dashboard status
shows where the **server** is in its life.

A server that is Active with a stopped process is completely normal — it means
your bot is not running and you should press Start.

## Still stuck?

Open a ticket **with the last 50 lines of the log pasted in**. It is the
single thing that most speeds up an answer.
