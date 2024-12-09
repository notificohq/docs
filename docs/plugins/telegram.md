# Telegram Bot
- **Contact:** `telegram:CHAT_ID`
- **Credential:** `telegram:TOKEN`

## Steps
### Step: `telegram.send`
```json
{
  "step": "telegram.send",
  "credential": "CREDENTIAL_NAME"
}
```

## Template parameters
```yaml
body: "You have {{ beans_count }} magic beans"  # text of Telegram message, sent by the bot
```

## Connecting to Telegram
You can get a new Telegram bot token from [@BotFather](https://t.me/BotFather).
