---
title: "定制化和更多参考"
slug: "cli-customization"
order: 10
extract_headings: false
preview: true
preview_content: "Kimi Code 定制化配置：AGENTS.md、MCP 与环境变量。"
---

<SeoMeta
  title="Kimi Code CLI 定制化配置指南 - Kimi 帮助中心"
  description="深入了解 Kimi Code CLI 的配置文件（config.toml）、AGENTS.md 项目配置、自定义 System Prompt、MCP 集成和环境变量设置。"
/>

# 定制化与参考

Kimi Code CLI 提供了丰富的定制化选项，让你可以根据自己的需求调整 AI 的行为和工作方式。

## 配置文件

Kimi Code CLI 使用 `~/.kimi/config.toml` 作为全局配置文件，支持 TOML 和 JSON 两种格式。你可以在配置文件中设置：

- **API 供应商和模型**：配置不同的模型提供商、API 地址和密钥。
- **默认模型**：指定默认使用的模型。
- **运行参数**：调整超时、并发、输出格式等运行时参数。

<Callout type="tip">
使用 `/config` 命令可以快速打开配置文件进行编辑。
</Callout>

## AGENTS.md 项目配置

在项目根目录放置 `AGENTS.md` 文件，可以为 AI 提供项目级别的上下文信息：

- **项目背景**：描述项目的功能、架构和技术栈。
- **构建步骤**：如何安装依赖、构建项目、运行测试。
- **代码规范**：命名规范、目录结构约定、代码风格偏好。
- **注意事项**：需要特别注意的安全限制、性能要求等。

使用 `/init` 命令可以让 AI 自动扫描项目并生成初始的 `AGENTS.md`。你也可以手动编辑该文件，添加更多项目特定的信息。`AGENTS.md` 可以放在项目的任意子目录中，AI 会自动加载相关的配置。

## 自定义 System Prompt

你可以通过以下方式自定义 AI 的 system prompt：

- **全局 system prompt**：在 `~/.kimi/AGENTS.md` 中编写，对所有项目生效。
- **项目级 system prompt**：在项目根目录的 `AGENTS.md` 中编写，仅对当前项目生效。
- **启动参数**：使用 `--system-prompt` 参数在启动时指定。

项目级配置会覆盖全局配置，启动参数优先级最高。

## MCP 集成

Kimi Code CLI 支持 Model Context Protocol（MCP），可以连接外部工具和数据源，扩展 AI 的能力：

- **MCP 服务器配置**：在配置文件中添加 MCP 服务器地址，AI 即可调用外部工具。
- **内置 MCP 支持**：部分常用的 MCP 工具已内置，无需额外配置。
- **自定义 MCP 服务器**：你可以开发自己的 MCP 服务器，为 AI 提供特定领域的能力。

MCP 配置可以写在 `~/.kimi/config.toml` 或项目级别的配置文件中。

## 环境变量

Kimi Code CLI 支持通过环境变量进行配置，适合在 CI/CD 或脚本中使用：

| 环境变量 | 说明 |
| --- | --- |
| `KIMI_API_KEY` | API 密钥 |
| `KIMI_BASE_URL` | 自定义 API 地址 |
| `KIMI_MODEL` | 默认模型名称 |
| `KIMI_MAX_TOKENS` | 最大输出 token 数 |

环境变量的优先级高于配置文件中的设置。

## 更多参考

- **斜杠命令参考**：使用 `/help` 查看所有可用命令。
- **CLI 参数参考**：运行 `kimi --help` 查看所有启动参数。
- **官方文档**：访问 [Kimi Code 文档](https://kimi.com/code/docs) 获取最新的完整文档。
