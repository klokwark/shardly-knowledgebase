# Triage and priority

## Categories

| Category | What belongs in it |
| --- | --- |
| `server` | The server itself: provisioning, resources, backups, panel |
| `bot` | Their code, tokens, intents, dependencies, imports |
| `billing` | Payments, invoices, plans, refunds |
| `account` | Sign-in, profile, notifications, deletion |
| `security` | Compromise, vulnerability reports, suspicious activity |
| `other` | Genuinely none of the above |

The line between `server` and `bot` is **whose fault could it be**. Their code
failing is `bot`. Our panel failing is `server`. When you cannot tell, it is
`bot` — that is where most of them land.

## Priorities and their SLA

| Priority | First response | Use it when |
| --- | --- | --- |
| `urgent` | **2 hours** | Platform down, security incident, paid and got nothing |
| `high` | **6 hours** | One customer's server is down and it is our side |
| `normal` | **24 hours** | The default. Everything ordinary |
| `low` | **48 hours** | A question, a feature request, an opinion |

**The SLA is first response, not resolution.** Answering within the window
with "I am on this, here is what I need" meets it. Solving it in a week and
never writing until then does not.

## What is actually urgent

- The platform is down for everybody.
- A security incident — a compromised account, an active vulnerability.
- Somebody paid and has nothing, and the automatic retries have given up.
- Data loss in progress, where acting now changes the outcome.

## What feels urgent and is not

- One bot offline because of the customer's own code. That is `normal`, and
  you will still probably answer it in an hour.
- An angry message. Tone is not priority. A furious message about an invoice
  is still billing.
- "URGENT!!!" in the subject. Triage reads the words, you read the situation.

Raising a priority because somebody shouted teaches people to shout, and
pushes down a genuinely urgent ticket from someone who was polite.

## Overriding the guess

Triage guesses and shows you why. Override it freely — the guess exists to
order the queue before a human has looked, not to be respected afterwards.

If you find yourself overriding the same wrong guess repeatedly, say so. The
rules are code and can be fixed.

## Security tickets

Anything in `security` is worked ahead of everything else, whatever its
priority. If you are not sure whether something is a security matter, treat it
as one and ask.
