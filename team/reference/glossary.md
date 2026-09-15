# Glossary

**Add-on** — Something bought on top of a plan. Shards, or a database.

**Audit log / activity log** — Append-only record of consequential actions.
Customer-readable. Two-year retention. Includes what staff did.

**Backup** — Snapshot of a server's disk. Two manual slots on every plan.

**Capability** — A feature flag independent of the hosting tier.
`auditExport`, `customDomain`, `teams`, `sso`, `scheduledTasks`. A flag being
on does not mean the feature is built.

**Claim (job)** — A worker picking up a job. Counted separately from failures,
because a frozen worker costs a delay, not an attempt.

**Dead letter** — A job that gave up after five real failures. Posts to
`#staff-logs` automatically. Always means somebody may have paid and got
nothing.

**Deflection** — Showing a customer an answer before they open a ticket. Lives
in `support-kb.ts`.

**Deployment** — Our record of a customer's server. Has a `serverId` (the
short handle in URLs) and a status describing its life, not whether the
process is running.

**Entitlement** — What an account may do and up to what limit. Derived from
the plan, overridable per account by admin.

**Heartbeat** — `/api/health`. 200 alive, 503 dead.

**Intents** — What a Discord bot asks to receive. Three are privileged and
need enabling in Discord's portal.

**Job** — A unit of background work with an idempotency key. Provisioning and
order fulfilment run as jobs.

**Merchant of record** — Polar. They are the seller for tax purposes, hold the
card details, and issue invoices.

**Outbox** — Queue of Discord DMs waiting for the bot to deliver.

**Panel** — The Pterodactyl instance behind the servers. When "the panel is
busy", provisioning is slow.

**Plan status vs process state** — `deployment.status` describes the server's
life (queued, building, active, failed). The **console** says whether the bot
process is running. Both can be true at once; confusing them causes bad
replies.

**Shard** — One gateway connection handling a slice of a bot's servers.
Required past roughly 2,000 Discord servers.

**SLA** — First-response target. 2/6/24/48 hours by priority.

**Task** — Scheduled work in `tasks.ts`. Driven from outside: the bot's ping,
the daily cron, or ordinary traffic.

**`waiting`** — Ticket status meaning the ball is with the customer. **Stops
the SLA clock**, which is why it has to be honest.
