# Categories, priorities, statuses

## Categories

`server` · `bot` · `billing` · `account` · `security` · `other`

The line between `server` and `bot` is **whose fault could it be**. Their code
failing is `bot`. Our panel failing is `server`. When genuinely unclear, `bot`
— that is where most land.

## Priorities and SLA

| Priority | First response |
| --- | --- |
| `urgent` | 2 hours |
| `high` | 6 hours |
| `normal` | 24 hours |
| `low` | 48 hours |

First response, not resolution.

## Statuses

| Status | Clock |
| --- | --- |
| `open` | running |
| `in_progress` | running |
| `waiting` — on the customer | **stopped** |
| `resolved` | stopped |
| `closed` | stopped |

## Queue order

Priority dominates; age is added so nothing starves; past SLA jumps to the
top.

## The in-product deflection list

Before opening a ticket, customers are shown short answers matching what they
have typed. That list lives in `api/_lib/support-kb.ts` and currently covers:

| Slug | Covers |
| --- | --- |
| `server-wont-start` | Bot offline or will not start |
| `invalid-token` | Invalid token, disallowed intents |
| `upload-code` | Getting code onto the server |
| `billing-portal` | Invoices, card changes, cancelling |
| `addons` | Shards, database, more resources |
| `account-access` | Password, 2FA, getting back in |
| `platform-status` | Is the platform having problems |

**Those are summaries. The full versions are in `customer/`.** When you change
one, change the other — a deflection card that contradicts the article it
links to is worse than no card.

If a question comes up repeatedly and is not on that list, say so. Adding an
entry is a small code change and it stops tickets being opened at all, which
is worth more than answering them quickly.

## When triage guesses wrong

Override it. It shows you why it guessed, and a wrong guess costs a reordering
rather than anything real.

If the same wrong guess keeps happening, raise it — the rules are code and can
be fixed.
