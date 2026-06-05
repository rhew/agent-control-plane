# Discord Setup

## Create the Server

1. Create a private Discord server for the agent.
2. Remove **View Channels** and **Create Invite** from `@everyone`.
3. Create a private text channel, for example `#hermes`.
4. Allow only your user or role and the bot role to view and send in that channel.
5. Enable **Developer Mode** in Discord user settings.
6. Right-click the channel and select **Copy Channel ID**.

## Create the Bot

1. Open the Discord Developer Portal: <https://discord.com/developers/applications>
2. Create an application for this agent.
3. Add a bot user.
4. Reset and copy the bot token once.
5. Turn off **Public Bot** if available.
6. Leave **Requires OAuth2 Code Grant** off.
7. Enable **Message Content Intent** so Hermes can read mention messages.
8. Enable **Server Members Intent** if using username or role allowlists. Numeric `DISCORD_ALLOWED_USERS` IDs do not require member lookup, but this intent is harmless for a private single-server bot.

## Invite the Bot

1. In OAuth2, use **Guild Install**.
2. In the OAuth2 URL generator, select:
   - `bot`
   - `applications.commands`
3. Grant only the permissions Hermes needs:
   - View Channels
   - Send Messages
   - Read Message History
   - Use Slash Commands
   - Create Public Threads
   - Send Messages in Threads
4. Do not grant Administrator.
5. Open the generated URL and invite the bot to the private server.

## Configure Hermes

Set these in `hermes-config/.env`:

```env
DISCORD_BOT_TOKEN=<bot-token>
DISCORD_ALLOWED_USERS=<your-user-id>
DISCORD_ALLOWED_CHANNELS=<channel-id>
DISCORD_REQUIRE_MENTION=true
```

Copy your user ID by right-clicking your Discord profile and selecting **Copy User ID**. Use the human user ID, not the bot ID.

Restart Hermes after changing the file:

```sh
docker compose restart hermes
```

## Test

Mention the bot application user in the allowed channel:

```text
@Agents of Bucka hello
```

Choose the autocomplete entry with the **APP** tag. A role mention with the same visible name does not count; Hermes requires the bot user in Discord's message `mentions` list when `DISCORD_REQUIRE_MENTION=true`.
