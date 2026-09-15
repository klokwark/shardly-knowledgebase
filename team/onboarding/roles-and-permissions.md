# Roles and permissions

Four roles. Yours decides what the staff panel shows you and what the API lets
you do.

## user

Every customer. Owns their own tickets and nothing else.

## support

The narrowest staff role.

- **Tickets:** read, reply, note, close
- **Servers:** read — enough to answer a ticket about one
- **Billing:** nothing
- **Users:** nothing

Cannot assign or re-prioritise, cannot touch a server, cannot see billing.
Those three are where a mistake turns into somebody's outage or somebody's
money.

## manager

Support, plus the authority to run the queue and act on a server.

- **Tickets:** everything, including assign and triage
- **Servers:** read and manage — restart, suspend
- **Billing:** read only
- **Users:** list and view

Read-only on billing on purpose: extending a plan or comping time is money,
and that stays with admin.

## admin

Everything, including handing out roles, changing billing, and raising an
account's limits.

## If you cannot do something

Ask. Do not find a way around it, and do not ask a customer to do something
awkward because you lack a permission — say "let me get someone who can" and
hand it over.

## Every action is logged

Power actions, suspensions, role changes, limit changes, file operations, data
exports. Actor, target, time, address, and how you authenticated.

**The customer sees the entries on their own account.** Not your address —
that is your personal data, not theirs — but they see that support acted, what
was done, and when.

Write and act as though they are reading it, because they can.

## Impersonation

Admin only, logged, and visible to the customer. Use it when you genuinely
cannot reproduce something any other way, say why in an internal note, and get
out when you are done.
