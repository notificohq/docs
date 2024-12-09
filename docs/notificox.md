# Notificox

[![GitHub Release](https://img.shields.io/github/v/release/notificohq/notifico?style=for-the-badge)](https://github.com/notificohq/notifico/releases/latest)

Notificox is a versatile tool designed to send messages to various services, inspired by the popular notification library, [Apprise](https://github.com/caronc/apprise).
It provides a unified interface to deliver notifications across multiple platforms, making it easier for users to manage and automate their communication needs.

With Notificox, you can send messages to a wide range of channels, including email, SMS, and instant messaging services.

This tool is a single dependency-free binary (only libc and SSL library are required), so you can run it anywhere,
for example, in CI pipelines.

Some arguments are formatted in [JSON5](https://json5.org/), so they can be entered in console without escape sequences.

## Send notification locally
**Usage:**
```shell
notificox send <CREDENTIAL> [CONTACTS]... --context <CONTEXT>
```

**Where:**

- CONTEXT: JSON5-formatted message context object. Parameters are transport-specific. You can read about template parameters in [Plugins](plugins/core.md) section. Most of the transports require only "body" parameter to be set.
- CREDENTIAL: Transport credential. You can read about transport syntax in [Plugins](plugins/core.md) section.
- CONTACTS: zero or more contacts to send the message. The Contact format is transport-specific. Some transports, like Gotify, don't require contacts, as they only use credentials to send.

This command internally constructs a Notifico [pipeline](pipeline.md) and executes it using the embedded pipeline engine.
This process is fully transparent to end user.

### Examples
Sending a Telegram message to recipient with chat_id=111579711 using telegram token:
```shell
notificox send "telegram:TOKEN" "telegram:111579711" -c "{body: 'my notification body'}"
```
Sending a Slack message with a PDF file attached:
```shell
notificox send "slack:TOKEN" "slack:CHAT_ID" -c "{body: 'my notification body'}" -a ~/file.pdf
```
Sending a [ntfy.io](plugins/ntfy.md) message with templating enabled:
```shell
notificox send "ntfy:https://ntfy.sh" "ntfy:notifico" -t template.toml -c "{username: 'USER1'}"

== template.toml ==
[parts]
body = "Hello from Notifico! Username: {{username}}"
```

## Trigger an event on remote Notifico Ingest service
**Usage:**
```shell
notificox send-event [OPTIONS] --ingest <INGEST> <EVENT> <CONTEXT>
```
