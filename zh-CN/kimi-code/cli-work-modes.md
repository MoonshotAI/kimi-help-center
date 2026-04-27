---
title: "工作模式"
slug: "cli-work-modes"
order: 9
extract_headings: false
preview: true
preview_content: "Kimi Code CLI 的 Agent、Shell、Plan、Thinking 和 Print 五种工作模式。"
---
<SeoMeta
  title="Kimi Code CLI 工作模式 - Kimi 帮助中心"
  description="了解 Kimi Code CLI 的五种工作模式：Agent 模式、Shell 模式、Plan 模式、Thinking 模式和 Print 模式的使用方法与场景。"
/>
# 工作模式

## Agent 与 Shell 模式

Kimi Code CLI 有两种输入模式：

- **Agent 模式**：默认模式，输入的内容会发送给 AI 处理
- **Shell 模式**：直接执行 Shell 命令，无需离开 Kimi Code CLI

按 `Ctrl-X` 可以在两种模式之间切换。当前模式会显示在底部状态栏中。


在 Shell 模式下，你可以像在普通终端中一样执行命令：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "$ ls -la\n$ git status\n$ npm run build",
    },
  ]}
/>

Shell 模式也支持部分斜杠命令，包括 `/help`、`/exit`、`/version`、`/editor`、`/changelog`、`/feedback`、`/export`、`/import` 和 `/task`。

> 注意：Shell 模式中每个命令独立执行，`cd`、`export` 等改变环境的命令不会影响后续命令。

## Plan 模式

Plan 模式是一种只读的规划模式，让 AI 在动手编码之前先制定实施方案，避免在错误方向上浪费精力。

在 Plan 模式下，AI 只能使用只读工具（`Glob`、`Grep`、`ReadFile`）探索代码库，不能修改任何文件或执行命令。AI 会将方案写入一个专门的 plan 文件，然后提交给你审批。你可以选择批准、拒绝或提供修改意见。

### 进入 Plan 模式

有四种方式进入 Plan 模式：

- **启动参数**：使用 `kimi --plan` 直接以 Plan 模式启动新会话
- **快捷键**：按 `Shift-Tab` 切换 Plan 模式的开关
- **斜杠命令**：输入 `/plan` 或 `/plan on`
- **AI 主动触发**：面对复杂任务时，AI 可能会通过 `EnterPlanMode` 工具请求进入 Plan 模式，你可以选择同意或拒绝

你也可以在配置文件中设置 `default_plan_mode = true`，让每次新建会话都默认进入 Plan 模式。

进入 Plan 模式后，提示符会变为 `📋`，底部状态栏会显示蓝色的 `plan` 标识。

### 审批方案

AI 完成方案后会通过 `ExitPlanMode` 提交审批。审批面板会显示完整的方案内容，你可以：

- **批准执行**：如果方案包含多个可选实施路径，AI 会列出 2–3 个带标签的选项（如 "方案 A"、"方案 B (Recommended)"）供你选择，选中后 AI 退出 Plan 模式并按该路径执行；如果方案只有一条路径，则显示 **Approve** 按钮
- **Reject**：拒绝方案，保持 Plan 模式，你可以在对话中提供反馈
- **Reject and Exit**：拒绝方案并退出 Plan 模式，一步完成拒绝和退出操作
- **Revise**：输入修改意见，AI 会据此修订方案并重新提交

按 `Ctrl-E` 可以在全屏分页器中查看完整方案内容。

### 管理 Plan 模式

使用 `/plan` 命令可以管理 Plan 模式：

- `/plan`：切换 Plan 模式开关
- `/plan on`：开启 Plan 模式
- `/plan off`：关闭 Plan 模式
- `/plan view`：查看当前方案内容
- `/plan clear`：清除当前方案文件

## Thinking 模式

Thinking 模式让 AI 在回答前进行更深入的思考，适合处理复杂问题。

你可以通过 `/model` 命令切换模型和 Thinking 模式。在选择模型后，如果模型支持 Thinking 模式，系统会询问是否开启。也可以在启动时通过 `--thinking` 参数启用：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "kimi --thinking",
    },
  ]}
/>

> 提示：Thinking 模式需要当前模型支持。部分模型（如 `kimi-k2-thinking-turbo`）始终使用 Thinking 模式，无法关闭。

