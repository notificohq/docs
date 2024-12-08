# Pushover

**Contact:** `pushover:USER_KEY`

**Credential:** `pusoover:API_TOKEN`

**Channel:** `pushover`

## Template parameters
```yaml
body: "Template {{ parameter }}" # body of Pushover message
title: "Title" # title, displayed in Push notification
```

## Steps
### Step: `pushover.send`
```json
{
  "step": "pushover.send",
  "credential": "CREDENTIAL_NAME"
}
```

## Connecting to Pushover
To configure your Pushover account, you have to create a new application [here](https://pushover.net/apps/build).
You will get "API Token", that you use in credential.
