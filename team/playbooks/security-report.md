# Playbook: security report

**Category:** `security` · **Priority:** `urgent` · Ahead of everything else.

## Somebody has reported a vulnerability

## First, within the hour

Acknowledge. Even with nothing else to say.

> Thank you — we have got this and we are looking at it now. I will come back
> to you today with what we have found.

Researchers who get silence go public. Researchers who get a fast human reply
almost never do.

## Be grateful, and mean it

They did us a favour. Nobody is ever in trouble with us for reporting in good
faith, even if they poked further than we would have liked.

**Do not** lead with whether they breached the terms. **Do not** threaten. It
turns a free security audit into a public incident and a reputation we would
deserve.

## Gather

- What they found, and how to reproduce it.
- What they could reach. Their own data, or someone else's?
- When they found it.
- Whether they have told anybody else, or intend to.
- Whether they want credit.

## Escalate immediately

Staff channel, now, not after you have written a nice reply. Then the note.

## While it is open

- **Do not confirm or deny specifics publicly.**
- **Do not discuss it in customer-facing channels.**
- Keep the reporter updated even when there is no news. "Still working on it"
  on Thursday is worth a great deal.

## If customer data was reached

That is a possible breach. Admin, immediately. There are notification
obligations with **72-hour** deadlines under GDPR, and the clock starts when
we become aware — which is now.

Do not decide by yourself whether it counts.

## Closing it out

Tell them what we found, what we changed, and when it shipped. Offer credit if
they want it.

> Fixed and deployed this morning. You were right that the check was missing;
> it now verifies ownership before returning the record. Thank you for
> reporting it properly — happy to credit you publicly if you would like.

## Not a vulnerability

Sometimes it is not. Say so kindly and explain why — they have usually put
real effort in.

> Thanks for looking at this. That endpoint does return the data, but only for
> the account holding the session, so a signed-in user seeing their own
> information is expected. If you can get it to return somebody else's, that
> is very much a bug and I want to hear about it.
