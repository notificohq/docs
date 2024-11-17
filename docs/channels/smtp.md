# SMTP (Simple Mail Transfer Protocol)

## Steps
```json
{
  "step": "smtp.send",
  "credential": "CREDENTIAL_NAME"
}
```

## Template parameters
```toml
# Sender address ("FROM" field).
from = "Sender <sender@example.com>"
subject = "Email subject string"
body_html = "<b>HTML body</b>"
body_plaintext = "Plaintext body"
```

All emails are sent as multipart data with HTML and plaintext parts.


## Credentials
To configure an SMTP server, add the following section to your `credentials.toml` file:

```toml
[smtp.<NAME>]
tls = true  # The flag indicating whether to use TLS (STARTTLS is supported, too)
host = "smtp.example.com"  # The address of your SMTP server.
port = 587  # The port number used by your SMTP server (commonly 25, 465, or 587).
username = "your_username@example.com"  # The username for authenticating with the SMTP server.
password = "your_password"  # The password associated with the SMTP username.
```

Replace the values with your SMTP server details.