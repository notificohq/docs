# Quick start
The fastest way to deploy Notifico is Docker. We will use RabbitMQ as an AMQP broker and SQLite as a database.

Run in your terminal
```shell
$ git clone https://github.com/notificohq/notifico-example.git
$ cd notifico-example
```

## Configure your credentials
First, you need to create a credential file that will provide all the necessary credentials.
In this example, we use SMTP server, because it is the easiest to configure.

Open a file named `credentials.toml` in example directory and replace SMTP credentials with yours:

```toml
[smtp.mail1]
tls = true  # The flag indicating whether to use TLS (STARTTLS is supported, too)
host = "smtp.example.com"  # The address of your SMTP server.
port = 587  # The port number used by your SMTP server (commonly 25, 465, or 587).
username = "your_username@example.com"  # The username for authenticating with the SMTP server.
password = "your_password"  # The password associated with the SMTP username.
```

??? example "Example for Gmail"
    To use your Google account with SMTP, especially when using third-party applications like Notifico,
    it's recommended to create an App Password. This is a special password that allows the app to access your Google account
    securely without using your main account password. Here's how you can create an App Password for your Google account:

    1. **Enable 2-Step Verification:**
    Before you can create an App Password, you need to have 2-Step Verification enabled on your Google account.
    You can enable it by going to your Google Account settings, selecting "Security,"
    and then following the instructions under "2-Step Verification."

    2. **Create an App Password:**
        - Go to https://myaccount.google.com/apppasswords
        - Enter a new name for your App Password, for example `Notifico`.
        - Google will provide you with a 16-character password. This is your App Password.
    3. **Use the App Password:**
    Replace the password field in your credentials.toml file with the App Password you just generated.
    It should look something like this:

    ```toml
    [smtp.mail1]
    tls = true
    host = "smtp.gmail.com"
    port = 587
    username = "your_username@gmail.com"
    password = "your_app_password_here"
    ```

## Run using docker compose

```shell
$ docker compose up
```

This command will download Notifico, start the dependencies and run all the necessary services.

Now, Notifico is up and running and the admin panel will be available here: [http://localhost:8000](http://localhost:8000).

Now, you can create your Event, Template and Pipeline. Read

## Create a template

## Create your first pipeline
Go to the "Pipelines" section in your admin panel, click "+ Create". Select Project (Default Project), add an event, that you created above, and type `email` in chennel field.

??? example "Screenshot"
    ![example_create_pipeline.png](example_create_pipeline.png)

Then you can create steps.
Example steps:
```json linenums="1"
[
  {
    "step": "templates.load",
    "templates": ["your_template_name"]
  },
  {
    "step": "smtp.send",
    "credential": "mail1"
  }
]
```

The editor is not convenient right now, we will replace it with a simple JSON editor in the following releases.

Now, you can trigger the event.
