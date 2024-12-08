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

## Contact

Each contact in the `contacts` array represents a specific method of reaching the recipient. Each Contact is represented by a string, formatted as `type:value`.

## Example

Here's an example of a Recipient object with multiple contacts:

```json
{
  "id": "3766b9e9-a700-4c75-a9c9-88117af11767",
  "contacts": [
    "telegram:123456789",
    "mobile_phone:+123456789",
    "email:someone@example.com"
  ]
}
```
