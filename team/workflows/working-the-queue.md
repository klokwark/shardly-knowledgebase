# Working the queue

## Where to start

The queue is ordered for you. Priority dominates, age is added so nothing
starves, and anything past its SLA jumps to the top.

Work from the top. You do not have to be religious about it — if you are
already deep in a Discord.js problem and another one appears, take it — but
the top is where the system thinks the damage is.

## The statuses

| Status | Means | Clock |
| --- | --- | --- |
| `open` | Nobody has picked it up | running |
| `in_progress` | You are on it | running |
| `waiting` | Ball is with the customer | **stopped** |
| `resolved` | Answered, not yet confirmed | stopped |
| `closed` | Done | stopped |

## `waiting` is not a dumping ground

Use it when the ball is genuinely with the customer: you asked for a log, you
asked them to try something, you need a decision only they can make.

Do not use it because you do not know the answer yet. That is still your
ticket, and moving it to `waiting` to clean up your view is how a ticket gets
lost for a week.

The clock stops on `waiting`, which is exactly why it must be honest. A ticket
sitting in somebody's inbox is not a queue we are failing to work — but a
ticket you parked is.

## One ticket, one owner

Assign it to yourself when you start. Half-answered tickets with no owner are
how two people reply to the same person with different answers.

## Internal notes

Use them generously. What you tried, what you ruled out, what you suspect.

The customer cannot see them. The next person can — and often the next person
is you, three weeks later, with no memory of any of it.

## Before you close

- Did you answer the question they asked, or the question you found
  interesting?
- Is there a second question further down their message you skipped?
- Would this ticket have been shorter if you had asked for the log first?
- Should this have a knowledge base article? If two people have asked this
  month, yes.

## A ticket you cannot finish today

Say so. "I have not forgotten this, I am waiting on X, I will come back to you
Tuesday" costs a minute and buys enormous goodwill.

Silence is the thing customers complain about, far more often than slowness.

## The queue looks bad

Tell a manager rather than working faster and worse. A backlog is a staffing
problem, not a personal failing, and rushed replies generate more tickets than
they close.
