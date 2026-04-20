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
  pageUrl="https://www.kimi.com/help/kimi-code/cli-getting-started"
/>

Kimi Code CLI is a terminal-based AI agent that helps you with software development tasks and terminal operations. It can read and edit code, execute shell commands, search and fetch web pages, and autonomously plan and adjust its approach during execution.

## Use cases

- **Write and Modify Code**: Describe your requirements and the AI will automatically write and modify code.
- **Understand Projects**: Quickly grasp project architecture, code logic, and file purposes.
- **Automate Tasks**: Batch code modifications, documentation, test generation, and other repetitive work.

## Ways to use

| Method | Command | Description |
| --- | --- | --- |
| Interactive Terminal | `kimi` | Chat with the AI in your terminal — ideal for daily development |
| Browser Interface | `kimi web` | Open an interactive UI in your browser |
| Agent Integration | `kimi acp` | Integrate into your IDE via the ACP protocol |

## Installation

Run the following command in your terminal to install Kimi Code CLI:

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

1. Navigate to your project directory:

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "cd /path/to/your/project",
    },
  ]}
/>

2. Launch Kimi Code CLI:

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "kimi",
    },
  ]}
/>

3. Run the `/login` command to complete authorization:

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

4. Once configured, you can start chatting with the AI.

## Generate AGENTS.md

Run the `/init` command in your project directory — Kimi Code CLI will automatically scan the project structure and generate an `AGENTS.md` file:

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "/init",
    },
  ]}
/>

`AGENTS.md` provides the AI with project context such as background information, build steps, and coding conventions, helping the AI understand your project more accurately.
