# API

The main method in Notifico is:

`POST /api/v1/event/send`

It will create AMQP message, send it to broker, and then run the pipeline for the corresponding event.

```json5
{
  "event": "event_name",
  "recipient": {
    // This ID will be used for List-Unsubscribe and other features.
    // It is recommended to store it in an external system and use the same ID for the same Recipient.
    "id": "3766b9e9-a700-4c75-a9c9-88117af11767",
    "contacts": [
      {
        // Telegram uses "Chat ID" for identifying users in its Bot API.
        // You cannot use usernames or phone numbers here.
        "type": "telegram",
        "chat_id": 123456789
      },
      {
        // This can be used for SMS or WhatsApp communication.
        "type": "mobile_phone",
        "number": "+123456789"
      },
      {
        // This is Email. You know what it is.
        // Address format can be "Anyone <anyone@example.com>"
        "type": "email",
        "address": "someone@example.com"
      }
    ]
  },
  // This is your context, that is passed to templating engine.
  "context": {
    "variable": 102
  }
}
```