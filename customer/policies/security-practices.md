---
title: How we handle security
slug: security-practices
category: security
keywords: [security, report vulnerability, disclosure, encryption, practices]
reviewed: 2026-09-15
---

# How we handle security

## Reporting something

Found a vulnerability? **security@shardly.xyz**, or a ticket in the security
category.

Tell us what you found, how to reproduce it, and what you could reach. We will
confirm we have it, tell you what we found, and tell you when it is fixed.

**We will not be difficult about it.** Nobody has ever been in trouble with us
for reporting a bug in good faith.

Please do: test only against your own account, stop as soon as you have proved
the point, and give us time before going public.

Please do not: access other people's data, degrade the service for others, or
run automated scanners against production — they are indistinguishable from an
attack and we will block them.

## What we do

- **Passwords** are hashed, never stored as text. Support cannot read yours.
- **Two-factor authentication** and **passkeys** are available on every
  account, free.
- **Sessions are visible and revocable** by you, from
  [Account → Security](../account/sessions-and-devices.md).
- **Changing a password ends every other session.**
- **Destructive actions need a fresh code** emailed to you — reinstalls,
  deletions, exports. A stray click cannot wipe your server.
- **Everything consequential is logged**, including what our staff do to your
  account, and you can read it.
- **Rate limits** on every API route, by account and by address.
- **Data stays in the EU.**

## What we ask of you

- Turn on two-factor authentication.
- Do not put your token in your code.
- Do not reuse the password you use everywhere else.
- Check [where you are signed in](../account/sessions-and-devices.md)
  occasionally.

## Staff access

Our staff can see your servers and act on them — that is what makes support
possible. Every one of those actions is written to your activity log with
their name on it, and you can read it.

## Still stuck?

**security@shardly.xyz**, or a security ticket. Security tickets are worked
ahead of everything else.
