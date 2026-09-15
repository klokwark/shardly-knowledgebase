# Runbook: the heartbeat

## The URL

`https://shardly.xyz/api/health`

Public, no token. Safe to open in a browser or share with a customer asking
whether it is us.

## Reading it

**200 + `"status": "alive"`** — the platform is answering and every check
passed.

**503 + `"status": "dead"`** — something failed. `failed` names which, `detail`
says why.

```json
{
  "at": "2026-09-15T09:12:44.118Z",
  "detail": { "database": "14 ms", "queued": "0" },
  "status": "alive",
  "version": "ec209d1"
}
```

## The checks

| Check | Red when | What it means for you |
| --- | --- | --- |
| `database` | Ping fails or takes over 3s | Everything is broken. Escalate now. |
| `config` | A required secret is missing | Usually a deploy that lost a variable. Escalate. |
| `scheduler` | Tasks overdue **and** jobs queued | Provisioning has stopped. Escalate. |

## Why `scheduler` needs both halves

Tasks are driven from outside — the bot's hourly ping, the daily cron, and
ordinary site traffic. On a quiet night, "no task ran recently" is the correct
state, not a fault.

It is only a problem when work is waiting and nothing is picking it up. That
is the shape of *somebody paid and their server is not being built*.

## What it deliberately does not report

**Dead letters do not turn it red.** They already shout in `#staff-logs`, and
they stay until somebody clears them — so they would pin a monitor red for a
week, which is how a monitor stops being read.

Check `#staff-logs` and the provisioning queue for those.

## During an incident

1. Open the heartbeat. Note the code and which check failed.
2. Post it in the staff channel — it is the fastest shared fact.
3. If it is 200 and a customer is reporting a problem, it is **their** bot.
   Move to normal troubleshooting.

## If the heartbeat itself does not answer

Then the deployment is down entirely, not just a check failing. That is worse
than a 503 and it is an immediate escalation.

The endpoint is built so that this should not happen — every check is wrapped
and the outer catch still returns a 503 with a reason. Total silence means the
function is not running at all.

## The hourly bot line

`#staff-logs` gets a health line from the Discord bot every hour. It is meant
to be boring.

**If it stops appearing, the bot has stopped.** That does not take the
platform down — site traffic still drives the scheduler — but on a quiet night
nothing will drive it, and provisioning retries will stall. Worth raising.
