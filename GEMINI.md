# Publora

Publora publishes and schedules social media posts. These tools work on the
accounts the signed-in user has connected in Publora.

## How to work with these tools

- Call `list_connections` first and copy each `platformId` exactly as returned.
  The ids look like `linkedin-n20H8w1Omj` or `mastodon-117189156651500869`, and
  they cannot be guessed or shortened.
- Call `account_context` before a batch of posts: it returns the plan, the
  quotas and the latest date that can be scheduled. The free Starter plan
  allows 15 posts a month, 3 scheduled at a time, 7 days ahead, and no X.
- Times are ISO 8601 in UTC or with an explicit offset, for example
  `2026-10-20T09:00:00Z`. A post with neither `scheduledTime` nor
  `publishNow: true` is saved as a draft. `publishNow: true` publishes
  immediately, so omit `scheduledTime` with it.
- Instagram, TikTok and YouTube need media. Pass public https links in
  `mediaUrls` and Publora downloads the files itself.
- Per-network options belong in `platformSettings`: an Instagram cover, a
  YouTube title and privacy, TikTok privacy, Telegram flags, a Threads reply
  setting, LinkedIn reposts.
- Pinterest can be connected but not published to.
- To check the connection without posting anywhere, call `create_post` with
  `publora-playground` as the only platform. The request is accepted and
  discarded.

## Before publishing

Show the user the text, the accounts and the time, and publish only after they
confirm. A published post cannot be recalled: `delete_post` works only on
unpublished posts, refuses published or in-progress ones with HTTP 409, and
never removes anything from a social network.
