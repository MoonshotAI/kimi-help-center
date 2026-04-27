---
title: "Kimi Code 会员权益指南"
slug: "membership-guide"
order: 1
extract_headings: false
preview: true
preview_content: "Kimi Code 会员权益、API Key 管理与设备登录指南。"
---
<SeoMeta
  title="Kimi Code 会员权益指南 - Kimi 帮助中心"
  description="了解 Kimi Code 的会员权益，包括兼容多种 Agent 工具、100 Tokens/s 高速推理、高频并发支持，以及 API Key 获取与设备管理方法。"
/>

# Kimi Code 概览

## Kimi Code 是什么
Kimi Code 是  [Kimi 会员权益](https://www.kimi.com/membership/pricing?from=kfc_docs_overview)中面向编程场景的智能编程服务。

你可以把它理解为一个 AI 编程助手：它可以在开发工具中帮你阅读代码、修改文件、执行命令，并协助完成开发任务。

Kimi Code 主要有三种使用方式：
1. 通过 Kimi Code CLI，在终端中使用；
2. 通过 Kimi Code for VS Code，在 VS Code 编辑器中使用；
3. 订阅用户可通过 API Key，接入 Claude Code、Roo Code、OpenCode 等第三方开发工具。
备注：CLI（Command-Line Interface，命令行界面）

## 核心优势

- **底层模型持续升级**：紧跟 Kimi 最新旗舰模型，持续获得前沿代码理解、推理与生成能力
- **广泛兼容**：完美适配 Kimi Code CLI、VS Code、Claude Code 等各类开发工具
- **极速响应**：最高输出速度可达 100 Tokens/s
- **高频并发**：每 5 小时支持约 300–1200 次请求，最高并发 30


## 开始使用

Kimi Code 支持会员在官方客户端和第三方平台使用权益，覆盖不同的开发场景。


### 使用官方客户端

选择适合你的客户端，一键安装：

#### 方式一：Kimi Code CLI
Kimi Code CLI 是一个运行在终端中的 AI Agent，帮助你完成软件开发任务和终端操作。它可以阅读和编辑代码、执行 Shell 命令、搜索和抓取网页，并在执行过程中自主规划和调整行动。

终端可以理解为：一个通过输入文字命令来操作电脑的窗口。

安装后，你可以在终端里和 AI 对话，让它帮你：
- 阅读代码
- 修改文件
- 执行命令
- 搜索网页
- 辅助完成开发任务
适合习惯终端操作的开发者。在终端中与 AI 对话，让它阅读代码、编辑文件、执行命令、搜索网页，自主完成开发任务。

如果你使用的是 macOS / Linux，请在终端中复制并运行：
```bash
# macOS / Linux
curl -LsSf https://code.kimi.com/install.sh | bash
```
如果你使用的是 Windows，请打开 PowerShell，复制并运行：
```powershell
# Windows (PowerShell)
Invoke-RestMethod https://code.kimi.com/install.ps1 | Invoke-Expression
```

安装完成后，在终端中运行 `kimi` 即可启动。


#### 方式二：Kimi Code for VS Code

适合偏好使用 VS Code 编辑器的开发者。在编辑器侧边栏与 AI 协同，支持代码补全、文件编辑、网页搜索和自动化任务。

在 VS Code 扩展市场搜索 "Kimi Code" 安装，或访问 [Visual Studio Marketplace](vscode:extension/moonshot-ai.kimi-code)。

>若安装后未显示扩展，请重启 VS Code 或在命令面板中执行 "Developer: Reload Window" (Mac: Cmd+Shift+P, Windows/Linux: Ctrl+Shift+P)。

其他编辑器如 JetBrains、Zed 可通过 CLI 的 ACP 协议接入使用，详见 [JetBrains 配置](/third-party-tools/jetbrains) 和 [Zed 配置](/third-party-tools/zed)。


### 方式三：第三方工具接入

安装官方客户端或接入第三方工具后，需要完成认证才能使用 Kimi Code 额度。

#### OAuth 自动认证（官方客户端）

使用 Kimi Code CLI 或 VS Code 扩展的用户，可通过 OAuth 授权自动接入，无需手动管理 API Key。

**Kimi Code**：通过 `/login` 命令自动登入 Kimi Code 平台，即完成接入

**Kimi Code for VS Code 插件**：安装后通过侧边栏登录按钮完成接入

#### API Key（第三方工具 / 自建应用）

Kimi Code 权益支持在主流 Coding Agent 中使用——例如 Claude Code、Roo Code、OpenCode 等；也可以配合 OpenClaw、Hermes 等通用 Agent 框架。让你在自己习惯的工具里自由调用 Kimi 的 AI 能力。

如果你要将 Kimi Code 接入第三方开发工具，需要手动配置 API Key。

#### 服务地址

Kimi Code API 同时兼容 OpenAI 和 Anthropic 两种协议，按需选择对应的 Base URL：

  | 协议 | Base URL |
  |------|----------|
  | OpenAI 兼容 | `https://api.kimi.com/coding/v1` |
  | Anthropic 兼容 | `https://api.kimi.com/coding/` |

#### 获取 API Key

Kimi 会员可在 [Kimi Code 控制台](https://www.kimi.com/code/console) 创建和管理（最多 5 个，仅创建时显示一次，请妥善保存）。

#### 模型 ID

在第三方工具中调用 Kimi Code API 时，请统一使用模型 ID `kimi-for-coding`。无论是 OpenAI 兼容协议还是 Anthropic 兼容协议，请求体里的 `model` 字段都填这个值。

> **说明**：`kimi-for-coding` 是固定的模型 ID，后端会根据最新发布的模型自动更新其对应的 display name，你无需变更客户端配置即可享受模型升级。

#### 配置到第三方工具

获取 API Key 后，将对应 Base URL 和 API Key 配置到对应工具的环境变量即可使用。配置详情见 [在其他 coding agent 中使用](/third-party-tools/other-coding-agents)。

> **注意**：使用时请保持工具的真实身份标识，篡改客户端标识（User-Agent）将被视为违规，可能导致会员权益暂停。

## 额度与限制

Kimi Code 的额度以订阅日为起点**每 7 天自动刷新**，未用完不累积。除了周额度外，还有**每 5 小时的滚动频率窗口**——即使总量充足，短时间请求过多也会触发限流，等窗口滚动后自动恢复。

所有登录设备和 API Key 共享同一套配额：无论从 CLI、VS Code 还是第三方工具发起请求，消耗的都是同一个账户的额度。超过 30 天未活跃的设备会被自动解绑，重新 `/login` 即可恢复。

登录 [Kimi Code 控制台](https://www.kimi.com/code/console) 可随时查看剩余额度与频限状态、管理 API Key 和登录设备。

> Kimi Code 与 Kimi 会员计划共享额度，如 Kimi 会员的月总额度达到上限，Kimi Code 额度会变为冻结状态，需等待月额度重置或升级订阅，月额度消耗可在 Kimi 主页设置中的 [订阅](https://www.kimi.com/membership/subscription) 查看。

## 平台对比

Kimi Code 会员权益专为编程场景设计。如需在自己的产品中调用大模型能力，或需要团队协作与用量管理，请访问 [Kimi 开放平台](https://platform.kimi.com)。

| 对比项 | Kimi Code 平台 | Kimi 开放平台 |
|--------|---------------|---------------|
| Base URL | Open AI 兼容： `https://api.kimi.com/coding/v1`<br> Anthropic 兼容：`https://api.kimi.com/coding/` | `https://api.moonshot.cn/v1` |
| 计费方式 | 会员订阅，按月/年付费，有频控限制 | 按量付费，充值即用 |
| 最佳场景 | 终端/IDE Agent 编程、多文件工程任务 | 产品集成、企业级调用、多模态应用开发 |


## 下一步

- [Kimi Code CLI 快速开始](/kimi-code-cli/getting-started) – 安装、登录、第一次对话
- [Kimi Code for VS Code 快速开始](/kimi-code-for-vscode/getting-started) – 安装扩展、登录、典型工作流
- [在更多第三方工具中使用](/third-party-tools/other-coding-agents) – Claude Code、Roo Code 等
- [常见问题](/kimi-code/faq) – 安装、登录、使用中的常见问题