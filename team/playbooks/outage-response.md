# Playbook: outage

## Is it actually us?

**1. [shardly.xyz/api/health](https://shardly.xyz/api/health).** 200 and
`"alive"` means the platform is answering. 503 means it is not, and the body
says which check failed.

**2. The staff channel.** Has the hourly health line stopped? Are dead letters
pouring in?

**3. The queue.** Several unrelated customers in a few minutes is an
incident. **Two is a coincidence, three is an incident.**

**4. The staff servers page.** Scheduler row overdue with work queued means
nothing is driving the clock.

## If it is us

**Tell people before you understand it.** "We are looking at it" at 14:02
beats a polished explanation at 15:30.

Post in Discord. Short, honest, no jargon:

> We are aware that the dashboard is not loading for some people and are
> looking into it now. Bots that are already running are not affected. Next
> update in 15 minutes.

Say what is **not** affected if you know — it halves the incoming volume.

## While it runs

- Update on the interval you promised, even to say there is nothing new. A
  missed update is worse than a boring one.
- Do not speculate about the cause publicly.
- Do not give an ETA you are not sure of. "We do not have an ETA yet" is
  better than a wrong one.

## In the queue

Tickets will arrive about the same thing. You do not need a different answer
for each:

> This is a platform-wide problem we are working on right now — it is not
> anything on your side. Updates are going into our Discord as we have them,
> and I will reply here when it is resolved.

Tag them so you can find them all afterwards.

## When it is fixed

Post it. Then **go back to every ticket** and close it individually. A
customer who opened a ticket deserves a reply, not a link to a channel.

## Afterwards

Somebody writes what happened, honestly. Not for the customers necessarily —
for us. What broke, what we noticed, how long each step took, what would have
made it shorter.

The most useful question is usually: **did we find out from monitoring or from
a customer?** If it was a customer, that is the thing to fix.

## Not us

If health is green and it is one customer, it is their bot. Be kind about it —
they were not unreasonable to ask — and move to normal troubleshooting.

> Everything is green on our side and I am not seeing this from anyone else,
> so let us look at your bot specifically. Could you paste the last 50 lines
> of your console?
