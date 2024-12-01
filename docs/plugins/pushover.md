# Telegram Bot

**Channel identifier:** `pushover`

## Quick example
`POST /api/v1/send`
```json
{
    "event": "YOUR_EVENT_NAME",
    "recipients": [
        {
            "id": "3766b9e9-a700-4c75-a9c9-88117af11767",
            "contacts": [
                {
                    "type": "pushover",
                    "user": "RECIPIENT_USER_KEY"
                }
            ]
        }
    ],
    "context": {
        "beans_count": 4815162342
    }
}
```

## Step: `pushover.send`
```json
{
  "step": "pushover.send",
  "credential": "CREDENTIAL_NAME"
}
```

## Template parameters
- `text` parameter defines the body of Pushover message.
- `title` defines the title, displayed in Push notification.
```toml
text = "You have {{ beans_count }} magic beans"
title = "Hello!"
```

## Contact
[Recipient](../recipient.md) Contact format for Pushover integration:
```json
{
  "type": "pushover",
  "user": "USER_KEY"
}
```

## Credentials
To configure your Pushover account, you have to create a new application [here](https://pushover.net/apps/build).
You will get "API Token", that you can add to your `credentials.toml` file:

```toml
[pushover.CREDENTIAL_NAME]
token = "YOUR_PUSHOVER_TOKEN"
```

Replace `CREDENTIAL_NAME` with a credential name, that will be used for referencing this credential in pipelines (see above).
