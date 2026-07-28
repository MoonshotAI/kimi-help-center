---
title: "Getting started"
slug: "cli-getting-started"
order: 3
extract_headings: false
preview: true
preview_content: "Kimi Code CLI installation, login, and getting-started guide."
---

<SeoMeta
  title="Kimi Code CLI Installation & Quick Start - Kimi Help Center"
  description="Get started with Kimi Code CLI: install commands, terminal and browser usage, first-time login, and generate AGENTS.md with /init."
/>

# Getting started with Kimi Code CLI

Kimi Code CLI is an AI agent that runs in the terminal, helping you carry out software development tasks and day-to-day terminal operations — reading and modifying code, running shell commands, searching files, fetching web pages, and autonomously planning and adjusting its next steps based on feedback as it works.

It fits scenarios such as:

- **Writing and modifying code**: implementing new features, fixing bugs, completing refactors
- **Understanding a project**: exploring an unfamiliar codebase and answering questions about architecture and implementation
- **Automating tasks**: batch-processing files, running builds and tests, chaining multiple scripts together

The CLI is written in TypeScript, distributed via npm, and runs on Node.js.

## Before you start

- **Operating system**: macOS, Linux, or Windows (via PowerShell)
- **Kimi account**: an active Kimi membership subscription, or a callable API key

<Callout type="tip">
Kimi Code CLI is a fully interactive TUI application. For the best visual experience, run it in a terminal with true-color and ligature support, such as [Kitty](https://sw.kovidgoyal.net/kitty/) or [Ghostty](https://ghostty.org/).
</Callout>

## Installation

Two installation options are available: the official install script (recommended, no pre-installed Node.js required) and a global npm install.

### Install script (recommended)

macOS / Linux:

<Frames
  src="./images/cli-getting-started/screenshot-23.png"
  alt="Installing Kimi Code CLI"
/>

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "curl -fsSL https://code.kimi.com/kimi-code/install.sh | bash",
    },
  ]}
/>

Windows (PowerShell):

<CodePreview
  files={[
    {
      name: "command.ps1",
      language: "powershell",
      content: "irm https://code.kimi.com/kimi-code/install.ps1 | iex",
    },
  ]}
/>

The script automatically downloads the latest release, verifies the checksum, and places the `kimi` executable on your `PATH`.

<Callout type="tip">
On Windows, install [Git for Windows](https://gitforwindows.org/) before first launch. Kimi Code CLI uses the bundled Git Bash as its shell environment; if Git Bash is installed in a custom location, set `KIMI_SHELL_PATH` to the absolute path of `bash.exe`.
</Callout>

### npm installation

If you already have Node.js 22.19.0 or later installed, you can install directly via npm:

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "node --version\nnpm install -g @moonshot-ai/kimi-code",
    },
  ]}
/>

Or with pnpm:

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "pnpm add -g @moonshot-ai/kimi-code",
    },
  ]}
/>

### Verify installation

After installation, verify that the executable is ready:

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "kimi --version",
    },
  ]}
/>

<Callout type="tip">
If the `kimi` command is not found, try reopening your terminal or running `source ~/.bashrc` (or `~/.zshrc`).
</Callout>

> Because of macOS Gatekeeper, the first run of `kimi` may take noticeably longer. You can speed up subsequent launches by adding your terminal app to **System Settings → Privacy & Security → Developer Tools**.

## Upgrade and uninstall

**Upgrade**: run `kimi upgrade` — the CLI checks for the latest version and presents update options. Choose `Install update now` to upgrade based on your current install source. You can also upgrade directly via the package manager:

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "npm install -g @moonshot-ai/kimi-code@latest",
    },
  ]}
/>

**Uninstall**: if you installed via the script, delete the `kimi` executable. If you installed via npm:

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "npm uninstall -g @moonshot-ai/kimi-code",
    },
  ]}
/>

## First launch

### Interactive terminal

Move into your project directory and run `kimi` to start the interactive UI:

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "cd your-project\nkimi",
    },
  ]}
/>

### Single instruction

To run a single instruction without entering the interactive UI, use `-p`:

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "kimi -p \"Take a look at this project's directory structure\"",
    },
  ]}
/>

### Resume session

To resume the previous session, add `-C`:

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "kimi -C",
    },
  ]}
/>

### First login

On first launch you need to configure an API source. In the interactive UI, enter `/login` to begin the login flow:

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "/login",
    },
  ]}
/>

`/login` opens a platform selector supporting two options:

