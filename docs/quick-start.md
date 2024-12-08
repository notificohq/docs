# Quick start
The fastest way to deploy Notifico is Docker. We will use RabbitMQ as an AMQP broker and SQLite as a database.

Run in your terminal
```shell
$ curl -o docker-compose.yml https://raw.githubusercontent.com/notificohq/notifico/refs/heads/main/examples/docker-compose.simple.yml
```

## Configure your credentials
First, you need to set all the necessary service credentials.
In this example, we use SMTP server because it is the easiest to configure.

Open `docker-compose.yml`, that you have just downloaded and replace SMTP credentials with yours:

```yaml
NOTIFICO_CRED_MAIL1: smtp:YOUR_SMTP_USERNAME:YOUR_SMTP_PASSWORD@YOUR_SMTP_SERVER:587?tls=true
```

If your SMTP username contains "@" sign, replace it with %40. All other characters must be urlencoded as well.

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
    Replace the password field in your NOTIFICO_CRED_MAIL1 variable with the App Password you just generated.
    It should look something like this:

    ```yaml
    NOTIFICO_CRED_MAIL1: smtp:your_username%40gmail.com:your_app_password_here@smtp.gmail.com:587?tls=true
    ```

## Run using docker compose

```shell
$ docker compose up
```

This command will download Notifico, start the dependencies and run all the necessary services.

Now, Notifico is up and running and the admin panel will be available here: [http://localhost:8000](http://localhost:8000).

Now, you can create your [Event, Template and Pipeline](pipeline.md).
