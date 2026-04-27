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

<ColumnsContent
  columns={[
    {
      title: "Code Reading",
      description: "Type @ to select files and request an explanation of the logic flow.",
      pageUrl: "/help/vscode/code-reading",
      type: "microscope",
    },
    {
      title: "Refactoring",
      description: "Request a refactoring plan for a folder and review diffs before applying.",
      pageUrl: "/help/vscode/refactoring",
      type: "code",
    },
    {
      title: "Debugging",
      description: "Paste error traces and reference related files for instant diagnosis.",
      pageUrl: "/help/vscode/debugging",
      type: "okcomputer",
    },
  ]}
/>

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