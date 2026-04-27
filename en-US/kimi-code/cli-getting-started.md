---
title: "Getting started"
slug: "cli-getting-started"
order: 3
extract_headings: false
preview: true
preview_content: "Set up Kimi Code with CLI, VS Code, or third-party agents using your membership benefits."
---

<SeoMeta
  title="Kimi Code overview - Kimi Help Center"
  description="Set up Kimi Code with CLI, VS Code, or third-party agents using your membership benefits."
/>

Kimi Code CLI is an AI Agent that runs in your terminal, helping you complete software development tasks and terminal operations. It can read and edit code, execute Shell commands, search and scrape the web, and autonomously plan and adjust its actions during execution.

## Use cases

- **Write and Modify Code**: Implementing new features, fixing bugs, and refactoring code.
- **Understand Projects**: Exploring unfamiliar codebases and answering questions about architecture and implementation.
- **Automate Tasks**: Batch processing files, executing builds and tests, and running scripts.

If you have any issues suggestions, provide feedback on [GitHub Issues](https://github.com/MoonshotAI/kimi-cli/issues) 

## Ways to use

| Method | Command | Description |
| --- | --- | --- |
| Interactive Terminal | `kimi` | Chat with the AI in your terminal — ideal for daily development |
| Browser Interface | `kimi web` | Open an interactive UI in your browser |
| Agent Integration | `kimi acp` | Integrate into your IDE via the ACP protocol |

## Installation

Run the installation script to complete the setup. The script will first install [uv](https://docs.astral.sh/uv/) and then install Kimi Code CLI via uv:

<Frames
  src="./images/cli-getting-started/screenshot-23.png"
  alt="screenshot 23"
/>

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "curl -LsSf https://code.kimi.com/install.sh | bash",
    },
  ]}
/>

After installation, verify that it was installed successfully:

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "kimi --version",
    },
  ]}
/>

> If the `kimi` command is not found, try reopening your terminal or running `source ~/.bashrc` (or `~/.zshrc`).

## First run

### Startup and login

Navigate to your project directory:

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "cd /path/to/your/project",
    },
  ]}
/>

Run the `/login` command to complete authorization:

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "/login",
    },
  ]}
/>

   The system will prompt you to select a login method — follow the instructions to complete authorization.

### Core Capabilities

You can interact with Kimi Code CLI using natural language:

<ColumnsContent
  columns={[
    {
      title: "Ask Questions",
      description: "Understand project architecture and entry points.",
      pageUrl: "/help/core-operations/asking-questions",
      type: "microscope",
    },
    {
      title: "Modify Code",
      description: "Let Kimi write features or fix bugs with your approval.",
      pageUrl: "/help/core-operations/editing-code",
      type: "code",
    },
    {
      title: "Run Commands",
      description: "Execute tests and automate terminal tasks.",
      pageUrl: "/help/core-operations/executing-commands",
      type: "okcomputer",
    },
  ]}
/>

## Common Commands Cheat Sheet

| Command | Description |
|------|------|
| `kimi` | Start interactive dialogue |
| `kimi web` | Open browser graphical interface |
| `/login` | Configure or switch API sources |
| `/usage` | Check remaining balance and quota |
| `/help` | View all commands and shortcuts |
| `Ctrl-J` | New line (do not submit) |
| `Ctrl-C` / `Ctrl-D` | Interrupt current operation / Exit |

## FAQ 

**I entered my API Key, but it says authentication failed.**

First, confirm that your Key and Base URL belong to the same platform. `api.kimi.com` and `api.moonshot.cn` are two completely independent account systems, and their API Keys are not interchangeable:

**The `kimi` command is not found after installation.**

The installation script adds `kimi` to your PATH, but you need to restart the terminal or run `source ~/.bashrc` (or `source ~/.bashrc`) for it to take effect. If it's still not found, check if `~/.local/bin` is in your PATH.

**The browser did not pop up after running `/login`.**

In a remote server or headless environment, `/login` will display a URL. Manually copy it into your browser to complete the authorization.

## Upgrade and uninstallation

Upgrade to the latest version:

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "uv tool upgrade kimi-cli --no-cache",
    },
  ]}
/>

Uninstall Kimi Code CLI:
<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "uv tool uninstall kimi-cli",
    },
  ]}
/>