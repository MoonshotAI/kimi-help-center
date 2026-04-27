---
title: "交互与输入"
slug: "cli-interaction"
order: 7
extract_headings: false
preview: true
preview_content: "Kimi Code 的交互模式、斜杠命令与审批机制说明。"
---
<SeoMeta
  title="Kimi Code CLI 交互方式与命令参考 - Kimi 帮助中心"
  description="掌握 Kimi Code CLI 的 Agent/Shell 双模式切换、Thinking 模式、多行输入、图片粘贴、斜杠命令和审批确认机制等交互功能。"
/>

# 交互与输入

Kimi Code CLI 提供了多种交互方式，帮助你高效地与 AI 协作。

## Agent 模式与 Shell 模式

Kimi Code CLI 有两种输入模式：

- **Agent 模式**（默认）：输入的内容会发送给 AI 处理，AI 会阅读代码、执行命令、修改文件等。
- **Shell 模式**：直接执行 Shell 命令，无需离开 Kimi Code CLI。

使用 **Ctrl-X** 在两种模式之间快速切换。Shell 模式下也支持部分斜杠命令，如 `/help`、`/exit`、`/version` 等。

## Thinking 模式

Thinking 模式让 AI 在回答前进行更深入的思考，适合处理复杂问题。

- 使用 `/model` 命令切换模型和 Thinking 模式。
- 启动时可通过 `--thinking` 参数直接开启 Thinking 模式。

## 多行输入

按 **Ctrl-J** 插入换行，进行多行输入。适合输入较长的 prompt 或粘贴多行代码片段。

## 剪贴板粘贴

按 **Ctrl-V** 从剪贴板粘贴内容，支持粘贴文本和图片。粘贴图片时，AI 可以直接理解图片内容（如截图、设计稿、报错截图等）。

## 斜杠命令

以 `/` 开头的命令用于控制会话、配置和调试。常用命令包括：

| 命令 | 说明 |
| --- | --- |
| `/help` | 显示帮助信息 |
| `/login` | 登录授权 |
| `/model` | 切换模型和 Thinking 模式 |
| `/sessions` | 列出和切换会话 |
| `/clear` | 清空当前上下文 |
| `/compact` | 压缩上下文 |
| `/init` | 生成 AGENTS.md |
| `/exit` | 退出 CLI |

在输入框中输入 `/` 后，会自动显示可用命令列表。

## @ 路径补全

在输入中使用 `@` 符号可以引用文件或目录路径，系统会自动补全：

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "帮我看看 @src/utils/auth.ts 这个文件有没有安全隐患",
    },
  ]}
/>

这样 AI 会自动读取引用的文件内容作为上下文。

## 结构化问答

在某些场景下，AI 会以结构化选项的形式请求你的输入。使用**方向键**选择选项，按 **Enter** 确认。

## 审批确认

当 AI 需要执行文件修改、Shell 命令等操作时，会请求你的确认。你可以选择：

| 选项 | 说明 |
| --- | --- |
| **允许** | 允许本次操作 |
| **本会话允许** | 允许同类操作在当前会话中不再询问 |
| **拒绝** | 拒绝本次操作 |

### YOLO 模式

如果你信任 AI 的操作，可以使用 YOLO 模式跳过所有确认：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "kimi --yolo",
    },
  ]}
/>

<Callout type="warning">
YOLO 模式下 AI 会自动执行所有操作，请谨慎使用。建议仅在可控的开发环境中使用。
</Callout>
