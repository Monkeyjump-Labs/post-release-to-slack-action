# post-release-to-slack-action

A GitHub Action to post a release to Slack for easy review.

## Usage

To use this action, add a GitHub Action to your repository that is similar to the below:

```yaml
- uses: Monkeyjump-Labs/post-release-to-slack-action
  id: post_release_to_slack
  name: Post Release Info to Slack
  with:
    release_number: ${{ github.event.release.id }}
    channel: C01234567
    slack_bot_token: ${{ secrets.SLACK_BOT_TOKEN }}
```

This will trigger a post to the channel with the release info.

### Channel ID or name

`channel` accepts either a Slack channel ID (e.g. `C01234567`) or a
human-readable channel name (e.g. `release-notes` or `#release-notes`). When a
name is provided it is resolved to an ID via `conversations.list` before
posting, so the bot token needs the `channels:read` scope (and `groups:read`
for private channels). The bot must also be a member of the channel for
`chat.postMessage` to succeed.
