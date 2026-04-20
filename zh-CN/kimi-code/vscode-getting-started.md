---
title: "Kimi Code for VS Code 快速开始"
slug: "vscode-getting-started"
order: 10
extract_headings: false
preview: true
preview_content: "Kimi Code VS Code 插件的安装、登录与使用入门。"
---
<SeoMeta
  title="Kimi Code for VS Code 快速入门 - Kimi 帮助中心"
  description="在 VS Code 中安装和使用 Kimi Code 扩展：登录、聊天面板、@引用文件、斜杠命令、代码变更 Diff 视图和 MCP 集成全流程指南。"
  pageUrl="https://www.kimi.com/help/kimi-code/vscode-getting-started"
/>
# Kimi Code for VS Code 快速开始

Kimi Code for VS Code 是集成于 Visual Studio Code 的扩展插件。安装后，你可以在编辑器内直接发起提问、审查代码 diff 并快速提交变更。插件能够读取你引用的文件内容，理解项目上下文，提供更精准的编程辅助。

## 安装

1. 打开 VS Code。
2. 进入扩展市场（快捷键 `Ctrl+Shift+X` / `Cmd+Shift+X`）。
3. 搜索 **Kimi Code**。
4. 点击 **安装**。

<Callout type="tip">
如果扩展未出现，尝试重启 VS Code 或在命令面板中执行 `Developer: Reload Window`。
</Callout>

## 登录配置

安装完成后，需要登录你的 Kimi 账号：

1. 打开 Kimi Code 聊天面板。
2. 输入 `/login` 命令。
3. 按提示完成授权，系统会自动绑定你的账号。

## 基本使用

### 聊天面板

Kimi Code 在 VS Code 侧边栏提供了原生的聊天面板，你可以：

- **提问和对话**：直接输入问题，AI 会结合项目上下文进行回答。
- **引用文件**：使用 `@` 符号引用文件或文件夹，AI 会读取其内容作为上下文。
- **斜杠命令**：使用 `/` 命令执行项目扫描、上下文管理等操作。

### 代码变更

AI 生成的代码变更会以 diff 视图展示，你可以：

- **审查变更**：逐行查看 AI 建议的修改内容。
- **接受或拒绝**：选择性地应用部分或全部变更。
- **回退操作**：对已应用的变更进行回退。

### 集成 MCP

VS Code 扩展同样支持 MCP 集成，你可以在项目中配置 MCP 服务器来扩展 AI 的能力。

## 与 CLI 的区别

| 特性 | VS Code 扩展 | CLI |
| --- | --- | --- |
| 使用环境 | VS Code 编辑器内 | 终端 |
| 交互方式 | 图形化聊天面板 | 命令行对话 |
| 代码变更 | diff 视图，支持回退 | 直接修改文件 |
| 文件引用 | @ 引用，图形化选择 | @ 引用，路径补全 |
| Shell 命令 | AI 代为执行 | 支持 Shell 模式直接执行 |
| 会话管理 | 面板内管理 | /sessions 命令管理 |

两种方式可以按需使用，互不冲突。CLI 更适合终端重度用户和自动化场景，VS Code 扩展更适合习惯图形化操作的开发者。
