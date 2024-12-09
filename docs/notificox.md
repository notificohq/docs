# NotificoX

[![GitHub Release](https://img.shields.io/github/v/release/notificohq/notifico?style=for-the-badge)](https://github.com/notificohq/notifico/releases/latest)

NotificoX is a versatile tool designed to send messages to various services, inspired by the popular notification library, [Apprise](https://github.com/caronc/apprise).
It provides a unified interface to deliver notifications across multiple platforms, making it easier for users to manage and automate their communication needs.

With NotificoX, you can send messages to a wide range of channels, including email, SMS, and instant messaging services.

This tool is a single dependency-free binary (only libc and SSL library are required), so you can run it anywhere,
for example in CI pipelines.

Some arguments are formatted in [JSON5](https://json5.org/), so they can be entered without numerous escape sequences.

## Send notification locally
**Usage:**
```shell
notificox send <CREDENTIAL> [CONTACTS]... --template <TEMPLATE>
```

**Where:**

- TEMPLATE: JSON5-formatted message template object. Template parameters are transport-specific. You can read about template parameters in [Plugins](plugins/core.md) section. Most of the transports require only "body" parameter to be set.
- CREDENTIAL: Transport credential. You can read about transport syntax in [Plugins](plugins/core.md) section.
- CONTACTS: zero or more contacts to send the message. Contact format is transport-specific. Some transports, like Gotify, don't require contacts, as they only use credentials to send.

This command internally constructs a Notifico [pipeline](pipeline.md) and executes it using the embedded pipeline engine.
This process is fully transparent to end user.

### Example
```shell
# Send a Telegram notification to recipient with chat_id=111579711 using telegram token
notificox send --template "{body: 'my notification body'}" \
    "telegram:TOKENTOKEN:TOKENTOKENTOKENTOKENTOKENTOKENTOKEN" \
    "telegram:111579711"
```

## Trigger an event on remote Notifico Ingest service
**Usage:**
```shell
notificox send-event [OPTIONS] --ingest <INGEST> <EVENT> <CONTEXT>
```
