---
title: "Interaction & input"
slug: "cli-interaction"
order: 5
extract_headings: false
preview: false
---

<SeoMeta
  title="Interaction \u0026 input - Kimi Help Center"
  description="Kimi Code CLI provides multiple interaction methods to help you collaborate with the AI efficiently."
/>

Kimi Code CLI provides multiple interaction methods to help you collaborate with the AI efficiently.

## Agent mode vs. shell mode

Kimi Code CLI has two input modes:

- **Agent Mode** (default): Your input is sent to the AI for processing — the AI reads code, executes commands, modifies files, and more.
- **Shell Mode**: Execute shell commands directly without leaving Kimi Code CLI.

Press **Ctrl-X** to quickly switch between the two modes. Shell Mode also supports select slash commands such as `/help`, `/exit`, `/version`, etc.

## Thinking mode

Thinking Mode enables the AI to perform deeper reasoning before responding — ideal for complex problems.

- Use the `/model` command to switch models and toggle Thinking Mode.
- You can also enable Thinking Mode at launch with the `--thinking` flag.

## Multi-line input

Press **Ctrl-J** to insert a newline for multi-line input. This is useful for longer prompts or pasting multi-line code snippets.

## Clipboard paste

Press **Ctrl-V** to paste content from the clipboard — supports both text and images. When pasting images, the AI can directly interpret the image content (e.g., screenshots, design mockups, error screenshots).

## Slash commands

Commands starting with `/` are used to control sessions, configuration, and debugging. Common commands include:

| Command | Description |
| --- | --- |
| `/help` | Display help information |
| `/login` | Log in and authorize |
| `/model` | Switch models and Thinking Mode |
| `/sessions` | List and switch sessions |
| `/clear` | Clear the current context |
| `/compact` | Compress the context |
| `/init` | Generate AGENTS.md |
| `/exit` | Exit the CLI |

Typing `/` in the input field will automatically display a list of available commands.

## @ Path completion

Use the `@` symbol in your input to reference file or directory paths — the system will auto-complete:

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "Check @src/utils/auth.ts for any security vulnerabilities",
    },
  ]}
/>

The AI will automatically read the referenced file content as context.

## Structured Q&A

In certain scenarios, the AI will present structured options for your input. Use the **arrow keys** to select an option and press **Enter** to confirm.

## Approval confirmation

When the AI needs to perform file modifications, shell commands, or other operations, it will ask for your confirmation. You can choose:

| Option | Description |
| --- | --- |
| **Allow** | Permit this operation |
| **Allow for Session** | Allow similar operations for the rest of the current session without further prompts |
| **Deny** | Reject this operation |

### YOLO mode

If you trust the AI's operations, you can use YOLO Mode to skip all confirmations:

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "kimi --yolo",
    },
  ]}
/>

> In YOLO Mode the AI will automatically execute all operations — use with caution. Recommended only in controlled development environments.
