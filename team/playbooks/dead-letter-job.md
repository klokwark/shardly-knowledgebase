# Playbook: a job dead-lettered

**Priority:** `urgent`. Somebody has paid and has nothing.

## What you are looking at

A job gave up after five real failures. It posted into `#staff-logs`
automatically — **you do not wait for the customer to report this.**

A dead letter is not a log line. Every one is a customer in a bad state who
may not have noticed yet.

## Check in order

**1. Open the job.** `/app/staff/servers` → Provisioning queue. Dead ones sort
to the top.

**2. Read `lastError`.** That is why we stopped.

**3. What type?**

- **`server.provision`** → the customer's deployment is `failed` and they have
  been emailed. They know.
- **`order.paid`** → the order is marked `manual_refund_required`. Usually
  sold out: they paid for capacity we did not have. **They may not know
  anything is wrong.** Contact them.

**4. Is the underlying cause fixed?** A full node, an expired key, a panel
outage. Retrying into the same wall just produces another dead letter.

**5. Retry** once the cause is addressed. The button resets the counters and
runs it immediately.

## The `order.paid` case

This is the worst one, because they are out of pocket with nothing to show and
no email telling them so.

1. Find out whether capacity exists now.
2. **If yes:** retry, confirm the server builds, then write to them explaining
   what happened before they notice.
3. **If no:** refund, proactively, and tell them why. Do not wait to be asked.

> You bought a Shard plan this morning and we could not deliver it — the tier
> sold out between you paying and us building it, which should not be possible
> and is our mistake. I have refunded you in full; it will be back with you in
> a few days.
>
> If you would like the Pro tier instead I can set that up now, or I will tell
> you the moment Shard capacity is back.

## Do not

- Retry repeatedly without fixing the cause.
- Close the ticket because the retry worked, without telling the customer what
  happened.
- Assume they know. The `order.paid` case sends no email.

## Escalate when

- It is a node or panel problem.
- The same error dead-letters more than one job.
- A refund is needed — that is admin.
