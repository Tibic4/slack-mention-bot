# slack-mention-bot

A Slack bot that reminds you of posts that you have not reacted to with a specified reaction when you are mentioned.

You can prevent the omission of correspondence.

## Installation

### Slack bot settings

- Grant the following permissions to **Bot Token Scopes** in **Scopes** of **OAuth & Permissions**

  - chat:write

- Grant the following permissions to **User Token Scopes** in **Scopes** of **OAuth & Permissions**

  - channels:history
  - channels:read
  - groups:history
  - groups:read
  - im:history
  - im:read
  - mpim:history
  - mpim:read

### Cloud Run settings

- Create a service account
  - Grant the following permissions
    - Cloud Run Administrator
    - Cloud Run Service Agent
    - Storage Administrator
- Generate a service account key

### GitHub Actions settings

- Register **Repository secrets** from **Secrets** > **Actions** in **Setting** of the remote repository
  - `GCP_CREDENTIALS`
    - `cat /path/to/credentils_key.json | base64 | pbcopy` and copy to clipboard
  - `GCP_PROJECT_ID`
  - `GCP_REGION`
  - `REACTION_NAME`
    - If :heavy-check-mark:, register heavy-check-mark
  - `SERVICE_NAME`
  - `SLACK_BOT_TOKEN`
  - `SLACK_CHANNEL_ID`
    - Channel to post reminder
  - `SLACK_USER_ID`
    - Your Slack member ID
  - `SLACK_USER_TOKEN`

### Push this source code to GitHub

- Since the application is automatically deployed to Cloud Run by GitHub Actions, push this source code to GitHub

### Start Cloud Scheduler

- Start Cloud Scheduler with the following configuration
  - Specify the service account for Cloud Run management
