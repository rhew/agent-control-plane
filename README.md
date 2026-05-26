# Hermes Agent

Docker Compose wrapper for Hermes Agent.

## Config

Hermes reads `./hermes-config` as `/opt/data`.

Set `HERMES_UID` and `HERMES_GID` in `.env` to the output of `id -u` and `id -g` so Hermes writes mounted files as your user instead of root.

Set `API_SERVER_KEY` in `hermes-config/.env` so clients authenticate to the Hermes API server with `Authorization: Bearer <key>`.

## Run

```sh
docker compose up -d
```

Gateway: `http://127.0.0.1:8642/v1`

## CLI

```sh
docker run -it --rm -v "$PWD/hermes-config:/opt/data" nousresearch/hermes-agent:latest
```
