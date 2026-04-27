# 快速开始

Kimi Code CLI 是一个运行在终端中的 AI Agent，帮助你完成软件开发任务和终端操作。它可以阅读和编辑代码、执行 Shell 命令、搜索和抓取网页，并在执行过程中自主规划和调整行动。

Kimi Code CLI 适合以下场景：

- **编写和修改代码**：实现新功能、修复 bug、重构代码
- **理解项目**：探索陌生的代码库，解答架构和实现问题
- **自动化任务**：批量处理文件、执行构建和测试、运行脚本

Kimi Code CLI 支持以下几种使用方式：

- **交互式命令行**（`kimi`）：在终端中以 Shell 方式与 AI 对话，支持自然语言描述任务或直接执行 Shell 命令
- **浏览器界面**（`kimi web`）：在本地浏览器中打开图形界面，支持会话管理、文件引用、代码高亮等
- **Agent 集成**（`kimi acp`）：以服务方式运行，通过 Agent Client Protocol 集成到 IDE 和其他本地 Agent 客户端中

> 如果你遇到问题或有建议，欢迎在 [GitHub Issues](https://github.com/MoonshotAI/kimi-cli/issues) 反馈。



## 开始之前

- **操作系统**：macOS、Linux 或 Windows（通过 PowerShell）
- **Kimi 账号**：需拥有 Kimi 会员订阅，或可调用的 API key


## 安装

运行安装脚本即可完成安装。脚本会先安装 [uv](https://docs.astral.sh/uv/)（Python 包管理工具），再通过 uv 安装 Kimi Code CLI：

```sh
# Linux / macOS
curl -LsSf https://code.kimi.com/install.sh | bash
```

```powershell
# Windows (PowerShell)
Invoke-RestMethod https://code.kimi.com/install.ps1 | Invoke-Expression
```

验证安装是否成功：

```sh
kimi --version
```


> 由于 macOS 的安全检查机制（Gatekeeper），首次运行 `kimi` 命令可能需要较长时间。可以在「系统设置 → 隐私与安全性 → 开发者工具」中添加你的终端应用来加速后续启动。

如果你已经安装了 uv，也可以直接运行：

```sh
uv tool install --python 3.13 kimi-cli
```

> Kimi Code CLI 支持 Python 3.12-3.14，但建议使用 3.13 以获得最佳兼容性。


## 第一次运行

### 启动与登录

在你想要工作的项目目录中命令启动 Kimi Code CLI：

```sh
cd your-project
kimi
```

首次启动时，输入 `/login` 配置 API 来源：

```
/login
```

推荐选择 **Kimi Code** 平台，会自动打开浏览器完成 OAuth 授权；选择其他平台则需要输入 API 密钥。配置完成后自动保存并重新加载。详见[平台与模型](/kimi-code-cli/configuration/providers-and-models)配置文档。


### 第一步：问一个问题

用自然语言提问，快速了解项目：

```
这个项目的整体架构是怎样的？入口文件在哪里？
```

Kimi Code CLI 会自动搜索和阅读相关文件，然后给出回答。

### 第二步：做一次代码修改

试试让 Kimi Code CLI 修改代码：

```
给 README 添加一个"快速开始"部分，包含安装和运行步骤
```

Kimi Code CLI 在修改文件前会展示 diff 并请求确认——你可以批准、拒绝，或直接输入反馈让它调整方向。它不会在未经允许的情况下改动你的代码。

### 第三步：执行一条命令

Kimi Code CLI 也可以运行 Shell 命令并分析结果：

```
运行测试，如果有失败的用例就修复它们
```

到这里，你已经体验了三个核心能力：**提问理解**、**修改代码**、**执行命令**。

>如果项目中没有 AGENTS.md 文件，可以运行 /init 命令让 Kimi Code CLI 分析项目并生成该文件，帮助 AI 更好地理解项目结构和规范。


## 常用命令速查

| 命令 | 说明 |
|------|------|
| `kimi` | 启动交互式对话 |
| `kimi web` | 打开浏览器图形界面 |
| `/login` | 配置或切换 API 来源 |
| `/usage` | 查看剩余额度和配额 |
| `/help` | 查看所有命令和快捷键 |
| `Ctrl-J` | 换行（不提交） |
| `Ctrl-C` / `Ctrl-D` | 中断当前操作 / 退出 |

完整命令列表请参考[斜杠命令](/kimi-code-cli/reference/slash-commands)和[键盘快捷键](/kimi-code-cli/reference/keyboard-shortcuts)。


## 常见问题

**我填了 API Key 怎么提示鉴权失败**

先确认你用的 Key 和 Base URL 是不是同一个平台的。`api.kimi.com` 和 `api.moonshot.cn` 是两个完全独立的账号体系，API Key 互不通用：

| 平台 | Base URL | 计费方式 | Key 创建入口 |
|------|---------|---------|-------------|
| **Kimi Code** | Open AI 兼容： `https://api.kimi.com/coding/v1`<br> Anthropic 兼容：`https://api.kimi.com/coding/` | Kimi 会员订阅（含额度） | [Kimi Code 控制台](https://www.kimi.com/code/console) |
| **Kimi 开放平台** | `https://api.moonshot.cn/v1` | 按量付费 | [Kimi 开放平台官网 ](https://platform.kimi.com) |


**安装后 `kimi` 命令找不到**

安装脚本会将 `kimi` 添加到 PATH，但需要重启终端或执行 `source ~/.bashrc`（或 `source ~/.zshrc`）才能生效。如果仍然找不到，检查 `~/.local/bin` 是否在你的 PATH 中。

**`/login` 后浏览器没有弹出**

如果在远程服务器或无图形界面的环境中，`/login` 会显示一个 URL，手动复制到浏览器打开即可完成授权。

更多问题请参考[常见问题](/kimi-code/faq)。


## 升级与卸载

升级到最新版本：

```sh
uv tool upgrade kimi-cli --no-cache
```

卸载 Kimi Code CLI：

```sh
uv tool uninstall kimi-cli
```


## 下一步

- [核心操作](/kimi-code-cli/core-operations) – 学习交互输入、上下文管理、工作模式等交互技巧
- [配置文件](/kimi-code-cli/configuration/configuration-files) — 自定义模型、行为和工具权限
- [MCP 集成](/kimi-code-cli/customization/mcp) — 连接外部工具和数据源扩展能力
