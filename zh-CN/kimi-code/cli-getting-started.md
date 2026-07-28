---
title: "开始使用"
slug: "cli-getting-started"
order: 6
extract_headings: false
preview: true
preview_content: "Kimi Code CLI 安装、登录与初始化的快速入门指南。"
---

<SeoMeta
  title="Kimi Code CLI 安装与快速入门 - Kimi 帮助中心"
  description="从零开始使用 Kimi Code CLI：安装命令、两种使用方式（终端/浏览器）、首次登录四步指引，以及用 /init 生成项目配置文件。"
/>

# 开始使用 Kimi Code CLI

Kimi Code CLI 是一个运行在终端中的 AI Agent，帮助你完成软件开发任务和终端操作。它可以阅读和编辑代码、执行 Shell 命令、搜索和抓取网页，并在执行过程中自主规划和调整方案。

## 适合场景

- **编写和修改代码**：实现新功能、修复 bug、完成重构
- **理解项目**：探索陌生的代码库，解答架构和实现层面的问题
- **自动化任务**：批量处理文件、运行构建与测试、串联多个脚本

整套 CLI 以 TypeScript 编写，通过 npm 分发，运行在 Node.js 之上。

## 开始之前

- **操作系统**：macOS、Linux 或 Windows（通过 PowerShell）
- **Kimi 账号**：需拥有 Kimi 会员订阅，或可调用的 API key

<Callout type="tip">
Kimi Code CLI 为全交互式 TUI 应用，推荐在支持真彩色与连字的现代终端中运行以获得最佳体验，例如 [Kitty](https://sw.kovidgoyal.net/kitty/) 或 [Ghostty](https://ghostty.org/)。
</Callout>

## 安装

提供两种安装方式：官方安装脚本（推荐，无需预装 Node.js）和 npm 全局安装。

### 脚本安装（推荐）

macOS / Linux：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "curl -fsSL https://code.kimi.com/kimi-code/install.sh | bash",
    },
  ]}
/>

Windows（PowerShell）：

<CodePreview
  files={[
    {
      name: "command.ps1",
      language: "powershell",
      content: "irm https://code.kimi.com/kimi-code/install.ps1 | iex",
    },
  ]}
/>

脚本会自动下载最新版本、校验 checksum，并把 `kimi` 可执行文件放到你的 `PATH` 中。

<Callout type="tip">
Windows 用户首次启动前还需要安装 [Git for Windows](https://gitforwindows.org/)，Kimi Code CLI 会使用其中的 Git Bash 作为 Shell 环境。如果 Git Bash 安装在非标准路径，请把 `KIMI_SHELL_PATH` 设为 `bash.exe` 的绝对路径。
</Callout>

### npm 安装

如果你已经安装了 Node.js 22.19.0 或更高版本，可以直接用 npm 安装：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "node --version\nnpm install -g @moonshot-ai/kimi-code",
    },
  ]}
/>

或用 pnpm：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "pnpm add -g @moonshot-ai/kimi-code",
    },
  ]}
/>

### 验证安装

安装完成后，验证可执行文件是否就绪：

<Frames
  src="./images/cli-getting-started/cli-getting-started-02.png"
  alt="验证安装"
/>

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
由于 macOS 的安全检查机制（Gatekeeper），首次运行 `kimi` 命令可能需要较长时间。可以在「系统设置 → 隐私与安全性 → 开发者工具」中添加你的终端应用来加速后续启动。
</Callout>

<Callout type="tip">
如果 `kimi` 命令未找到，请尝试重新打开终端或执行 `source ~/.bashrc`（或 `~/.zshrc`）。
</Callout>

## 升级与卸载

**升级**：运行 `kimi upgrade`，CLI 会检查最新版本并展示更新选项。选择 `Install update now` 后根据当前安装来源执行升级；也可以直接用包管理器：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "npm install -g @moonshot-ai/kimi-code@latest",
    },
  ]}
/>

**卸载**：脚本安装的用户删除 `kimi` 可执行文件即可；npm 安装的用户：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "npm uninstall -g @moonshot-ai/kimi-code",
    },
  ]}
/>

## 第一次启动

### 启动交互界面

进入项目目录后直接运行 `kimi` 启动交互界面：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "cd your-project\nkimi",
    },
  ]}
/>

### 单条指令

只想执行一条指令而不进入交互界面时，使用 `-p`：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "kimi -p \"帮我看一下这个项目的目录结构\"",
    },
  ]}
/>

### 继续会话

继续上一次会话加 `-C`：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "kimi -C",
    },
  ]}
/>

### 首次登录

首次启动时需要配置 API 来源。在交互界面中输入 `/login` 进入登录流程：

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "/login",
    },
  ]}
