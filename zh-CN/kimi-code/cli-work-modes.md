---
title: "工作模式"
slug: "cli-work-modes"
order: 9
extract_headings: false
preview: true
preview_content: "Kimi Code CLI 的 Plan 模式和 Thinking 模式的使用方法与场景。"
---

<SeoMeta
  title="Kimi Code CLI 工作模式 - Kimi 帮助中心"
  description="了解 Kimi Code CLI 的 Plan 模式和 Thinking 模式的使用方法与场景。"
/>

# 工作模式

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
