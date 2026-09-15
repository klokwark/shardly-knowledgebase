# SLA and escalation

## The targets

| Priority | First response |
| --- | --- |
| urgent | 2 hours |
| high | 6 hours |
| normal | 24 hours |
| low | 48 hours |

First response, not resolution. The clock stops on `waiting`, `resolved` and
`closed`.

## A ticket approaching its SLA

**Answer it, even if you do not have the answer.**

> Sorry for the wait. I am on this — I need to look at your server's logs
> before I can say what is happening, and I will come back to you within the
> next two hours.

That meets the SLA honestly. What does not meet it is a holding reply with no
content and no commitment, sent purely to stop a counter going red.

## A ticket past its SLA

It jumps the queue automatically. Take it next.

If it has been sitting because nobody knew the answer, that is an escalation,
not a waiting game. See below.

## When to escalate to a manager

- You need a permission you do not have — restart, suspend, billing.
- The customer is asking for a refund or a credit.
- The customer is threatening a chargeback or legal action.
- You have replied twice and it is not getting better.
- You are about to say something you are not fully sure about to an angry
  customer.

## When to escalate to engineering

- The dashboard or API is behaving wrongly in a way you can reproduce.
- A provisioning job has dead-lettered for a reason that is not obviously a
  one-off.
- Data looks wrong — a plan that says one thing and behaves as another.
- Several customers report the same thing in a short window. **Two is a
  coincidence, three is an incident.**

**How:** internal note on the ticket with what you have established, then flag
it in the staff channel with the ticket number. Do not just reassign it and
walk away — the note is what stops the next person starting from nothing.

## What to tell the customer when you escalate

That you have, and roughly when you will come back.

> I have passed this to our engineers with everything you have sent. I will
> update you by tomorrow afternoon either way, even if the answer is that we
> are still looking.

Never "it has been escalated" with no name, no timeframe and no follow-up.
That is the sentence customers hate most in all of support.

## Then actually follow up

Put it in `waiting` only if the ball is with them. If the ball is with
engineering, it is still `in_progress` and still yours to chase.
