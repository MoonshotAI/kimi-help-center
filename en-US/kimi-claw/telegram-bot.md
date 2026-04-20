---
title: "Set up a Telegram bot"
slug: "telegram-bot"
order: 4
extract_headings: false
preview: false
---

<SeoMeta
  title="Set up a Telegram bot - Kimi Help Center"
  description="Connect Kimi Claw to Telegram so you can chat with it from any device — no browser required."
  pageUrl="https://www.kimi.com/help/kimi-claw/telegram-bot"
/>

Connect Kimi Claw to Telegram so you can chat with it from any device — no browser required.

## Step-by-step setup

### 1. Create a bot with BotFather

1. Open Telegram and start a chat with [@BotFather](https://t.me/BotFather).
2. Send `/newbot`.
3. Follow the prompts to choose a **display name** and a **username** (must end in `bot`).
4. BotFather will reply with a **bot token** — copy it and keep it safe.

### 2. Connect the bot to Kimi Claw

1. Open your Kimi Claw conversation on [kimi.com](https://kimi.com).
2. Tell Kimi Claw: _"Here's my Telegram bot token: `<your-token>`. Please set up the Telegram connection."_
3. Kimi Claw will save the token to its configuration.

### 3. Restart and pair

1. Restart Kimi Claw — either ask it to restart, or go to **Settings → Restart Kimi Claw**.
2. Once it's back online, open your new Telegram bot and send a message.
3. Kimi Claw will respond — the pairing is complete.

## Tips

- **Privacy mode:** By default, bots in Telegram groups only see messages that mention them or start with `/`. If you want Kimi Claw to see all group messages, disable Privacy Mode via BotFather (`/setprivacy → Disable`).
- **Multiple bots:** You can create multiple Telegram bots and connect them to the same Kimi Claw instance.
- **Token security:** Never share your bot token publicly. If compromised, revoke it via BotFather (`/revoke`) and configure a new one.
