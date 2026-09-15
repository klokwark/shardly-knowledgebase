# Playbook: payment failed

**Category:** `billing` · **Priority:** `normal`, `high` if suspended

## What you are looking at

A subscription lapsed. Their server is suspended, or about to be.

## Check in order

**1. Their billing state.** `/app/staff/billing`, or their account. Is the
subscription `canceled`, `revoked`, or still `active`?

**2. Is the server suspended or removed?** Suspended is recoverable — files
intact. Removed is not.

**3. Did they pay and it just has not landed?** Ask for the Polar receipt.
Sometimes a payment succeeds and the state takes minutes.

## What to say

Suspended, not yet removed:

> Your subscription did not renew — the card was declined on Tuesday — so the
> server is suspended. **Your files are all still there.** Update the card
> under Billing → Manage billing and it comes straight back.
>
> If the card is fine and the bank blocked it as an unexpected foreign charge,
> approving it once usually settles it.

Paid but still showing lapsed:

> Thanks — I can see the payment. Give it about five minutes to reach us; if
> it has not come back by then, reply here and I will sort it manually.

## Do not

- Say "your server has been deleted" unless it has. Suspended and deleted are
  very different, and getting it wrong causes real panic.
- Restore a suspended server without the payment being fixed. That is a
  billing decision and it is not yours.

## The removal window

Suspended servers are eventually removed. **If they are close to it, say so
plainly** — the kindest thing you can do is tell them there is a clock.

If they need a few days, escalate to admin. We can usually hold it.

## Repeat failures

Third failed payment in three months means something structural — a card that
keeps expiring, a bank that keeps blocking. Say so kindly and suggest monthly
billing or a different card. Do not make them work it out themselves.

## Escalate when

- Anything about a refund, credit or holding a server past its window.
- They paid and we cannot find it.
- A chargeback is mentioned — immediately, to admin.
