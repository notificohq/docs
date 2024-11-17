# Pipelines

Pipelines define how Notifico processes incoming events and sends notifications to different channels.

Each pipeline consists of a channel, events, and steps.

### Configuration

The pipeline configuration is defined in the `pipelines.yml` file. Here's an example of how to configure pipelines:

```yaml
events:
  - name: send_notification
pipelines:
  - channel: telegram
    events:
      - send_notification
    steps:
      - step: templates.load
        templates: [ "zerna.toml" ]
      - step: telegram.send
        credential: telegram_bot_1
  - channel: email
    events:
      - send_notification
    steps:
      - step: templates.load
        templates: [ "zerna.toml" ]
      - step: email.send
        credential: mailman_1
```

### Events

Events are the triggers that start the pipeline execution. In the example above, there's a single event named `send_notification`. You can define as many events as needed.

### Channels

Channels represent the communication mediums where notifications will be sent. In the example above, there are two channels: `telegram` and `email`. You can add as many channels as needed.

### Steps

Steps define the actions to be performed in each pipeline. In the example above, there are two steps for each channel:

1. `templates.load`: This step loads template files specified in the `templates` array.
2. `telegram.send` or `smtp.send`: These steps send notifications to the respective channels using the credentials specified.

### Credentials

Credentials are used to authenticate with the external services. In the example above, `telegram_bot_1` and `mailman_1` are the credentials defined in the `credentials.toml` file.

### More Pipelines

You can add more pipelines to handle different events and channels. Just follow the same pattern as shown in the example.