- **Kimi Code (OAuth)** — device-code flow; open the link on any device, sign in, and enter the code to authorize
- **Kimi Platform API key** — enter an API key from `platform.kimi.com` or `platform.kimi.ai`

To sign out, enter `/logout` to clear the current credentials.

<Callout type="tip">
If you want to connect Anthropic, OpenAI, Google, or other providers, edit `~/.kimi-code/config.toml` directly to configure the API key. For the full reference of all config options, see environment variables and configuration overrides documentation.
</Callout>

## Generate AGENTS.md

Run the `/init` command in your project directory. Kimi Code CLI will automatically scan the project structure and generate an `AGENTS.md` file:

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "/init",
    },
  ]}
/>

`AGENTS.md` is used to provide AI with project background information, build steps, code conventions, and other context to help AI understand your project more accurately.

## Your first conversation

Once logged in, describe a task in natural language. A good starting point is to let Kimi Code CLI familiarize itself with the project:

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "Take a look at this project's directory structure and briefly describe what each directory is for.",
    },
  ]}
/>

Kimi Code CLI automatically calls file-reading, search, and other tools to browse the relevant content before responding. Read-only operations are executed automatically by default without requiring confirmation. For operations that modify files or run shell commands, it asks for your confirmation before proceeding.

You can also describe a more concrete task directly:

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "Add a function in src/utils that converts any string to kebab-case, and add a unit test for it.",
    },
  ]}
/>

Kimi Code CLI plans the steps, modifies the code, runs the tests, and tells you what it did at each step.

<Callout type="tip">
Not sure what to do? Type `/help` at any time to open the built-in command and keyboard shortcut panel. Use `↑`/`↓` to browse and `Esc` to close. To exit, type `/exit`, press `Ctrl-C` twice, or press `Ctrl-D` with the input box empty.
</Callout>

## Common commands and keyboard shortcuts

### Session commands

| Command | Description |
| --- | --- |
| `/new` | Start a new session, clearing the current context |
| `/sessions` | Browse session history and choose one to resume |
| `/model` | Switch the current model |
| `/compact` | Manually compress the context to free up tokens |
| `/fork` | Fork the current session, keeping history but continuing independently |

### Most-used keyboard shortcuts

| Shortcut | Description |
| --- | --- |
| `Esc` | Interrupt streaming output / close a popup |
| `Ctrl-C` | Interrupt output; press twice while idle to exit |
| `Shift-Tab` | Toggle Plan mode |
| `Ctrl-S` | Inject a message mid-stream without waiting for the current response to finish |
| `Ctrl-O` | Collapse / expand tool output |

For the full list, type `/help` or visit [Interaction & input](/kimi-code/cli-interaction).

## Where data is stored

Kimi Code CLI stores its local data under `~/.kimi-code/` by default — config files, session records, logs, and the update cache. To move it elsewhere, point to a new path via the `KIMI_CODE_HOME` environment variable. For the full directory layout, see environment variables documentation.

## FAQ

**I entered my API Key, but it says authentication failed.**

First, confirm that your Key and Base URL belong to the same platform. `api.kimi.com` and `api.moonshot.cn` are two completely independent account systems, and their API Keys are not interchangeable:

| Platform | Base URL | Billing | Key creation |
|------|---------|---------|-------------|
| **Kimi Code** | OpenAI compatible: `https://api.kimi.com/coding/v1`<br> Anthropic compatible: `https://api.kimi.com/coding/` | Kimi membership subscription (includes credits) | [Kimi Code Console](https://www.kimi.com/code/console) |
| **Kimi Open Platform** | `https://api.moonshot.cn/v1` | Pay-as-you-go | [Kimi Open Platform](https://platform.kimi.com) |

**The `kimi` command is not found after installation.**

The installation script adds `kimi` to your PATH, but you need to restart the terminal or run `source ~/.bashrc` (or `source ~/.zshrc`) for it to take effect. If it's still not found, check if `~/.local/bin` is in your PATH.

**The browser did not pop up after running `/login`.**

In a remote server or headless environment, `/login` will display a URL. Manually copy it into your browser to complete the authorization.

If you have any issues or suggestions, provide feedback on [GitHub Issues](https://github.com/MoonshotAI/kimi-cli/issues).

## Next steps

- [Interaction & input](/kimi-code/cli-interaction) — input box operations, approval flow, Plan mode, and YOLO mode explained
- [Sessions & context](/kimi-code/cli-sessions) — resuming sessions, compressing context, exporting sessions
- [Common use cases](/kimi-code/cli-use-cases) — prompt examples for typical tasks
