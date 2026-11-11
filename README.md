# Publora extension for Gemini CLI

Publish and schedule social media posts without leaving the terminal. One call
reaches LinkedIn, X, Instagram, Threads, TikTok, YouTube, Facebook, Bluesky,
Mastodon and Telegram.

## Install

```bash
gemini extensions install https://github.com/publora-team/gemini-cli-publora
```

Start Gemini CLI and sign in to Publora once:

```
/mcp auth publora
```

A browser window opens. There is no key to paste and nothing to install
locally: the extension points at the hosted Publora MCP server, which supports
OAuth discovery and dynamic client registration.

### No browser (SSH, CI)

OAuth needs a local browser. On a headless machine, create an API key in
[Publora](https://app.publora.com/dashboard/api), export it as
`PUBLORA_API_KEY` and add this to `~/.gemini/settings.json`. It takes
precedence over the extension's server of the same name:

```json
{
  "mcpServers": {
    "publora": {
      "url": "https://mcp.publora.com/mcp",
      "type": "http",
      "headers": { "Authorization": "Bearer $PUBLORA_API_KEY" }
    }
  }
}
```

## What you can ask for

- "Show my connected accounts"
- "Draft a post about today's release for LinkedIn and Mastodon"
- "Schedule it for Monday 9am UTC with the image at <url>"
- "List my scheduled posts and delete the one about the webinar"

## What it does

- Creates and updates posts as drafts, on a schedule or for immediate
  publishing, and deletes posts that have not been published
- Attaches images and video by public link
- Carries per-network settings: YouTube title and privacy, Instagram cover,
  TikTok privacy, Telegram flags, Threads replies, LinkedIn reposts
- Reads post status and the accounts you connected
- Adds comments and reactions on LinkedIn
- Reads statistics for Instagram, Threads, Mastodon and Bluesky

## Account

You need a Publora account. The free plan covers 3 connected accounts and 15
posts a month, with up to 3 scheduled at a time and 7 days ahead. It needs no
card and includes API and MCP access. X publishing and webhooks are on the paid
plan.

- Product: https://publora.com
- Docs: https://docs.publora.com
- Support: support@publora.com

## License

MIT
