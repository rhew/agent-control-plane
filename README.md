# Hermes Agent

Docker Compose wrapper for Hermes Agent.

## Config

Hermes reads `./hermes-config` as `/opt/data`.

Set `HERMES_UID` and `HERMES_GID` in `.env` to the output of `id -u` and `id -g` so Hermes writes mounted files as your user instead of root.

Set runtime secrets and gateway settings in `hermes-config/.env` so they stay out of Git:

```env
DISCORD_BOT_TOKEN=<discord-bot-token>
DISCORD_ALLOWED_USERS=<your-discord-user-id>
DISCORD_ALLOWED_CHANNELS=<discord-channel-id>
DISCORD_REQUIRE_MENTION=true
```

Set both Discord allowlists so Hermes only responds to approved users in approved channels. See [DISCORD.md](DISCORD.md) for bot setup and mention behavior.

If you need local OpenAI-compatible API access, enable `API_SERVER_ENABLED`.

## Run

```sh
docker compose up -d
```

## Reload

```sh
docker compose restart hermes
```

## CLI

```sh
docker compose run --rm -it hermes <command>
```
