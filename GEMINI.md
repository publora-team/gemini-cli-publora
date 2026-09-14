# Publora

Publora publishes and schedules social media posts. These tools work on the
accounts the signed-in user has connected in Publora.

## How to work with these tools

- Call `list_connections` first and copy each `platformId` exactly as returned.
  The ids look like `linkedin-n20H8w1Omj` or `mastodon-117189156651500869`, and
  they cannot be guessed or shortened.
- Times are ISO 8601 in UTC, for example `2026-10-20T09:00:00Z`. A post without
  a scheduled time is saved as a draft and is not published.
- Instagram, TikTok and YouTube need media. Pass public https links in
  `mediaUrls` and Publora downloads the files itself.
- Per-network options belong in `platformSettings`: an Instagram cover, a
  YouTube title and privacy, TikTok privacy, Telegram flags, a Threads reply
  setting, LinkedIn visibility.
- Pinterest can be connected but not published to.
- To check the connection without posting anywhere, create a post with the
  platform `publora-playground`. The request is accepted and discarded.

## Before publishing

Show the user the text, the accounts and the time, and publish only after they
confirm. A published post cannot be recalled from the social network: deleting
it in Publora removes the record, not the post.
