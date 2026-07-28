---
title: "Work Modes"
slug: "cli-work-modes"
order: 9
extract_headings: false
preview: true
preview_content: "How to use Plan mode and Thinking mode in Kimi Code CLI, and when to use them."
---

<SeoMeta
  title="Kimi Code CLI Work Modes - Kimi Help Center"
  description="Learn how to use Plan mode and Thinking mode in Kimi Code CLI, and when to use them."
/>

# Work Modes

## Plan mode

Plan mode is a read-only planning mode that lets the AI create an implementation plan before it starts coding, helping avoid wasted effort in the wrong direction.

In Plan mode, the AI can only use read-only tools (`Glob`, `Grep`, `ReadFile`) to explore the codebase. It cannot modify any files or run commands. The AI writes the plan to a dedicated plan file and then submits it for your approval. You can approve it, reject it, or provide revision comments.

### Enter Plan mode

You can enter Plan mode in four ways:

- **Startup option**: Use `kimi --plan` to start a new session directly in Plan mode
- **Keyboard shortcut**: Press `Shift-Tab` to toggle Plan mode on or off
- **Slash command**: Enter `/plan` or `/plan on`
- **AI-initiated**: For complex tasks, the AI may request to enter Plan mode through the `EnterPlanMode` tool. You can accept or decline

You can also set `default_plan_mode = true` in the configuration file so every new session starts in Plan mode by default.

After entering Plan mode, the prompt changes to `📋`, and the bottom status bar shows a blue `plan` indicator.

### Review and approve plans

When the AI finishes the plan, it submits it for approval through `ExitPlanMode`. The approval panel displays the complete plan. You can:

- **Approve execution**: If the plan includes multiple implementation paths, the AI lists 2–3 labeled options (such as "Plan A" or "Plan B (Recommended)") for you to choose from. After you select one, the AI exits Plan mode and executes that path. If there is only one path, an **Approve** button is shown
- **Reject**: Reject the plan and stay in Plan mode. You can provide feedback in the conversation
- **Reject and Exit**: Reject the plan and exit Plan mode in one step
- **Revise**: Enter revision comments. The AI will update the plan accordingly and submit it again

Press `Ctrl-E` to view the full plan in the full-screen pager.

### Manage Plan mode

Use the `/plan` command to manage Plan mode:

- `/plan`: Toggle Plan mode on or off
- `/plan on`: Turn on Plan mode
- `/plan off`: Turn off Plan mode
- `/plan view`: View the current plan
- `/plan clear`: Clear the current plan file

## Thinking mode

Thinking mode lets the AI think more deeply before responding, making it suitable for complex problems.

You can use the `/model` command to switch models and Thinking mode. After you select a model, if the model supports Thinking mode, the system will ask whether to enable it. You can also enable it at startup with the `--thinking` option:

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "kimi --thinking",
    },
  ]}
/>

> Tip: Thinking mode must be supported by the current model. Some models, such as `kimi-k2-thinking-turbo`, always use Thinking mode and cannot turn it off.
