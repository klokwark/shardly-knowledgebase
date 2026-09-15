# Plans and entitlements

The numbers, in one place.

## Plans

| | Starter | Pro | Shard |
| --- | --- | --- | --- |
| Weekly | €2 | €5 | €12 |
| Memory | 512 MB | 2 GB | 8 GB |
| CPU | shared vCPU | 1 core | 2 cores |
| Disk | 5 GB | 20 GB | 80 GB |
| Shards included | 1 | 3 | 10 |

Monthly is roughly 12% under weekly. All prices exclude tax.

## Backups

| | Manual slots | Scheduled | Retention |
| --- | --- | --- | --- |
| Starter | 2 | none | — |
| Pro | 2 | every 24h | 14 days |
| Shard | 2 | every hour | 30 days |

Two manual slots on **every** plan, Starter included. This is the one people
get wrong most often.

## API limits, per minute

| | Reads | Writes |
| --- | --- | --- |
| No plan / signed out | 60 | 20 |
| Starter | 120 | 40 |
| Pro | 240 | 80 |
| Shard | 600 | 200 |

A write that provisions, moves a file or reaches the panel costs five times a
read. So "expensive" actions run out roughly five times faster than the number
suggests.

## Other limits

| | Free | Starter | Pro | Shard |
| --- | --- | --- | --- | --- |
| Attachment size | 8 MB | 8 MB | 16 MB | 32 MB |
| Attachments per message | 5 | 5 | 5 | 5 |
| GitHub imports per 30 min | 0 | 5 | 10 | 20 |
| Largest repo archive | — | 60 MB | 60 MB | 120 MB |
| Servers | 0 | unlimited | unlimited | unlimited |

Sign-in links are capped at five per email address per hour with a minute
between sends — an abuse limit, not a plan perk, and it does not scale.

## Capabilities

Feature flags, independent of the hosting tier. "Enterprise" is not a plan you
can buy — it is a set of flags somebody is granted.

| Capability | Starter | Pro | Shard |
| --- | --- | --- | --- |
| `customDomain` | — | yes | yes |
| `scheduledTasks` | — | yes | yes |
| `auditExport` | — | — | yes |
| `teams` | — | — | yes |
| `sso` | — | — | — |

**Important:** a flag being on does not mean the feature is built.
`customDomain` and `scheduledTasks` are flags for things that do not exist
yet. See [what we have not built](not-built-yet.md).

## Add-ons

| Add-on | Price | Gives |
| --- | --- | --- |
| Shards | €5/week | 5 extra shards |
| Database | see pricing page | 5 GB database |

## Overrides

Admin can raise any limit, or grant any capability, for a single account —
without moving them up a tier and without a deploy. The change is recorded in
the customer's activity log with the actor's name.

**Offer this** when the ask is narrow and reasonable: a customer who needs 30
imports an hour for a migration does not need a tier upgrade, they need a
number changed for a week.
