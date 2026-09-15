---
title: Passkeys
slug: passkeys
category: account
keywords: [passkey, webauthn, fingerprint, face id, security key, yubikey]
reviewed: 2026-09-15
---

# Passkeys

A passkey signs you in with whatever unlocks your device — a fingerprint, your
face, a PIN, or a hardware key. There is no password to remember, and nothing
that can be phished.

## Add one

**Account → Security → Passkeys → Add.**

Your browser takes over from there and asks how you want to store it. Say yes.

## Use one

On the sign-in page, choose the passkey option. Your device asks you to
confirm. That is the whole flow.

## Worth knowing

- **A passkey is tied to where you stored it.** One saved in your phone's
  keychain syncs to your other devices signed into that account; one saved on
  a hardware key lives on that key.
- **Add more than one** if you can — a second passkey, or keep a password as
  well. A passkey on a single lost phone is a locked door.
- **We never see it.** The private half never leaves your device. We store a
  public key, which is useless to anybody who steals it.

## Removing one

From the same screen. Do it when you lose a device — and
[revoke its sessions](sessions-and-devices.md) at the same time, because
removing the passkey does not sign out a session it already created.

## Still stuck?

Passkey support varies by browser and operating system. If **Add** does nothing,
try a different browser before opening a ticket, and say which one failed.
