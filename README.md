# BlinkWork MCP (Cursor / Grok Bot)

Thin connect package: remote HTTP MCP + one secret. No custom tools in v1.

## Get your token

1. Sign in at [blinkwork.com](https://www.blinkwork.com)
2. Open [Settings → Access Tokens](https://www.blinkwork.com/settings/tokens)
3. Generate a token (e.g. name it "Grok Bot" or "Cursor")
4. Paste it once into Plugins → Configure as `BLINKWORK_API_TOKEN` — never in chat

## What it does

- Points at `https://api.blinkwork.com/mcp`
- Asks for `BLINKWORK_API_TOKEN` via Plugins → Configure
- Ships one skill: verify with `whoami`, then optional `teammate.inbox` when that tool exists

## Install

Published on the Cursor Marketplace as **blinkwork**. After install, configure the token above, then ask the agent to run the BlinkWork connect check (`whoami`).

### Manual MCP (Grok CLI)

```bash
grok mcp add --transport http blinkwork https://api.blinkwork.com/mcp \
  --header "Authorization: Bearer ${BLINKWORK_API_TOKEN}"
```

## Layout

```
.cursor-plugin/plugin.json   # name + BLINKWORK_API_TOKEN variable
mcp.json                     # url + Bearer ${BLINKWORK_API_TOKEN}
skills/blinkwork-connect/    # whoami → optional inbox
README.md
```

## Notes

- Grok Bot loads plugins from the Cursor dashboard/marketplace (not local plugin folders).
- Rotate any token that was pasted into a chat.
