# Internal notes

Notes on a ticket that the customer cannot see.

## Use them for

- **What you tried.** Especially what did not work.
- **What you ruled out**, and how. "Not a token problem, I saw a successful
  login at 14:02."
- **What you suspect** but have not confirmed.
- **Context from elsewhere** — a Discord conversation, a related ticket.
- **A warning to the next person.** "Third ticket about this; if it recurs,
  escalate rather than restarting again."

## Write them for the next person

Who is often you, weeks later, with no memory of it. "Tried the thing" helps
nobody. "Restarted at 15:10, stayed up 20 min, died with the same OOM" is a
handover.

## What not to write

They are invisible in the UI. They are not invisible full stop — they sit in
the database, they can be exported, and they would be disclosed in a legal
process.

So:

- **Nothing about the customer as a person.** Not "difficult", not "clueless",
  not a joke at their expense. Write the facts.
- **No credentials.** Not a token, not a password, not a key. Say where it is,
  never what it is.
- **No speculation about colleagues.** "Unclear why this was closed" is fine;
  naming and blaming is not.

The test: **would this be embarrassing if the customer read it?** If yes, do
not write it. That is not paranoia about disclosure — it is that writing it
changes how the next agent treats them.

## When to note versus reply

If the customer would benefit from knowing it, tell them. Notes are for things
that genuinely do not help them: internal reasoning, half-formed theories,
process.

A ticket with ten notes and two thin replies usually means somebody was
thinking out loud instead of communicating.
