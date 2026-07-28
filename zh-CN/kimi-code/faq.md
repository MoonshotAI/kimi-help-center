---
title: "Kimi Code 常见问题"
slug: "faq"
order: 4
extract_headings: true
preview: true
preview_content: "Kimi Code 常见问题"
---

<SeoMeta
  title="Kimi Code 常见问题 - Kimi 帮助中心"
  description="了解 Kimi Code 的安装与鉴权、API密钥无效、会员过期、交互问题等"
/>

# 常见问题

## 从 Kimi-Cli 旧版迁移新版指南

<Callout type="info">
Kimi Code CLI 已完成重大版本升级，底层从 Python/uv 迁移至 Node.js，带来更简单的安装方式、更快的启动速度和全新的终端界面。旧版将逐渐停止维护，建议尽快升级至新版。
</Callout>

如果你正在从旧版迁移，按照以下步骤操作——一条命令就能把配置、MCP server 与会话历史一并迁移至新版。

### 新版优势

- **不再依赖 Python / uv**：基于 Node.js 重写，无需配置 Python 环境，安装更简单
- **原生二进制，开箱即用**：启动更快，运行更轻量
- **终端界面全面重设计**：交互体验更流畅
- **数据可完整迁移**：配置、MCP、会话历史一键带走，无缝延续

### 如何迁移

迁移有两种方式。

装好 kimi-code 之后**第一次运行 `kimi`** 时，它会自动检测 `~/.kimi/` 下是否存在 kimi-cli 的数据。一旦检测到，就会弹出迁移提示，你可以选择立即迁移、稍后再说，或不再提示。

你也可以**随时手动运行**：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "kimi migrate",
    },
  ]}
/>

你可以选择是否同时迁移聊天会话。如果暂时不需要历史记录，选 **Config only**；否则选 **Config + N sessions** 一并迁移。结束后会显示结果摘要。

### 迁移会发生什么

**会被迁移的内容**：配置（`config.toml`）、MCP 服务配置、输入历史，以及你选择迁移的聊天会话。

**不会被迁移的内容**：OAuth 登录凭证和 MCP 服务的授权都不会被复制，迁移后需要在 kimi-code 里重新执行 `/login` 和重新授权 MCP 服务。kimi-cli 的插件也不在迁移范围内。

<Callout type="tip">
迁移**不会改动或删除** `~/.kimi/` 下的任何旧数据。kimi-cli 仍可照常使用，两者互不影响。迁移也可以重复运行，已经迁移过的会话不会被重复导入。
</Callout>

迁移完成后，从 kimi-cli 导入的会话会带上 `[imported]` 标记，方便你与新建的会话区分。

## 安装与鉴权

### `/login` 时模型列表为空

如果在运行 `/login` 命令时看到 "No models available for the selected platform" 错误，可能是以下原因：

- **API 密钥无效或过期**：检查你输入的 API 密钥是否正确，以及是否仍有效。
- **网络连接问题**：确认能正常访问 API 服务地址（如 `api.kimi.com` 或 `api.moonshot.cn`）。

**注意区分平台**

 Kimi Code 会员权益与 [Kimi 开放平台](https://platform.kimi.com) 有不同的 Base URL，配置时请注意 Base URL 与 API Key 的匹配是否正确。

| 平台 | Base URL | 计费方式 | Key 创建入口 |
|------|---------|---------|-------------|
| **Kimi Code** | Anthropic 兼容：`https://api.kimi.com/coding/` | Kimi 会员订阅（含额度） | [Kimi Code 控制台](https://www.kimi.com/code/console) |
| **Kimi 开放平台** | `https://api.moonshot.cn/v1` | 按量付费 | [Kimi 开放平台官网](https://platform.kimi.com) |


### API 密钥无效

API 密钥无效可能的原因：

- **密钥输入错误**：检查是否有多余的空格或遗漏的字符。
- **密钥已过期或被撤销**：在平台控制台确认密钥状态。

### 会员过期或配额用尽

如果你使用 Kimi Code 平台，可以通过 `/usage` 命令查看当前的配额和会员状态。如果配额用尽或会员过期，需要在 [Kimi Code](https://kimi.com/code) 续费或升级。

## 订阅相关

### 如何开发票或升级会员

请前往 [Kimi 会员权益页面](https://www.kimi.com/membership/pricing#pricing-faq)，根据页面指引完成开票申请或会员升级操作。

## 交互问题

### 粘贴图片失败

使用 `Ctrl-V` 粘贴图片时，如果提示 "Current model does not support image input"，说明当前模型不支持图片输入。

解决方法：

- **切换到支持图片的模型**：使用支持 `image_in` 能力的模型。
- **检查剪贴板内容**：确保剪贴板中确实有图片数据，而非图片文件的路径。

## 更新与升级

### macOS 首次运行缓慢

macOS 的 Gatekeeper 安全机制会在首次运行新程序时进行检查，导致启动变慢。解决方法：

- **等待检查完成**：首次运行时耐心等待，后续启动会恢复正常。
- **添加到开发者工具**：在「系统设置 → 隐私与安全性 → 开发者工具」中添加你的终端应用。

### 如何升级 Kimi Code CLI

在 CLI 内运行 `kimi upgrade`，会自动检查最新版本并引导升级。也可以直接用包管理器：

```sh
npm install -g @moonshot-ai/kimi-code@latest
```

## VS Code 扩展常见问题

以下是 Kimi Code VS Code 扩展（VS Code Extension）的常见问题。

### VS Code 提示未打开工作区

请在 VS Code 中打开文件夹，Kimi Code VS Code 扩展需要工作区才能正常工作。

### VS Code 提示找不到 CLI

请手动安装 Kimi Code CLI 并在 VS Code 设置中配置 `kimi.executablePath`，或确保内置 CLI 存在。

### VS Code 登录失败

请尝试跳过登录使用 API 密钥模式，检查网络连接，或稍后通过 VS Code 扩展的操作菜单重试。

### VS Code 发送消息无响应

请确认 Kimi Code CLI 可用、模型已配置且 VS Code 中已打开工作区文件夹。通过 "Kimi Code: Show Logs" 查看错误日志。

### VS Code 连接超时

若 30 秒内无响应将超时。请检查网络后重试。

### VS Code 发消息前报错

某些错误会阻止在 VS Code 中发送消息，如 Kimi Code CLI 未找到、版本过低、未登录或会话忙碌。错误将以 toast 提示，你的输入将被保留以便重试。

## 反馈与联系

### 文档未能解决问题

如果以上内容未能解决你的问题，欢迎通过邮件联系我们：[code@moonshot.ai](mailto:code@moonshot.ai)。请在邮件中描述你遇到的问题、操作步骤及相关日志信息，我们会尽快回复。