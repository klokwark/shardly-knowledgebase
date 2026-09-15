---
title: Discord.js quickstart
slug: quickstart-discordjs
category: bot
keywords: [discord.js, discordjs, quickstart, example, template, node]
reviewed: 2026-09-15
---

# Discord.js quickstart

A bot that starts, connects and answers one command. Copy it, change it.

## Files

Two files at the top level of your server.

**`package.json`**

```json
{
  "name": "my-bot",
  "version": "1.0.0",
  "type": "module",
  "main": "index.js",
  "dependencies": {
    "discord.js": "^14.16.0"
  }
}
```

**`index.js`**

```js
import { Client, GatewayIntentBits } from "discord.js";

const client = new Client({
  // Only ask for what you use. Every intent you add is one more thing that
  // can be refused at connect time.
  intents: [GatewayIntentBits.Guilds],
});

client.once("clientReady", () => {
  console.log(`Logged in as ${client.user.tag}`);
});

client.on("interactionCreate", async (interaction) => {
  if (!interaction.isChatInputCommand()) return;
  if (interaction.commandName === "ping") {
    await interaction.reply("Pong.");
  }
});

// Never hardcode the token. This reads the variable you set in Bot settings.
client.login(process.env.DISCORD_TOKEN);
```

## Then

1. Set `DISCORD_TOKEN` in **Bot settings**.
2. Check the startup file is `index.js`.
3. Press **Start**.

Dependencies install on start, so the first boot is slower than the rest.

## Registering the command

Slash commands are registered with Discord, not with us. The
[discord.js guide](https://discordjs.guide/) covers it properly and stays more
current than we would.

## Things that bite people

- **`type: "module"`** and `import` go together. If you use `require`, remove
  that line.
- **Node version.** We run a current LTS. If your code needs something older,
  say so in a ticket.
- **`console.log` is your friend.** Our console shows stdout live, so a log
  line is the fastest way to find out what your bot thinks is happening.

## Still stuck?

Open a ticket with the console output. Include what you expected to happen.
