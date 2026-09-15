# How the support system actually works

Enough of the machinery to answer confidently when something behaves oddly.

## A ticket

Lives in `supportTickets`. Has a **number** (short, sequential, what customers
quote), a category, a priority, a status, and a list of messages.

Messages can be **internal notes** — those never leave the staff endpoint and
the customer cannot see them. They are not secret from a subpoena, but they
are invisible in the UI.

## Triage

When a ticket is opened, a rule engine guesses the category and priority from
the subject, the body, and the account's state.

It is a transparent rule engine, not a model. Every reason it produces is
stored on the ticket and shown to you, and you can override both in one click.
A wrong guess costs a reordering, never a lost ticket.

## Queue order

Priority dominates, but age is added so a low-priority ticket cannot starve
behind a steady trickle of urgent ones. Anything past its SLA jumps the queue
outright.

You do not have to work strictly top-down, but the top is where the system
thinks the damage is.

## The reply email delay

When you reply, **no email is sent immediately**.

The ticket gets `notifyAfter` fifteen minutes out. A sweep runs later and, if
the customer still has not read it, sends the email. If they were on the page
and read it, no email is ever sent.

This is why a customer sometimes says "I didn't get an email" — they read it
in the browser, which is the system working.

## What drives the clock

Nothing on the web side runs on its own; it is serverless, frozen between
requests. Three things drive scheduled work:

1. **The Discord bot**, pinging hourly.
2. **The daily platform cron.**
3. **Ordinary traffic.** Every request to `/api/support/*` kicks the task
   runner in the background.

So on a busy day things happen promptly, and on a dead night they happen on
the hour. If notifications seem slow at 4am, that is why and it is expected.

Staff can see when each task last ran on `/app/staff/servers`.

## Notifications

One dispatcher. Per-type, per-channel preferences. Email is on by default;
Discord DM requires the customer to connect the **notification** Discord app,
which is separate from signing in with Discord.

Discord DMs are queued, not sent directly — the bot collects and delivers
them. So "sent" on our side means "handed to the bot".

## Attachments

Uploaded straight to UploadThing from the browser; we never see the bytes. We
store a key, and the message endpoint only trusts keys it can find in a row
owned by the account posting.

Anything under 8 MB on the free tier, more on paid plans. Any file type — the
narrow allow-list we used to have rejected exactly the files support needed.

## Provisioning

Buying does not build a server inside the payment request. The webhook records
the order and queues a job; a worker builds it, retries with backoff, and dead-
letters after five real failures.

Dead letters post into the staff Discord channel automatically. **Nobody has
to notice and report them** — see `playbooks/dead-letter-job.md`.

## The audit log

Everything consequential is written to `auditLog`, including everything you
do to a customer's account, with your name on it.

**The customer can read it.** Assume they will.
