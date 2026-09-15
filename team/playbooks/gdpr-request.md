# Playbook: GDPR request

**Category:** `account` · **Priority:** `high` · Legal deadline: **one
month**.

## The four we get

| Request | Self-service? | What to do |
| --- | --- | --- |
| **Access** — "what do you have on me" | Yes | Point at the export |
| **Portability** — "give it to me in a usable format" | Yes | Same export, it is JSON |
| **Erasure** — "delete me" | Yes | Point at account deletion, with the warning |
| **Rectification** — "this is wrong" | Mostly | Dashboard, or by ticket |

Most of this is self-service, which is the best outcome for everybody.

## Access and portability

> You can do this yourself right now: **Account → Data → Export data**. It
> gives you everything we hold — profile, servers, tickets — as a JSON file.
> Your activity log exports separately as CSV from Account → Security.
>
> If you need it in a different format or certified for a legal process, tell
> me what it has to look like and I will sort it.

## Erasure

Point them at it, and **make sure they understand it is immediate**.

> **Account → Data → Delete account**, and it asks for a code from your email.
>
> Please read this part first: there is no grace period. Your servers and
> every file on them go at once, and we cannot undo it. Download anything you
> want to keep first.
>
> Two things survive because the law requires it: invoices for ten years, and
> your support tickets with your name and email removed.

If they have an active subscription with time left, flag it before they press
it — afterwards there is no account to discuss a refund against.

## When they cannot do it themselves

Locked out, or asking on behalf of somebody. Verify identity first — see
[account recovery](account-recovery.md). **A deletion request from somebody
who cannot prove they own the account is an attack, not a right.**

## Data processing agreement

If their bot handles their users' data, they are the controller and we are
their processor.

Escalate to admin. Get: who the counterparty is, what their compliance team
requires, and by when.

## Record it

Note what was asked, when, what you verified, what you did, and when. The one
month is a legal deadline and the note is the evidence we met it.

## Escalate when

- A DPA or contract is involved.
- A supervisory authority is mentioned.
- They are asking about someone else's data.
- It is not obvious which right they are exercising — ask them, then escalate
  if still unclear.
