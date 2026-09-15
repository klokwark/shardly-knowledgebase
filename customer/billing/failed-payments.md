---
title: A payment failed
slug: failed-payments
category: billing
keywords: [payment failed, declined, card, expired, overdue, suspended, lapsed]
reviewed: 2026-09-15
---

# A payment failed

## What happens

Polar retries a failed payment on their own schedule. If it keeps failing, the
subscription lapses and we suspend the server.

**Suspended is not deleted.** Your files are still there. Pay and it comes
back.

## Fix it

**Billing → Manage billing** and update the card. Polar retries, or you can
make it retry immediately from the portal.

## Why it usually fails

- Card expired.
- Bank blocked it as an unexpected foreign charge. Polar is often billed from
  outside your country — approving it once usually teaches your bank.
- Insufficient funds at the moment they tried.
- 3-D Secure needed and nobody confirmed it.

## How long you have

Your server is suspended when the subscription lapses, and removed a while
after that. The exact window depends on how the retries fall.

**Do not rely on the gap.** If you get a failed-payment email, treat it as
the last warning — because on a small plan the window between "suspended" and
"gone" is not long.

## Make sure you hear about it

Billing notifications are on by default. If you have turned them off, this is
the class of message people most regret missing. See
[notification settings](../account/notification-settings.md).

## It failed and I have already paid

Sometimes a payment succeeds and the subscription still shows as lapsed for a
few minutes. Give it five, then open a ticket with the invoice or receipt from
Polar. We can see the order on our side and put it right.

## Still stuck?

[Open a billing ticket.](https://shardly.xyz/app/support/new) Include the
Polar receipt.
