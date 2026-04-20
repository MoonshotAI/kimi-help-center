---
title: "Kimi Code for VS Code quick start"
slug: "vscode-getting-started"
order: 10
extract_headings: false
preview: false
---

<SeoMeta
  title="Kimi Code for VS Code quick start - Kimi Help Center"
  description="Kimi Code for VS Code is an extension integrated into Visual Studio Code. Once installed, you can ask questions, review code diffs, and quickly commit change..."
  pageUrl="https://www.kimi.com/help/kimi-code/vscode-getting-started"
/>

# Kimi Code for VS Code quick start

<Callout type="info">
Kimi Code for VS Code is an extension integrated into Visual Studio Code. Once installed, you can ask questions, review code diffs, and quickly commit changes — all from within the editor.
</Callout>

## Installation

1. Open VS Code
2. Go to the Extensions Marketplace (shortcut `Ctrl+Shift+X` / `Cmd+Shift+X`)
3. Search for **Kimi Code**
4. Click **Install**

<Callout type="tip">
If the extension doesn't appear, try restarting VS Code or running `Developer: Reload Window` from the Command Palette.
</Callout>

## Login configuration

After installation, sign in to your Kimi account:

1. Open the Kimi Code chat panel
2. Enter the `/login` command
3. Follow the prompts to complete authorization — the system will automatically bind your account

## Basic usage

### Chat panel

Kimi Code provides a native chat panel in the VS Code sidebar where you can:

- **Ask Questions**: Type your question and the AI will respond using your project context
- **Reference Files**: Use the `@` symbol to reference files or folders — the AI reads their content as context
- **Slash Commands**: Use `/` commands for project scanning, context management, and more

### Code changes

AI-generated code changes are displayed in a diff view where you can:

- **Review Changes**: Inspect AI-suggested modifications line by line
- **Accept or Reject**: Selectively apply some or all changes
- **Revert**: Roll back changes that have already been applied

### MCP integration

The VS Code extension also supports MCP integration — you can configure MCP servers in your project to extend the AI's capabilities.

## Comparison with CLI

| Feature | VS Code Extension | CLI |
| --- | --- | --- |
| **Environment** | Inside VS Code editor | Terminal |
| **Interaction** | Graphical chat panel | Command-line conversation |
| **Code Changes** | Diff view with rollback | Direct file modification |
| **File References** | @ references, graphical selection | @ references, path completion |
| **Shell Commands** | Executed by the AI | Direct execution in Shell Mode |
| **Session Management** | In-panel management | /sessions command |

<Callout type="info">
Both methods can be used as needed and do not conflict with each other. The CLI is better suited for terminal power users and automation scenarios, while the VS Code extension is ideal for developers who prefer a graphical interface.
</Callout>
