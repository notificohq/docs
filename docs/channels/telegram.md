# Telegram Bot

**Channel identifier:** `telegram`

## Steps
```json
{
  "step": "telegram.send",
  "credential": "CREDENTIAL_NAME"
}
```

## Template parameters
- `body` parameter defines the text of Telegram message, sent by the bot.
```toml
body = "You have {{ beans_count }} magic beans"
```

## Credentials
To configure a Telegram bot, add the following section to your `credentials.toml` file:

```toml
[telegram_bot.CREDENTIAL_NAME]
token = "YOUR_TELEGRAM_BOT_TOKEN"
```

Replace `CREDENTIAL_NAME` with a credential name, that will be used for referencing this credential in pipelines (see above).
Also, replace`YOUR_TELEGRAM_BOT_TOKEN` with your actual Telegram bot token. You can get a new Telegram bot token from [@BotFather](https://t.me/BotFather).
