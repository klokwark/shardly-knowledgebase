# Tools and access

## What you need on day one

| Tool | What for | Who grants it |
| --- | --- | --- |
| Shardly staff account | The queue | An admin sets your role |
| Discord — staff channels | Incidents, dead letters, new tickets | An admin |
| Your own Shardly server | Reproducing things | Buy or get comped |

## The staff panel

`/app/staff` once you have a role.

- **Queue** — tickets, filtered and sorted
- **Servers** — every server, with live state from the panel, plus the
  provisioning queue and database schema health
- **Billing** — subscriptions and orders (manager and up)
- **Team** — who works here and what they can do (manager and up)

## The Discord channels

**`#staff-logs`** gets automatic posts:

- A new ticket opens, with number, category, priority and a quote
- A provisioning job gives up — somebody has paid and has nothing

The bot also posts an hourly health line. It is meant to be boring. **Boring
is the signal** — if it stops appearing, something is wrong with the bot.

## The heartbeat

`https://shardly.xyz/api/health`

200 means alive, 503 means something is broken, and the body says what. Safe
to open in a browser whenever you want to know whether it is us.

## What support cannot see

- **Customer passwords.** Hashed. Nobody can read one.
- **Bot tokens.** Stored so we can start the process, not shown back. If a
  customer has lost theirs, they reset it in Discord's portal. We cannot
  recover it.
- **Card details.** Polar holds those. We see subscription status and an
  invoice reference.

If a customer asks you for any of these, the answer is that we cannot — not
that we will not.

## Your own access hygiene

- Two-factor on your staff account. Not optional.
- Do not sign in to staff tools on a shared machine.
- Check [where you are signed in] on your own account occasionally.
- If you lose a device, revoke its sessions **before** you tell anybody you
  lost it.
