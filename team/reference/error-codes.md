# Errors and what they mean

## HTTP from our API

| Code | Means | What to tell them |
| --- | --- | --- |
| 400 | Malformed request | Usually a client bug. Get the exact steps. |
| 401 | Not signed in | Sign in again. Their session expired or was revoked. |
| 403 | Signed in, not allowed | Wrong account, or a capability their plan lacks. The body says which. |
| 404 | Not found — **or not allowed to know** | Staff endpoints 404 rather than 403 deliberately. |
| 405 | Wrong method | Client bug. |
| 409 | Conflict | E.g. no paid plan ready for setup. |
| 429 | Rate limited | The body names the limit and what lifts it. `Retry-After` says when. |
| 500 | Our bug | Escalate with the request and time. |
| 502 | Upstream failed — usually the panel | Often transient. Retry, then escalate. |
| 503 | Health check failing | Check `/api/health`. Likely an incident. |

**404 on a staff route is not a bug.** There is no reason to confirm to a
stranger that an endpoint exists.

## Discord errors in customer logs

| Error | Means |
| --- | --- |
| `An invalid token was provided` | Token wrong, missing or reset |
| `Used disallowed intents` | Privileged intent not enabled in the portal |
| `Missing Access` / `Missing Permissions` | Bot lacks permission in that server |
| `Unknown Guild` / `Unknown Channel` | Removed, or wrong id |
| `50007` | Cannot DM this user — no shared server, or DMs closed |
| `429` | Rate limited by Discord. See the article. |

**50007** is the one to recognise: it is why a Discord notification says
undeliverable. The customer left our server or closed DMs.

## Node errors

| Error | Means |
| --- | --- |
| `Cannot find module 'x'` | Not installed, or path wrong |
| `ENOSPC` | Disk full |
| `EACCES` | Permissions — usually an uploaded `node_modules` |
| `heap out of memory` | Memory limit |
| `ERESOLVE` | Dependency conflict |
| `EADDRINUSE` | Port already bound |
| `UnhandledPromiseRejection` | An async call rejected uncaught; Node kills the process |

## Job states

| State | Means |
| --- | --- |
| `queued` | Waiting for a worker |
| `running` | A worker has it, lease held |
| `done` | Succeeded |
| `dead` | Gave up after five real failures. **Somebody paid and has nothing.** |

`claims` much higher than `failures` means workers are picking the job up and
vanishing — a platform problem, not the customer's. Escalate.

## Health check

`/api/health`, 200 or 503. The body names which check failed: `database`,
`config`, or `scheduler`.

`scheduler` only goes red when tasks are overdue **and** jobs are queued —
because on a quiet night nothing running is correct rather than broken.
