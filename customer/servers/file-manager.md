---
title: File manager
slug: file-manager
category: server
keywords: [files, upload, editor, download, delete, rename, folder, zip]
reviewed: 2026-09-15
---

# File manager

Your server's disk, in the browser. Upload, edit, rename, delete, download.

## Getting code in

- **Drag and drop** files or a folder onto the file list.
- **Upload a zip** and decompress it there.
- **Import from GitHub** — see [that article](github-import.md).

Your entry point and `package.json` must be at the **top level**, not inside a
wrapper folder. A zip of a folder usually extracts as `my-bot/index.js`, which
will not start — move the contents up a level.

## Editing

Click a file. It opens in a real editor with syntax highlighting. Save with
the button or Ctrl/Cmd+S.

**Saving does not restart your bot.** Restart from the console when you are
ready.

## Downloading

Any file, from its row. Whole folders are not downloadable in one click today
— zip it on the server first, then download the zip.

## Deleting

Immediate, and there is no recycle bin. A [backup](backups.md) is the only
undo, so take one before a big change.

## Files you should not commit

`.env`, tokens, keys. Set secrets in **Bot settings → Variables** instead, so
they are not in the repository you are about to push somewhere.

## Size limits

The editor opens text files. A very large file may refuse to open in the
browser — that is the browser, not a limit we set. Split it, or read it from
the console instead.

## Still stuck?

[Open a server ticket.](https://shardly.xyz/app/support/new)