/>

`/login` 会弹出平台选择器，支持两种方式：

- **Kimi Code（OAuth）** — 验证码流程，在任意设备打开链接、登录并输入验证码即可授权
- **Kimi Platform API 密钥** — 输入来自 `platform.kimi.com` 或 `platform.kimi.ai` 的 API 密钥

需要退出登录时，输入 `/logout` 清除当前凭证。

<Callout type="tip">
如果你想接入 Anthropic、OpenAI、Google 等其他供应商，需要直接编辑 `~/.kimi-code/config.toml` 配置 API 密钥。配置项完整说明见环境变量和配置覆盖文档。
</Callout>

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

## 第一个对话

登录完成后，用自然语言描述任务即可。先让它熟悉当前项目：

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "帮我看一下这个项目的目录结构，简单介绍一下每个目录是做什么的",
    },
  ]}
/>

Kimi Code CLI 会自动调用文件读取、搜索等工具浏览相关内容后给出回答。只读操作默认自动执行无需确认；对于会修改文件或执行 Shell 命令的操作，默认会在执行前征求确认。

也可以直接描述更具体的任务：

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "在 src/utils 里新增一个函数，用来把任意字符串转成 kebab-case，并补一个单元测试",
    },
  ]}
/>

Kimi Code CLI 会规划步骤、修改代码、运行测试，并在每一步告诉你它做了什么。

<Callout type="tip">
不知道能做什么？输入 `/help` 可以打开内置的命令和快捷键面板，按 `↑`/`↓` 翻看，`Esc` 关闭。退出时输入 `/exit`，或按 `Ctrl-C` 两次，或在输入框为空时按 `Ctrl-D`。
</Callout>

## 常用命令与快捷键速查

### 会话相关命令

| 命令 | 说明 |
| --- | --- |
| `/new` | 开启新会话，清空当前上下文 |
| `/sessions` | 浏览历史会话，选择恢复 |
| `/model` | 切换当前使用的模型 |
| `/compact` | 手动压缩上下文，释放 token |
| `/fork` | 派生当前会话，保留历史独立继续 |

### 最常用快捷键

| 快捷键 | 说明 |
| --- | --- |
| `Esc` | 中断流式输出 / 关闭弹窗 |
| `Ctrl-C` | 中断输出；空闲时连按两次退出 |
| `Shift-Tab` | 切换 Plan 模式 |
| `Ctrl-S` | 输出中途插入消息，无需等待结束 |
| `Ctrl-O` | 折叠 / 展开工具输出 |

想看完整列表，输入 `/help` 或访问[工作模式](/kimi-code/cli-work-modes)和[交互与输入](/kimi-code/cli-interaction)。

## 数据存放在哪里

Kimi Code CLI 的本地数据默认保存在 `~/.kimi-code/` 下，包含配置文件、会话记录、日志和更新缓存。如需迁移到别处，通过 `KIMI_CODE_HOME` 环境变量指定新路径。完整说明见环境变量文档。

## 常见问题

**我填了 API Key 怎么提示鉴权失败**

先确认你用的 Key 和 Base URL 是不是同一个平台的。`api.kimi.com` 和 `api.moonshot.cn` 是两个完全独立的账号体系，API Key 互不通用：

| 平台 | Base URL | 计费方式 | Key 创建入口 |
|------|---------|---------|-------------|
| **Kimi Code** | Open AI 兼容： `https://api.kimi.com/coding/v1`<br> Anthropic 兼容：`https://api.kimi.com/coding/` | Kimi 会员订阅（含额度） | [Kimi Code 控制台](https://www.kimi.com/code/console) |
| **Kimi 开放平台** | `https://api.moonshot.cn/v1` | 按量付费 | [Kimi 开放平台官网](https://platform.kimi.com) |

**安装后 `kimi` 命令找不到**

安装脚本会将 `kimi` 添加到 PATH，但需要重启终端或执行 `source ~/.bashrc`（或 `source ~/.zshrc`）才能生效。如果仍然找不到，检查 `~/.local/bin` 是否在你的 PATH 中。

**`/login` 后浏览器没有弹出**

如果在远程服务器或无图形界面的环境中，`/login` 会显示一个 URL，手动复制到浏览器打开即可完成授权。

更多问题请参考[常见问题](/kimi-code/faq)。

## 下一步

- [交互与输入](/kimi-code/cli-interaction) — 输入框操作、审批流程、Plan 模式和 YOLO 模式详解
- [会话与上下文](/kimi-code/cli-sessions) — 恢复会话、上下文压缩、导出会话
- [常见使用案例](/kimi-code/cli-use-cases) — 典型任务的 prompt 示例
