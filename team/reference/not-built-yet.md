# What we have not built

**Read this before answering anything about domains, uptime, crash alerts,
teams or SSO.**

The marketing site is ahead of the product in several places. A reply that
repeats a claim we do not deliver turns a disappointment into being lied to,
which is far harder to recover from.

## The site says it and we do not have it

These are the dangerous ones. A customer has read them and believes them.

| Claim | Where | Reality |
| --- | --- | --- |
| "Every bot gets `bot-name.shardly.xyz` with a certificate already issued" | Landing page | **Not built.** No subdomains at all. |
| "Downtime DM the moment it happens" | Landing page | **Not built.** We restart; we do not notify. |
| "Back online in seconds / exit code and stack trace kept" | Landing page | Restart yes. The kept exit code and trace, no. |
| Uptime percentage | Landing page | **Not measured.** No automated uptime monitoring behind it. |
| "Bring your own domain whenever" | Landing page | **Not built.** |
| "Automatic reshard as you grow" | Landing page | **Not built.** Shards are what the plan gives plus what is bought. |
| "Six runtimes, version pinned per bot" | Landing page | **Discord.js only** today. |
| "Custom Docker images on Pro and up" | Landing page | The panel exposes the field; not a supported product feature. |
| Status page | `/status` | **No live feed.** It shows a failure state after five seconds by design, rather than a fake green. |

If a customer quotes one of these, see
[the playbook](../playbooks/feature-not-built-yet.md). Take the hit, do not
pretend, and flag it.

## Not claimed, and not built

Safer — nobody was promised these — but still asked about.

- Resource alerts on CPU, memory or disk thresholds
- Scheduled tasks and cron jobs
- SFTP access
- Log retention, search and export
- Public API with scoped keys
- Outgoing webhooks
- Deploy on push
- Teams — several people on one account
- Single sign-on and enforced 2FA policy
- Session and device list — **built**, this one is done
- VAT ID and purchase orders in the dashboard
- In-place plan upgrades
- Dunning — the sequence of emails before a lapse
- Shardly Studio (website hosting) — announced for December 2026

## Partly there

- **Backups.** Create and restore work. Download and retention management are
  thinner than the marketing implies.
- **Add-on shards** apply to the most recently created server. With several
  servers, the customer must tell us which.
- **Entitlement overrides** exist — admin can raise a specific limit for one
  account without moving them up a tier. Offer this when the ask is narrow.

## Recently built, so say yes

Things people assume we lack:

- Sessions and device list, with revoke
- Account activity log, customer-readable, CSV export
- Rate limiting with messages naming the limit and what lifts it
- Provisioning queue with automatic retries and dead letters
- Heartbeat at `/api/health`

## Keep this file honest

It is the most load-bearing page in the handbook. If you find something out of
date — either direction — fix it the same day. A stale "not built" is nearly
as damaging as a stale promise: it makes us say no to something we could do.
