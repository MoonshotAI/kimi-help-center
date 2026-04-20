---
title: "Sessions & context"
slug: "cli-sessions"
order: 6
extract_headings: false
preview: false
---

<SeoMeta
  title="Sessions \u0026 context - Kimi Help Center"
  description="Kimi Code CLI supports multi-session management and context persistence, allowing you to pause and resume work at any time."
  pageUrl="https://www.kimi.com/help/kimi-code/cli-sessions"
/>

Kimi Code CLI supports multi-session management and context persistence, allowing you to pause and resume work at any time.

## Session resumption

You can resume a previous session in several ways:

### Continue the most recent session

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "kimi --continue",
    },
  ]}
/>

Use the `--continue` (or `-c`) flag to continue the last conversation.
### Specify a session ID

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "kimi --session \u003csession-id\u003e",
    },
  ]}
/>

Use the `--session` flag to restore a specific session.

### Browse and switch

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "/sessions",
    },
  ]}
/>

Run `/sessions` (or `/resume`) to view the session list and select one to restore.
## Startup replay

When resuming a session, Kimi Code CLI automatically replays the conversation history, helping you quickly recall the previous context and progress.

## State persistence

The following state is automatically saved and restored across sessions:

- **Approval decisions**: Decisions such as "Allow for Session" are remembered.
- **Dynamic sub-agents**: Sub-agent configurations created during a session are preserved.
- **Additional directories**: Extra working directories added via commands are also persisted.

This means you can seamlessly continue your previous work after resuming a session.

## Clear & compact

Kimi Code CLI automatically compresses the context when needed to ensure the conversation can continue. You can also manage the context manually with slash commands:

### Clear context

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "/clear",
    },
  ]}
/>

Enter `/clear` (or `/reset`) to clear all context in the current session and start a fresh conversation:

### Compact context

Enter `/compact` to compress the context — preserving key information while reducing token usage:

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "/compact",
    },
  ]}
/>

You can also include instructions when compacting to tell the AI which information to prioritize:

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "/compact Keep the discussion about database migrations",
    },
  ]}
/>

### Context status

The status bar at the bottom of the CLI displays the current context utilization in real time, helping you monitor context consumption. When utilization is high, use `/compact` to compress the context and avoid losing important information.
