# post-release-to-slack-action
A github action to post a release to slack for easy review.

## Usage

To use this action, add a github action to your repository that is similar to the below:

```
- uses: Monkeyjump-Labs/post-release-to-slack-action
  id: post_release_to_slack
  name: Post Release Info to Slack
  with:
    release_number: ${{ github.event.release.id }}
    channel_id: 12345678
    slack_bot_token: ${{ secrets.SLACK_BOT_TOKEN }}
```

This will trigger a post to the channel with the release info.
