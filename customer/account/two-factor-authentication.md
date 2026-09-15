---
title: Two-factor authentication
slug: two-factor-authentication
category: security
keywords: [2fa, two factor, totp, authenticator, backup codes, mfa]
reviewed: 2026-09-15
---

# Two-factor authentication

A code from your phone on top of your password. If somebody else learns your
password, it is not enough.

## Turn it on

1. **Account → Security → Two-factor authentication → Set up.**
2. Enter your current password if your account has one.
3. Scan the QR code with any authenticator app — Google Authenticator,
   1Password, Bitwarden, Aegis. Any of them.
4. Type the six digits it shows.

You can also copy the secret by hand if you cannot scan.

## Backup codes

You are shown a set of backup codes **once**, at setup. Each works one time.

Save them somewhere that is not the phone holding the authenticator. A
password manager, or printed and in a drawer. Losing your phone with no backup
codes is the situation they exist for, and it is not a nice one.

## Signing in afterwards

Password first, then the six digits. If the code is refused, check your
phone's clock is set automatically — TOTP is time-based and a phone a minute
out will fail every attempt.

## Lost your phone and your codes

Open a ticket. We will ask you to prove the account is yours, and what counts
as proof depends on what is on the account — recent invoices, the server id,
the address on file.

It is deliberately not instant. An account recovery that support can do
quickly on the strength of a convincing message is a vulnerability, not a
feature.

## Does a reset get around it?

No. Resetting your password ends every session, so the new password has to be
used at a normal sign-in — where the second factor is asked for. That is on
purpose.

## Still stuck?

[Open a security ticket.](https://shardly.xyz/app/support/new)
