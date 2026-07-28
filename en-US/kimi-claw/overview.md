---
title: "Kimi Claw overview"
slug: "overview"
order: 1
extract_headings: false
preview: true
preview_content: "Deploy and manage your own Kimi Claw AI assistant in the cloud with one-click setup."
---

<SeoMeta
  title="Kimi Claw overview - Kimi Help Center"
  description="Deploy and manage your own Kimi Claw AI assistant in the cloud with one-click setup."
/>

# Product overview

<Callout type="info">
**Kimi Claw** is an AI assistant with a unique personality and persistent long-term memory. Through Kimi Claw, you can create, deploy, and chat with your own OpenClaw instance directly from Kimi.
</Callout>

<Frames
  src="./images/overview/claw.png"
  alt="Claw"
/>

## One-click cloud deploy

Don't have an OpenClaw yet? Head to [kimi.com/bot](https://kimi.com/bot) to create one. Kimi deploys it to the cloud for you — no server purchases, no command-line setup.

<Callout type="warning">

- One-click deploy requires an **Allegretto or higher** plan. [Membership Plans](https://www.kimi.com/membership/pricing).

</Callout>

- Kimi automatically provisions the **Kimi K2.6 model**, connects your **Kimi membership** credits/benefits, and enables Kimi Web Search — no separate API configuration needed.
- To switch to the **Kimi K3** model, change the model configuration in Kimi Claw settings, or see [Switch to the Kimi K3 model](#switch-to-k3).
- Kimi Claw can be deployed directly to Telegram and other chat platforms.

## Getting started

1. Sign in at [kimi.com/bot](https://kimi.com/bot)
2. Click **Create** to launch a new Kimi Claw
3. Wait for automatic setup to complete (usually a few minutes)
4. Customize your Kimi Claw's name and persona
5. In **Settings → Chat Channels**, connect the platforms you want to use (e.g., Telegram)

## Link an existing OpenClaw

If you've already self-hosted an OpenClaw instance, you can connect it to Kimi by installing the Kimi plugin:

1. Go to [kimi.com/bot](https://kimi.com/bot) and select **Link Existing OpenClaw**
2. Follow the instructions to install the plugin on your OpenClaw device
3. Once connected, you can chat with your OpenClaw through Kimi

<a id="switch-to-k3"></a>
## Switch to the Kimi K3 model

Kimi Claw uses the **Kimi K2.6 model** by default. If you want to use **Kimi K3**, run the commands below to update your local OpenClaw configuration.

```bash
# 1. Back up the current config
cp /root/.openclaw/openclaw.json /root/.openclaw/openclaw.json.bak.k3

# 2. Add the k3 model and switch the default model (example uses jq)
jq '
  (.models.providers["kimi-coding"].models // .models.providers.kimi-coding.models) |= . + [{
    "id": "k3",
    "name": "k3",
    "input": ["text", "image"],
    "reasoning": true,
    "contextWindow": 1048576,
    "maxTokens": 65536
  }]
  | .agents.defaults.model.primary = "kimi-coding/k3"
' /root/.openclaw/openclaw.json > /tmp/openclaw.json.tmp \
  && mv /tmp/openclaw.json.tmp /root/.openclaw/openclaw.json

# 3. Restart OpenClaw
openclaw gateway restart

# 4. Verify
session_status
```

After running the commands, confirm that `session_status` shows `model` as `kimi-coding/k3` and the `context` limit as `1.0m`.

<Callout type="warning">
The configuration file path may vary depending on your installation method. Replace `/root/.openclaw/openclaw.json` with the actual path on your system. Be sure to back up the file before making changes.
</Callout>
