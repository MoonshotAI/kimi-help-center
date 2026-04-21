---
title: "会话与上下文"
slug: "cli-sessions"
order: 6
extract_headings: false
preview: true
preview_content: "Kimi Code 会话管理：续接、上下文压缩与持久化。"
---
<SeoMeta
  title="Kimi Code CLI 会话管理与上下文 - Kimi 帮助中心"
  description="了解 Kimi Code CLI 的会话续接、状态持久化、上下文压缩与清空等功能，高效管理长时间的开发会话和项目上下文。"
/>
# 会话与上下文

Kimi Code CLI 支持多会话管理和上下文持久化，让你可以随时中断和恢复工作。

## 会话续接

你可以通过多种方式恢复之前的会话：

- **继续最近会话**：使用 `--continue`（或 `-c`）参数继续上一次对话：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "kimi --continue",
    },
  ]}
/>

- **指定会话 ID**：使用 `--session` 参数恢复特定会话：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "kimi --session <session-id>",
    },
  ]}
/>

- **列表切换**：在 CLI 中输入 `/sessions`（或 `/resume`）命令，查看会话列表并选择要恢复的会话。

## 启动回放

恢复会话时，Kimi Code CLI 会自动回放历史消息，帮助你快速回忆之前的上下文和进展。

## 状态持久化

以下状态会在会话之间自动保存和恢复：

- **审批决策**：你在会话中做出的「本会话允许」等审批决策会被记住。
- **动态子 Agent**：会话中创建的子 Agent 配置会被保留。
- **额外目录**：通过命令添加的额外工作目录也会被持久化。

这意味着恢复会话后，你可以无缝继续之前的工作。

## 清空与压缩

Kimi Code CLI 会在需要的时候自动对上下文进行压缩，确保对话能够继续。你也可以使用斜杠命令手动管理上下文：

### 清空上下文

输入 `/clear`（或 `/reset`）可以清空当前会话的所有上下文，重新开始对话：

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "/clear",
    },
  ]}
/>

### 压缩上下文

输入 `/compact` 可以压缩上下文，保留关键信息的同时减少 token 占用：

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "/compact",
    },
  ]}
/>

你也可以在压缩时附带说明，告诉 AI 哪些信息需要重点保留：

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "/compact 保留数据库迁移相关的讨论",
    },
  ]}
/>

### 上下文状态

CLI 底部的状态栏会实时显示当前的 context 使用率，帮助你了解上下文的消耗情况。当使用率较高时，建议使用 `/compact` 进行压缩，避免丢失重要信息。
