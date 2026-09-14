# Publora extension for Gemini CLI

Publish and schedule social media posts without leaving the terminal. One call
reaches LinkedIn, X, Instagram, Threads, TikTok, YouTube, Facebook, Bluesky,
Mastodon and Telegram.

## Install

```bash
gemini extensions install https://github.com/publora-team/gemini-cli-publora
```

On first use Gemini CLI opens a browser to sign in to Publora. There is no key
to paste and nothing to install locally: the extension points at the hosted
Publora MCP server, which supports OAuth discovery and dynamic client
registration.

## What you can ask for

- "Show my connected accounts"
- "Draft a post about today's release for LinkedIn and Mastodon"
- "Schedule it for Monday 9am UTC with the image at <url>"
- "List my scheduled posts and delete the one about the webinar"

## What it does

- Creates, updates and deletes posts, as drafts or on a schedule
- Attaches images and video by public link
- Carries per-network settings: YouTube title and privacy, Instagram cover,
  TikTok privacy, Telegram flags, Threads replies, LinkedIn visibility
- Reads post status and the accounts you connected
- Adds comments and reactions on LinkedIn, and reads LinkedIn statistics

## Account

You need a Publora account. The free plan covers 3 connected accounts and 15
posts a month, with no card, and it includes API and MCP access. X publishing
and webhooks are on the paid plan.

- Product: https://publora.com
- Docs: https://docs.publora.com
- Support: support@publora.com

## License

MIT
