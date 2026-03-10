# Kimi Claw User Guide

Welcome to Kimi Claw. This guide introduces Kimi Claw's core features and usage tips to help you build your own 24/7 personalized AI assistant.

---

## 1. Introduction to Kimi Claw

[OpenClaw](https://openclaw.ai/) is an AI assistant with unique personality and long-term memory capabilities. Now in Kimi, you can start chatting with OpenClaw via Kimi Claw.

### Deploy OpenClaw in One Click

If you don't have your own OpenClaw yet, you can first go to the **Create Kimi Claw** page to create your OpenClaw.

**Benefits:**
- Kimi deploys OpenClaw to the cloud with one click—no extra server purchase or command-line setup required
- Kimi automatically configures the Kimi K2.5 Thinking model and links your Kimi Code membership quota, so no additional API setup is needed. It also enables Kimi Web Search for web search capabilities
- One-click deployment is available on Allegretto plans and above. For details, see [Kimi Membership Plan](./membership-plan)

### Link to an Existing OpenClaw

- If you've already deployed OpenClaw, you can chat with it in Kimi by installing the Kimi plugin
- Go to the Kimi Claw page, choose "Link existing OpenClaw", then follow the steps to install the plugin on the device running OpenClaw. After that, you can talk to your OpenClaw in Kimi

---

## 2. Usage Tips

Many people treat Kimi Claw as a "tool that answers questions". In practice, it's a configurable assistant: set rules for persona and memory; teach methods to build habits; give a schedule to drive work forward.

### 2.1 Customize the Persona

Kimi Claw's reply style isn't fixed. With one instruction, you can change its role, tone, and format—more humorous, more rigorous, more like a product manager, or more like a study buddy. You can tune it from three angles:

**Customization Dimensions:**
- **Name and Identity**: Give it a new name and a role/job identity
- **Speaking Style**: Shorter, more polite, more playful, or more formal
- **Fixed Opening/Closing**: Add a standard opener, or end with one action item

**Examples:**
```
From now on, your name is 'Steven'. You are my information assistant. Start every reply with: "Good, then answer."
```

```
From now on, use a three-part format: conclusion, reasons, actionable steps. No fluff.
```

```
You are a rigorous investment research analyst. Mark uncertainty for every conclusion and include one risk note.
```

### 2.2 Learning Skills

Kimi Claw has a built-in **Clawhub Skill Library**. When you want it to do a task, you don't have to teach from scratch—ask it to find and install a high-quality Skill, like adding a dedicated module.

**Use Cases:**
- **Information Synthesis**: News briefs, competitor comparisons, meeting notes templates
- **Analysis**: Stock/industry mapping, data interpretation, risk extraction
- **Workflow**: A complete set of processes from requirements → decomposition → output → review

**Usage Examples:**
- Check out what opportunities there are in recent stocks. First, go search for and obtain the Skill related to Class A Share market data and analysis ideas, then install and analyze using the Skill.
- Conduct a competing product analysis. First, find a suitable competing product analysis Skill, then ask me for necessary information step by step.

**Teach Your Own Skills:**

You can also teach it your own best practices, or share Skills you already have. Teach it by providing:
- **Process**: How you normally do this work (what to search first, how to judge, how to present)
- **Standards**: What you care about most (accuracy, speed, actionability, risk control)
- **Templates**: Your preferred output format (structure, fields, length)

### 2.3 Set a Scheduled Task

Kimi Claw can run scheduled tasks. With clear timing and output requirements, it becomes an automatic reminder and an information radar. For reliable execution, state three things at once:

**Essential Information:**
- **Time**: When to run (specific date / daily time / day of week)
- **Output**: How to deliver (bullets, table, template, length, language)
- **Constraints**: Must/must-not rules (≤200 words, Chinese only, include a risk note, only 3 items, etc.)

**Examples:**
```
Every day at 9:00 AM, summarize the latest market news: 3 bullets + 1 risk note, in Chinese, within 200 words.
```

```
Remind me in 1 hour to continue today's daily report, and include the template (four-part).
```

```
Tonight at 22:30, remind me: shut down my computer, wash up, get ready to sleep. Use a gentle tone.
```

**Recommended Template:**
```
At [time], do [task], output [format], and follow [constraints].
```

If you state all three clearly, Kimi Claw's execution is more consistent and it's easier to build long-term automation habits.

### 2.4 Set up Telegram Bot

The built-in Skill of Kimi Claw will assist you in configuring different channels. You can send "I want to configure the Telegram robot" and the bot will provide you with a step-by-step plan. [More detailed steps](./telegram-setup)

**Configuration Process:**

1. Open Telegram and chat with @BotFather (confirm the handle is exactly @BotFather)
2. Run `/newbot`, follow prompts, and save the token
3. Tell Kimi Claw your Telegram token, like: `my telegram bot token is 123456:xxxxxxxxx`
4. In settings, restart Kimi Claw
5. Find your bot in chat, you will receive a pairing code command. Send it to Kimi Claw, like: `openclaw pairing approve telegram XXXXXXXX`, and it will help you complete the configuration
6. Then you can talk to your Kimi Claw in Telegram

**Group Chat Setting:**

If your bot can't respond in group chat, send Kimi Claw this code to make sure groupPolicy is open. Replace botToken with your token:

```json
{
  "telegram": {
    "enabled": true,
    "dmPolicy": "open",
    "allowFrom": ["*"],
    "botToken": "123456:xxxxx",
    "groups": {
      "*": {
        "requireMention": true
      }
    },
    "groupPolicy": "open",
    "streamMode": "partial"
  }
}
```

Then in settings click "Restart Kimi Claw". Invite your bot to group chat and promote it to admin so that it can receive messages. Then @your bot and it will respond.

If you want to set other channels, find the command in "Chat Channels - OpenClaw" and send it to Kimi Claw. We will support Terminal UI very soon.

---

## 3. Frequently Asked Questions

### 3.1 Can I use terminal to control Kimi Claw?

- Kimi Claw supports web SSH. Access via **[Settings] → [Open Terminal]**, then enter your commands
- You can also tell the Bot what commands you need executed, and it will run them for you
- **Note**: Terminal and plugins share the same communication channel. Restarting OpenClaw Gateway makes the terminal lose connection

### 3.2 Is Kimi Claw available on all platforms?

Kimi Claw is currently available on the web and mobile app (Android/iOS). Please download the newest version (2.6.0).

### 3.3 What if Kimi Claw doesn't reply to messages?

- It may have been disconnected from the server—refresh the page
- Try "Restart Kimi Claw" in Settings. After it restarts, message Kimi Claw again to see if it responds
- If neither works, try "Auto-fix Kimi Claw" in Settings
<img width="772" height="1076" alt="image" src="https://github.com/user-attachments/assets/9e35fd07-c172-4656-848b-d523392f4622" />


### 3.4 Can Kimi Claw send and receive files to/from me?

- You can send images and files to Kimi Claw in Kimi; it will use tools to view them
- The latest version of Kimi Claw plugin supports sending files to you in Kimi. If your Kimi Claw cannot send files to you, please upgrade the plugin to the latest version
- You can use other channels to obtain the files you need

### 3.5 How to uninstall the Kimi plugin in a linked OpenClaw?

**Warning**: The following command is only intended for uninstalling the Kimi plugin on linked OpenClaw devices. Please do not run this command on a one-click deployed Kimi Claw, as doing so will delete your connection to Kimi Claw and become unrecoverable.

You can run this command on the linked OpenClaw device to uninstall the Kimi plugin:

```bash
bash <(curl -fsSL https://cdn.kimi.com/kimi-claw/uninstall.sh)
```


