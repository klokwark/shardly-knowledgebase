# Playbook: server will not provision

**Category:** `server` · **Priority:** `high`, or `urgent` if they paid and
have nothing after an hour

## What you are looking at

They paid. The dashboard shows Queued, Building, or Setup failed.

## Check in order

**1. Is the job in the queue?**
`/app/staff/servers` → Provisioning queue. Find the key
`server.provision:<deployment id>`.

- **Not there at all** → the order never reached us. Jump to "no job" below.
- **`queued`** → it is waiting. Look at the next attempt time.
- **`dead`** → we gave up. See [dead letter](dead-letter-job.md).

**2. Is the scheduler alive?**
Same page, the Scheduler row. If a task is overdue and jobs are queued,
nothing is driving the clock — that is the real problem and it affects every
customer, not this one. Escalate immediately.

**3. Read the error.** The job row shows the last one. Common:

| Error mentions | Means |
| --- | --- |
| no space / allocation | The node is full. Engineering. |
| timeout / connection | Panel was busy. It retries. Wait. |
| egg / image | Configuration problem. Engineering. |
| account record not found | Data problem. Engineering. |

**4. Claims much higher than failures?** Workers are picking it up and
vanishing rather than failing. That is a platform problem, not this customer's
— escalate.

## No job at all

The order did not reach us.

- Ask for the Polar receipt.
- Check whether they paid with a different email address than their account.
  **This is the most common cause by a distance.**
- If the receipt is real and the account is right, escalate — an order needs
  matching up by hand.

## What to say

While it is retrying:

> Your server is still building — it retries automatically when our panel is
> busy, and it carries on whether or not you have the page open. You have
> definitely got the plan; it is the build that is slow. I am watching it and
> will let you know within the hour either way.

When it failed and you have retried it:

> Sorry about that — the build failed on our side and I have started it again.
> Your plan was never at risk. I will confirm when it is up.

## Escalate when

- The scheduler is stalled.
- The node is full.
- It has dead-lettered twice for the same reason.
- They paid over an hour ago and still have nothing.
