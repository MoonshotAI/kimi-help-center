---
title: "开始使用"
slug: "cli-getting-started"
order: 5
extract_headings: false
preview: true
preview_content: "Kimi Code CLI 安装、登录与初始化的快速入门指南。"
---
<SeoMeta
  title="Kimi Code CLI 安装与快速入门 - Kimi 帮助中心"
  description="从零开始使用 Kimi Code CLI：安装命令、三种使用方式（终端/浏览器/IDE）、首次登录四步指引，以及用 /init 生成项目配置文件。"
/>
# 开始使用 Kimi Code CLI

Kimi Code CLI 是一个运行在终端中的 AI Agent，帮助你完成软件开发任务和终端操作。它可以阅读和编辑代码、执行 Shell 命令、搜索和抓取网页，并在执行过程中自主规划和调整方案。

## 适合场景

- **编写和修改代码**：描述需求，AI 自动完成代码编写与修改。
- **理解项目**：快速了解项目架构、代码逻辑和文件作用。
- **自动化任务**：批量修改代码、添加文档、生成测试用例等重复性工作。

## 三种使用方式

| 方式 | 命令 | 说明 |
| --- | --- | --- |
| 交互式终端 | `kimi` | 在终端中与 AI 对话，适合日常开发 |
| 浏览器界面 | `kimi web` | 在浏览器中打开交互界面 |
| Agent 集成 | `kimi acp` | 通过 ACP 协议集成到 IDE 中使用 |

## 安装

在终端中运行以下命令安装 Kimi Code CLI：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "curl -LsSf https://code.kimi.com/install.sh | bash",
    },
  ]}
/>

安装完成后，验证安装是否成功：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "kimi --version",
    },
  ]}
/>

<Callout type="tip">
如果 `kimi` 命令未找到，请尝试重新打开终端或执行 `source ~/.bashrc`（或 `~/.zshrc`）。
</Callout>

## 首次运行

1. 进入你的项目目录：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "cd /path/to/your/project",
    },
  ]}
/>

2. 启动 Kimi Code CLI：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "kimi",
    },
  ]}
/>

3. 执行 `/login` 命令完成登录授权：

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "/login",
    },
  ]}
/>

   系统会提示你选择登录平台，按提示完成授权即可。

4. 配置完成后，你就可以开始与 AI 对话了。

## 生成 AGENTS.md

在项目目录下执行 `/init` 命令，Kimi Code CLI 会自动扫描项目结构并生成 `AGENTS.md` 文件：

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "/init",
    },
  ]}
/>

`AGENTS.md` 用于向 AI 提供项目的背景信息、构建步骤、代码规范等上下文，帮助 AI 更准确地理解你的项目。