## Print 模式

Print 模式让 Kimi Code CLI 以非交互方式运行，适合脚本调用和自动化场景。

### 基本用法

使用 `--print` 参数启用 Print 模式：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "# 通过 -p 传入指令（或 -c）\nkimi --print -p "列出当前目录的所有 Python 文件"\n\n# 通过 stdin 传入指令\necho "解释这段代码的作用" | kimi --print",
    },
  ]}
/>

Print 模式的特点：

- **非交互**：执行完指令后自动退出
- **自动审批**：隐式启用 `--yolo` 模式，所有操作自动批准，交互式问答（`AskUserQuestion`）和计划模式切换也会自动处理
- **文本输出**：AI 的回复输出到 stdout

### 仅输出最终消息

使用 `--final-message-only` 选项可以只输出最终的 assistant 消息，跳过中间的工具调用过程：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "kimi --print -p "根据当前变更给我一个 Git commit message" --final-message-only",
    },
  ]}
/>

`--quiet` 是 `--print --output-format text --final-message-only` 的快捷方式，适合只需要最终结果的场景：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "kimi --quiet -p "根据当前变更给我一个 Git commit message"",
    },
  ]}
/>

### JSON 格式

Print 模式支持 JSON 格式的输入和输出，方便程序化处理。输入和输出都使用 Message 格式。

- **JSON 输出**

使用 `--output-format=stream-json` 以 JSONL（每行一个 JSON）格式输出：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "kimi --print -p "你好" --output-format=stream-json",
    },
  ]}
/>

输出示例：

<CodePreview
  files={[
    {
      name: "example.txt",
      language: "jsonl",
      content: "{\"role\":\"assistant\",\"content\":\"你好！有什么可以帮助你的吗？\"}",
    },
  ]}
/>

如果 AI 调用了工具，会依次输出 assistant 消息和 tool 消息。

- **JSON 输入**

使用 `--input-format=stream-json` 接收 JSONL 格式的输入：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "echo '{\"role\":\"user\",\"content\":\"你好\"}' | kimi --print --input-format=stream-json --output-format=stream-json",
    },
  ]}
/>

这种模式下，Kimi Code CLI 会持续读取 stdin，每收到一条用户消息就处理并输出响应，直到 stdin 关闭。

### Message 格式

输入和输出都使用统一的 Message 格式。

- **User 消息**

<CodePreview
  files={[
    {
      name: "example.json",
      language: "json",
      content: "{\"role\": \"user\", \"content\": \"你的问题或指令\"}",
    },
  ]}
/>

也可以使用数组形式的 content：

<CodePreview
  files={[
    {
      name: "example.json",
      language: "json",
      content: "{\"role\": \"user\", \"content\": [{\"type\": \"text\", \"text\": \"你的问题\"}]}",
    },
  ]}
/>

- **Assistant 消息**

<CodePreview
  files={[
    {
      name: "example.json",
      language: "json",
      content: "{\"role\": \"assistant\", \"content\": \"回复内容\"}",
    },
  ]}
/>

带工具调用的助手消息包含 `tool_calls` 字段。

- **Tool 消息**

<CodePreview
  files={[
    {
      name: "example.json",
      language: "json",
      content: "{\"role\": \"tool\", \"tool_call_id\": \"tc_1\", \"content\": \"工具执行结果\"}",
    },
  ]}
/>

### 退出码

Print 模式使用退出码表示执行结果，方便脚本和 CI 系统判断是否需要重试：

| 退出码 | 含义 | 说明 |
| --- | --- | --- |
| `0` | 成功 | 任务正常完成 |
| `1` | 失败（不可重试） | 配置错误、认证失败、额度用尽等永久性错误 |
| `75` | 失败（可重试） | 429 速率限制、5xx 服务端错误、连接超时等暂时性错误 |

### 使用场景

- **CI/CD 集成**

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "kimi --print -p "检查 src/ 目录下是否有明显的安全问题，输出 JSON 格式的报告"",
    },
  ]}
/>

- **批量处理**

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "for file in src/*.py; do\n  kimi --print -p "为 $file 添加类型注解"\ndone",
    },
  ]}
/>

- **与其他工具集成**

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "my-tool | kimi --print --input-format=stream-json --output-format=stream-json | process-output",
    },
  ]}
/>
