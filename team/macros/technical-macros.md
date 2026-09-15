# Technical macros

## Ask for logs — send this first, every time

> Could you paste the last 50 lines from your console? Open your server,
> select the log text and copy it.
>
> That normally shows exactly what is stopping it, and saves us both a round
> trip.

If they send a screenshot:

> That works, though pasting the text is easier for me to search — and screen
> captures often cut off just above the interesting line.

## Token reset

> That error means Discord is rejecting the token.
>
> 1. Open the [developer portal](https://discord.com/developers/applications),
>    pick your application, then **Bot**.
> 2. **Reset Token** and copy the new one straight away — it is shown once.
> 3. In Shardly, **Bot settings → Variables**, set `DISCORD_TOKEN` to it.
> 4. Restart from the console.
>
> If the token was ever pushed to a public repository, Discord invalidates it
> automatically — removing the commit does not help, only the reset does.

## Wrapper folder

> I can see the problem: your files are inside a `{folder}` folder rather than
> at the top level, so the startup file we are looking for is not where we
> expect.
>
> In the file manager, open `{folder}`, select everything, and move it up one
> level. Then restart. That is usually all it takes.

## Intents

> `Used disallowed intents` means your code is asking for a privileged intent
> your application has not been granted.
>
> Two halves, and both have to agree:
>
> 1. [Developer portal](https://discord.com/developers/applications) → your
>    app → **Bot** → enable the intents you need (Message Content, Server
>    Members, Presence).
> 2. Request the same ones in your `Client({ intents: [...] })`.
>
> Worth knowing: past 100 servers you have to apply to Discord for privileged
> intents and wait for approval, so it is worth planning for before you get
> there.

## Restarted for you

> I have restarted your server and it has come up cleanly — it has been
> running for {time} now without issue.
>
> If it goes down again, reply here rather than restarting it yourself. A
> repeat means something is actually wrong and I would rather find it than
> keep restarting.

## Out of memory

> That is your bot exceeding the memory your plan allows. Your plan is
> {plan}, which gives you {memory}.
>
> Dropping this in your code will tell us which it is:
>
> ```js
> setInterval(() => {
>   const mb = process.memoryUsage().heapUsed / 1024 / 1024;
>   console.log(`heap ${mb.toFixed(1)} MB`);
> }, 60_000);
> ```
>
> If it climbs steadily and never comes down, that is a leak — usually a Map
> or array that gets added to and never cleaned. If it is high and flat from
> the start, you have simply outgrown the plan and moving up a tier is the
> honest fix.

## It is their code

> That is a syntax error in `{file}` at line {line} — {what}.
>
> Not a hosting problem, but here is what I think it should be:
>
> ```js
> {corrected}
> ```
>
> Save, restart, and let me know.
