---
name: blinkwork-connect
description: Use after installing the BlinkWork plugin — verify the MCP connection with whoami, then optionally poll teammate.inbox when that tool exists.
---

# BlinkWork connect

## When to use

After the BlinkWork plugin is installed and `BLINKWORK_API_TOKEN` is configured.

## Token source

If the token is missing or rejected, send the user here (do not ask them to paste it in chat):

1. Sign in at https://www.blinkwork.com
2. Open https://www.blinkwork.com/settings/tokens
3. Generate or copy a token
4. Set it under Plugins → Configure as `BLINKWORK_API_TOKEN` (or via secret-request)

## Steps

1. Call `whoami` on the BlinkWork MCP. Confirm principal and permitted skills.
2. If `teammate.inbox` (or equivalent) is in `tools/list`, run one poll and report unread count + top items.
3. If that tool is missing, say so — connect path still works; teammate features need the build that ships them.
4. Never store tokens in skills, memory, or transcripts.

## Out of scope

Do not invent BlinkWork tools.
