---
title: "Core concepts & terminal"
slug: "concepts"
order: 3
extract_headings: false
preview: false
---

<SeoMeta
  title="Core concepts \u0026 terminal - Kimi Help Center"
  description="Image: 截图30"
  pageUrl="https://www.kimi.com/help/kimi-claw/concepts"
/>

## Key concepts

| Concept | Description |
|---------|-------------|
| **Memory** | Kimi Claw's long-term memory system. Stores your preferences, habits, and important information across conversations. |
| **Skills** | Installable capability modules from the ClawHub library that give Kimi Claw domain-specific expertise. |
| **HEARTBEAT** | Scheduled background tasks that run on a timer — useful for recurring reminders, data pulls, and digests. |
| **Identity** | Kimi Claw's role definition: name, profession, persona. Fully customizable by you. |
| **Soul** | Core personality traits and behavioral principles that shape Kimi Claw's interaction style. |
| **Tools** | The set of capabilities Kimi Claw can invoke — web search, file handling, code execution, and more. |
| **User** | The relationship definition between you and Kimi Claw, which governs interaction patterns and information sharing. |

## Terminal

<Frames
  src="./images/concepts/screenshot-30.png"
  alt="screenshot 30"
/>

You can open a command-line interface via **Settings → Terminal** on the web, and run commands to control Kimi Claw directly.

Alternatively, just tell Kimi Claw what command to run in plain language — it will execute it for you.

> Note: The Terminal and plugins share the same connection channel. Restarting the OpenClaw gateway will disconnect the Terminal.

## Command reference

### System

| Command | Description |
|---------|-------------|
| `/help` | Show help information |
| `/status` | View current system status |
| `/ping` | Test whether the connection is alive |
| `/cron` | Manage scheduled tasks |
| `/config` | View or edit configuration |
| `/new` | Start a new conversation (clears current context) |
| `/reset` | Reset Kimi Claw |
| `/compact` | Compress the current conversation context |
| `/stop` | Stop the currently running task |

### Skills

| Command | Description |
|---------|-------------|
| `/skills` | Browse, install, and manage skills |

### Scheduled tasks

| Command | Description |
|---------|-------------|
| `/cron` | View and manage the task schedule |

### Memory

| Command | Description |
|---------|-------------|
| `/memory` | View and manage long-term memory |

### Configuration & debugging

| Command | Description |
|---------|-------------|
| `/config` | View or edit system configuration |
| `/logs` | View runtime logs |
| `/debug` | Enable debug mode for detailed diagnostics |
