The fastest way to deploy Notifico is Docker. We will use RabbitMQ as AMQP broker.

Create `credentials.toml` file:
```toml
[smtp.email]
tls = true
host = "<Your SMTP server host>"
port = <Your SMTP server port>
username = "USERNAME"
password = "PASSWORD"
```

