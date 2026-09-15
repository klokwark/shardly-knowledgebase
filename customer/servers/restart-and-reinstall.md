---
title: Restart and reinstall
slug: restart-and-reinstall
category: server
keywords: [restart, reinstall, wipe, reset, fresh, rebuild, destructive]
reviewed: 2026-09-15
---

# Restart and reinstall

Two very different buttons.

## Restart

Stops your process and starts it again. Your files are untouched.

This is what you want after changing a file, a variable, or the startup file.
It takes seconds.

## Reinstall

**Wipes the disk and rebuilds the server from scratch.** Your files are gone.
Your code is gone. Everything you uploaded is gone.

It exists for a server whose state has become genuinely unrecoverable — a
broken dependency tree that will not resolve, a disk full of something you
cannot identify, a half-finished migration.

### It asks for a code

Because it is destructive, a reinstall sends a six-digit code to your email
address and will not run without it. A stray click cannot wipe your server,
and neither can somebody sitting at your unlocked laptop.

### Before you reinstall

1. **Take a backup**, and download it.
2. Or at least download your source.
3. Make sure your code is in GitHub, if it should be.

Then reinstall, then put the code back.

## Which do I need?

Almost always **restart**.

Reinstall is right maybe once a year. If you are considering it because your
bot will not start, open a ticket first — that is usually a five-line fix and
a reinstall will not touch the cause.

## Still stuck?

[Open a server ticket.](https://shardly.xyz/app/support/new)
