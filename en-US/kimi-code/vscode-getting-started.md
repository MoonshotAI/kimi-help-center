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
/>

# Kimi Code for VS Code quick start

<Callout type="warning">
**VS Code Extension Compatibility Notice**

Kimi Code for VS Code is currently only available for new installation to users of the legacy Python CLI. Existing users who have already installed the plugin can continue using it after upgrading to the new CLI. TS version CLI users are not supported for installation at this time.
</Callout>

Kimi Code for VS Code is an extension integrated into Visual Studio Code. After installation, you can ask questions directly within the editor, review code diffs, and quickly commit changes. 

The extension can read the content of files you reference and display modification suggestions through a visual interface, executing them after your confirmation. The entire workflow is under your control while significantly improving development efficiency.

This extension provides a native chat panel in VS Code, supporting:
- Referencing files or folders via the `@` symbol.
- Executing project scans and context management via `/` commands.
- Diff views showing file changes with rollback support.
- Integrating MCP servers to call external tools.

---

## Installation

1.  **Prerequisites**: You need a Kimi account subscription or a Kimi API key.
2.  **Marketplace**: Install via the [VS Code Marketplace](vscode:extension/moonshot-ai.kimi-code).

<Callout type="tip">
If the extension doesn't appear after installation, please restart VS Code or execute **Developer: Reload Window** in the command palette (Mac: `Cmd+Shift+P`, Win/Linux: `Ctrl+Shift+P`).
</Callout>

---

## Authentication

Kimi Code supports two authentication modes. You can switch modes at any time via the **gear icon**.

<Frames
  src="./images/vscode/kimi-code-gear-icon.png"
  alt="Authentication settings"
  width={800}
  height={450}
/>

- **Kimi Account Mode**: Click the login button to authorize via your browser.
- **API Key Mode**: Click to skip login if you have already configured an API key.

---

## Typical Workflows

Code Reading: Type`@` to select a file or folder, request an explanation of the code flow, and continue asking follow-up questions.

Refactoring: Reference target code such as `@src/feature/`, request a refactoring plan, review the diff and selectively approve, using rollback when necessary.

Debugging: Paste error messages or stack traces, reference related files, request diagnosis and fixes, then approve the proposed changes.

Project Overview: Reference a folder such as `@src/services/`, request a module map or architecture summary, and continue asking about dependencies or weak points.

---

## Commands and Shortcuts

Use `CodePreview` to quickly test commands or reference key shortcuts:

<CodePreview
  files={[
    {
      name: "shortcuts.txt",
      language: "text",
      content: "Ctrl+Shift+K : Focus Kimi input box\nAlt+K : Insert current file reference\nCtrl+N : New conversation",
    },
  ]}
/>

| Shortcut | Function |
| :--- | :--- |
| `Ctrl+Shift+K` / `Cmd+Shift+K` | Focus Kimi input box |
| `Alt+K` | Insert current file reference |
| `Ctrl+N` / `Cmd+N` | New conversation |
| `↑` / `↓` | Browse input history |

<Callout type="info">
Type **Kimi Code** in the command palette to access more commands: open in new tab, open in sidebar, or manage sessions.
</Callout>