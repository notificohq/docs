# Recipient

A Recipient in Notifico represents an entity that can receive notifications. Each recipient has a unique identifier and one or more contact methods for notification targeting.

## Properties

### id
- Type: String
- Description: A unique identifier for the recipient. This ID is used for features like List-Unsubscribe and should be consistent across notifications for the same recipient.
- Example: "3766b9e9-a700-4c75-a9c9-88117af11767"

### contacts
- Type: Array of Contact objects
- Description: An array containing one or more contact methods for the recipient. These contacts are used for notification targeting.

## Contact Object

Each contact in the `contacts` array represents a specific method of reaching the recipient. The structure of a contact object is as follows:

### type
- Type: String
- Description: Specifies the channel for notification. This parameter is channel-specific and determines how the notification will be sent to the recipient.
- Examples: `telegram`, `mobile_phone`, `email`, `slack`

### Additional Parameters
Depending on the `type`, each contact object will have additional parameters specific to that channel. For example:

For `"type": "telegram"`:

  - `chat_id`: The Telegram Chat ID for the recipient

For `"type": "mobile_phone"`:

  - `number`: The phone number for SMS or WhatsApp communication

For `"type": "email"`:

  - `address`: The email address of the recipient

## Example

Here's an example of a Recipient object with multiple contacts:

```json
{
  "id": "3766b9e9-a700-4c75-a9c9-88117af11767",
  "contacts": [
    {
      "type": "telegram",
      "chat_id": 123456789
    },
    {
      "type": "mobile_phone",
      "number": "+123456789"
    },
    {
      "type": "email",
      "address": "someone@example.com"
    }
  ]
}
```
