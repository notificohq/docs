# SMTP (Simple Mail Transfer Protocol)

**Contact:** `email:EMAIL`

**Credential:** `smtp:USERNAME:PASSWORD@HOST:PORT`, `smtp:USERNAME:PASSWORD@HOST:PORT?tls=true`

**Channel:** `email`

## Steps
### Step: `smtp.send`
```json
{
  "step": "smtp.send",
  "credential": "CREDENTIAL_NAME"
}
```

## Template parameters
```yaml
from: "Sender <sender@example.com>" # Sender address ("FROM" field).
subject: "Email subject string"
body_html: "<b>HTML body</b>"
body: "Plaintext body"
```

If `body_html` field is empty, the message is sent as simple plaintext data. If both `body` and `body_html` fields are set,
the email is sent as multipart data with HTML and plaintext parts.
