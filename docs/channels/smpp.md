# SMPP (Short Message Peer-to-Peer Protocol)

**Channel identifier:** `sms`

SMPP is a protocol used by the telecommunications industry for exchanging SMS messages between Short Message Service Centers (SMSC) and External Short Messaging Entities (ESME).

Many SMS Center services allow SMPP protocol for sending SMS.

To configure an SMPP server, add the following section to your `credentials.toml` file:

```toml
[smpp.<NAME>]
host = "smpp.example.com"
port = 2775
username = "your_username"
password = "your_password"
```

Note: We don't support TLS for SMPP right now. This will be added in future releases.
