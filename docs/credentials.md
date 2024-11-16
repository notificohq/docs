# Credentials

Credentials are stored in TOML format. You can add as many configurations as you need for different services.

## Telegram Bot

To configure a Telegram bot, add the following section to your `credentials.toml` file:

```toml
[telegram_bot.<NAME>]
token = "YOUR_TELEGRAM_BOT_TOKEN"
```

Replace `YOUR_TELEGRAM_BOT_TOKEN` with your actual Telegram bot token.

## SMTP (Simple Mail Transfer Protocol)

To configure an SMTP server, add the following section to your `credentials.toml` file:

```toml
[smtp.<NAME>]
tls = true
host = "smtp.example.com"
port = 587
username = "your_username@example.com"
password = "your_password"
```

Replace the values with your SMTP server details.

## SMPP (Short Message Peer-to-Peer Protocol)

To configure an SMPP server, add the following section to your `credentials.toml` file:

```toml
[smpp.<NAME>]
host = "smpp.example.com"
port = 2775
username = "your_username"
password = "your_password"
```

Replace the values with your SMPP server details.

## WhatsApp Business

To configure a WhatsApp Business bot, add the following section to your `credentials.toml` file:

```toml
[whatsapp_business.<NAME>]
phone_id = YOUR_PHONE_ID
token = "YOUR_WHATSAPP_BOT_TOKEN"
```

Replace `YOUR_PHONE_ID` and `YOUR_WHATSAPP_BOT_TOKEN` with your actual WhatsApp Business bot details.
