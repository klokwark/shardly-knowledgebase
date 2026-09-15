# Playbook: account recovery

**Category:** `account` or `security` · **Priority:** `high`

## What you are looking at

Somebody cannot get into their account and self-service has not worked. Lost
2FA device with no backup codes, or lost access to the email address itself.

## The rule

**This is deliberately slow.** An account recovery that a convincing message
can complete quickly is a vulnerability wearing a helpful face.

The person asking is usually the owner. Occasionally they are not, and that is
the case the process exists for.

## What counts as proof

Ask for several. Any one alone is weak.

- **A recent invoice number**, or the last four digits of the card used.
- **A server id** from the account.
- **The original signup address**, if they are writing from a different one.
- **Roughly when they signed up.**
- **What the account has on it** — how many servers, which plan, the bot's
  name.

An attacker who has read their Discord might know the bot's name. They will
not know the invoice number.

## What is not proof

- A convincing story.
- Urgency. "I need this in ten minutes" is pressure, not evidence — and
  pressure is a technique.
- Access to the Discord account. That is a different account.
- A screenshot. Trivially faked.

## Check against the record

Open the account in the staff panel. Compare what they said with what is
there. Look at their [activity log] — a compromise often shows as actions they
did not take.

## What to say

> I can help with this. Because it is account access I need to confirm a few
> things first — these are deliberately awkward, and they are what stops
> somebody else doing this to your account.
>
> Could you tell me: the number on a recent invoice, the id of one of your
> servers, and roughly when you signed up?

## When it does not add up

Do not accuse. Do not confirm what you know. Escalate.

> I am not able to confirm the account from that. Let me pass this to a
> colleague who can look further.

**Never tell them what was wrong with their answer.** That is a free hint.

## After recovery

- Tell them to set up 2FA again, with backup codes stored somewhere else.
- Tell them to review [where they are signed in] and revoke anything old.
- Note what proof you accepted. If it turns out to be wrong, that note is how
  we learn.

## Escalate when

- The proof is thin.
- There is any sign of compromise.
- They are asking for the email address on the account to be changed as part
  of it — that combination is the classic takeover.
