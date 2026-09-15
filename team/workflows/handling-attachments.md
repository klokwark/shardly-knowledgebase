# Attachments

## What customers can send

Any file type, up to the size their plan allows — 8 MB on the free tier, 16 on
Pro, 32 on Shard. Up to five files per message.

Any type on purpose: the narrow allow-list we used to have rejected exactly
the files support needs — a zip of a broken bot, a heap dump, a config with an
unexpected extension — and every rejection became a ticket asking how to send
the file.

## Safety

They are stored by UploadThing and downloaded from a domain that is not ours.
Nothing on our side executes or parses them.

**A hostile file is no more dangerous than one emailed to you** — which is to
say, be sensible. Do not run an attachment. Open archives in something you
trust. If a file is obviously malware, do not open it at all; note it and tell
a manager.

## What to ask for

**Text, not screenshots**, whenever there is a choice. A screenshot of a log
cannot be searched, cannot be copied into a reply, and is usually cropped just
above the interesting line.

> Could you paste the last 50 lines of the console rather than screenshotting?
> Easier for me to search.

Screenshots are right for: the dashboard looking wrong, a Discord permission
dialog, a rendering problem.

## Files with secrets in them

Customers send `.env` files. Regularly.

When they do:

1. Tell them, in the reply, to **reset whatever was in it** — a token in a
   file sent to support is a token that has been in an email.
2. Note it internally.
3. Do not quote the values back, not in the reply and not in a note.

## Attachments you send

You can attach too. Useful for a corrected config or an annotated screenshot.

Never attach anything with another customer's data in it. Check twice before
sending a log excerpt that you have not read line by line.
