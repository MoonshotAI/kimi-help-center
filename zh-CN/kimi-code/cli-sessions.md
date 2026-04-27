---
title: "上下文管理"
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
# 会话与上下文管理

## 会话续接

Kimi Code CLI 会自动保存你的对话历史，方便你随时继续之前的工作。

每次启动 Kimi Code CLI 时，都会创建一个新的会话。在运行过程中，你也可以输入 /new 命令随时创建并切换到一个新会话，无需退出程序。

如果你想继续之前的对话，有几种方式：

## 继续最近的会话

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
- 列表会显示每个会话的标题和最后更新时间，帮助你找到想要继续的对话。按 Ctrl-A 可在「仅当前目录」和「所有目录」之间切换范围，方便跨项目查找会话。使用 /title <text> 可以为会话设置一个自定义标题，方便后续查找。

## 退出时的续接提示
当会话退出时（包括正常退出、Ctrl-C 中断、/undo、/fork、/sessions 切换等场景），Kimi Code CLI 会自动打印一条续接命令提示：
<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "To resume this session: kimi -r <session-id>",
    },
  ]}
/>

## 启动回放

当你继续一个已有会话时，Kimi Code CLI 会回放之前的对话历史，让你快速了解上下文。回放过程中会显示之前的消息和 AI 的回复。

## 会话状态持久化

除了对话历史，Kimi Code CLI 还会自动保存和恢复会话的运行状态。当你恢复一个会话时，以下状态会自动还原：

- 审批决策：YOLO 模式的开关状态、通过 "本会话允许" 批准过的操作类型
- Plan 模式：Plan 模式的开关状态
- 子 Agent 实例：通过 Agent 工具在会话中创建的子 Agent 实例状态和上下文历史
- 额外目录：通过 --add-dir 或 /add-dir 添加的工作区目录

这意味着你不需要在每次恢复会话时重新配置这些设置。例如，如果你在上次会话中批准了某类 Shell 命令的自动执行，恢复会话后这些批准仍然有效。

## 导出与导入
### 导出与导入

Kimi Code CLI 支持将会话上下文导出为文件，或从外部文件和其他会话导入上下文。

#### 导出会话

输入 `/export` 可以将当前会话的完整对话历史导出为 Markdown 文件：

<CodePreview
  files={[
    {
      name: "example.txt",
      language: "text",
      content: "/export",
    },
  ]}
/>

导出文件包含会话元数据、对话概览和按轮次组织的完整对话记录。你也可以指定输出路径：

<CodePreview
  files={[
    {
      name: "example.txt",
      language: "text",
      content: "/export ~/exports/my-session.md",
    },
  ]}
/>

#### 导入上下文

输入 `/import` 可以从文件或其他会话导入上下文。导入的内容会作为参考信息附加到当前会话中：

<CodePreview
  files={[
    {
      name: "example.txt",
      language: "text",
      content: "/import ./previous-session-export.md\n/import abc12345",
    },
  ]}
/>

支持导入常见的文本格式文件（Markdown、代码、配置文件等）。你也可以传入一个会话 ID，从该会话导入完整的对话历史。

> 提示：导出文件可能包含敏感信息（如代码片段、文件路径等），分享前请注意检查。


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
