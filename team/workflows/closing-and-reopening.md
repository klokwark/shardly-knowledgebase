# Closing and reopening

## resolved versus closed

**`resolved`** — you believe it is answered, and you are giving them room to
disagree. Most tickets end here.

**`closed`** — done. Use it when the customer confirmed, or when there is
genuinely nothing left.

## Closing well

Say what happened, say what to do if it comes back, and leave the door open.

> That was the startup file — it is pointing at `index.js` and your entry
> point is `src/bot.js`. I have set it and your bot is up.
>
> If it goes down again, reply here and it reopens — no need to start a new
> ticket.

## Do not close

- With an unanswered question still in the thread.
- Immediately after a reply. Give them a chance.
- To tidy the queue. A closed ticket that was not solved becomes a new ticket
  with an angrier opening line.
- When you are waiting on engineering. That is `in_progress`, and yours.

## Reopening

A customer replying to a resolved ticket reopens it. That is correct — one
conversation, one thread.

When one reopens: **read the whole history before replying.** Nothing is worse
for a customer than explaining it a third time to a third person.

## The same person, again, about the same thing

Look for the pattern rather than fixing it again.

- Third crash this month → not a restart problem, something is wrong.
- Third billing confusion → our billing copy is unclear.
- Third "how do I…" → missing knowledge base article.

Note it and raise it. Repeat tickets are a product signal, and the queue is
often the first place a real problem becomes visible.

## Writing the article

If two people asked this month, write it. Add it to `customer/`, and consider
whether the short version belongs in the in-product deflection list too — see
`reference/ticket-categories.md`.
