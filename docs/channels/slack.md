# Slack

**Channel identifier:** `slack`

## Steps
```json
{
  "step": "telegram.send",
  "credential": "CREDENTIAL_NAME"
}
```

## How to connect

To set up the Slack channel for Notifico, follow these steps:

1. **Create a Slack App:**
      - Go to https://api.slack.com/apps
      - Click "Create New App" and choose "From scratch"
      - Give your app a name and select the workspace where you want to install it

2. **Configure Bot Token Scopes:**
      - In your app's dashboard, navigate to "OAuth & Permissions"
      - Scroll down to "Bot Token Scopes"
      - Add the following scope: `chat:write.public`

3. **Install the App:**
      - On the same "OAuth & Permissions" page, click "Install to Workspace"
      - Review the permissions and click "Allow"

4. **Get the OAuth Token:**
      - After installation, you'll be redirected back to the "OAuth & Permissions" page
      - Copy the "Bot User OAuth Token" (it starts with `xoxb-`)

5. **Add the Token to Notifico:**
      - Open your `credentials.toml` file
      - Add a new entry for Slack using this format:
        ```toml
        [slack.YOUR_CREDENTIAL_NAME]
        token = "xoxb-your-token-here"
        ```
      - Replace `YOUR_CREDENTIAL_NAME` with a meaningful name for this Slack connection
      - Paste your OAuth token in place of `xoxb-your-token-here`

6. **Use in Notifico:**
      - When configuring Notifico steps, use `slack` as the channel identifier
      - Reference your credential name in the step configuration

Now your Slack channel is ready to use!
