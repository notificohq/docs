# Quick start
The fastest way to deploy Notifico is Docker. We will use RabbitMQ as AMQP broker and PostgreSQL as database.

## Configure your credentials
First, you need to create a credential file that will provide all the necessary credentials.
In this example, we use SMTP server, because it is the easiest to configure.
Create a file named `credentials.toml` in Notifico root directory with the following contents:

```toml
[smtp.mailer1]
tls = true  # The flag indicating whether to use TLS (STARTTLS is supported, too)
host = "smtp.example.com"  # The address of your SMTP server.
port = 587  # The port number used by your SMTP server (commonly 25, 465, or 587).
username = "your_username@example.com"  # The username for authenticating with the SMTP server.
password = "your_password"  # The password associated with the SMTP username.
```

Replace all the values with your own.

## Run using docker compose

```shell
$ docker compose -f container/docker-compose.example.yml up --build
```

This command will build Notifico, start the dependencies and run all the necessary services.

The admin panel will be available here: http://localhost:8000

Now you can create event in "Events" section, template in "Templates" and then a pipeline in "Pipelines".

## Create your first pipeline
Go to the "Pipelines" section in your admin panel, click "+ Create". Select Project (Default Project), add an event, that you created above, and type `email` in chennel field.

Then you should create steps.
Example steps:
```json
[
  {
    "step": "templates.load",
    "templates": ["your_template_name"]
  },
  {
    "step": "smtp.send",
    "credential": "mailer1"
  }
]
```

The editor is not convenient right now, we will replace it with a simple JSON editor in the following releases.

Now, you can trigger the event.
