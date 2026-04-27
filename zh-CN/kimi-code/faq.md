# 常见问题

## 安装与鉴权

### `/login` 时模型列表为空

如果在运行 `/login`（或 `/setup`）命令时看到 "No models available for the selected platform" 错误，可能是以下原因：

- **API 密钥无效或过期**：检查你输入的 API 密钥是否正确，以及是否仍有效。
- **网络连接问题**：确认能正常访问 API 服务地址（如 `api.kimi.com` 或 `api.moonshot.cn`）。

**注意区分平台**

 Kimi Code 会员权益与 [Kimi 开放平台](https://platform.kimi.com) 有不同的 Base URL，配置时请注意 Base URL 与 API Key 的匹配是否正确。

| 平台 | Base URL | 计费方式 | Key 创建入口 |
|------|---------|---------|-------------|
| **Kimi Code** | Open AI 兼容： `https://api.kimi.com/coding/v1`<br> Anthropic 兼容：`https://api.kimi.com/coding/` | Kimi 会员订阅（含额度） | [Kimi Code 控制台](https://www.kimi.com/code/console) |
| **Kimi 开放平台** | `https://api.moonshot.cn/v1` | 按量付费 | [Kimi 开放平台官网 ](https://platform.kimi.com) |


### API 密钥无效

API 密钥无效可能的原因：

- **密钥输入错误**：检查是否有多余的空格或遗漏的字符。
- **密钥已过期或被撤销**：在平台控制台确认密钥状态。
- **环境变量覆盖**：检查是否有 `KIMI_API_KEY` 或 `OPENAI_API_KEY` 环境变量覆盖了配置文件中的密钥。可以运行 `echo $KIMI_API_KEY` 检查。

### 会员过期或配额用尽

如果你使用 Kimi Code 平台，可以通过 `/usage` 命令查看当前的配额和会员状态。如果配额用尽或会员过期，需要在 [Kimi Code](https://kimi.com/coding) 续费或升级。

## 交互问题

### Shell 模式中 `cd` 命令无效

在 Shell 模式中执行 `cd` 命令不会改变 Kimi Code CLI 的工作目录。这是因为每次 Shell 命令在独立的子进程中执行，目录切换只在该进程内生效。

如果需要切换工作目录：

- **退出并重新启动**：在目标目录中重新运行 `kimi` 命令。
- **使用 `--work-dir` 参数**：启动时指定工作目录，如 `kimi --work-dir /path/to/project`。
- **在命令中使用绝对路径**：直接使用绝对路径执行命令，如 `ls /path/to/dir`。

### 工作目录被删除或移除

如果在会话期间工作目录变得不可访问（外置硬盘拔出、目录被删除或文件系统卸载），Kimi Code CLI 会检测到这一情况并显示崩溃报告，包含会话 ID 和工作目录路径，之后干净退出。你可以通过 `kimi -r <session-id>` 在正确的目录中恢复会话。

### 粘贴图片失败

使用 `Ctrl-V` 粘贴图片时，如果提示 "Current model does not support image input"，说明当前模型不支持图片输入。

解决方法：

- **切换到支持图片的模型**：使用支持 `image_in` 能力的模型。
- **检查剪贴板内容**：确保剪贴板中确实有图片数据，而非图片文件的路径。

## ACP 问题

### IDE 无法连接到 Kimi Code CLI

如果 IDE（如 Zed 或 JetBrains IDE）无法连接到 Kimi Code CLI，请检查以下几点：

- **确认 Kimi Code CLI 已安装**：运行 `kimi --version` 确认安装成功。
- **检查配置路径**：确保 IDE 配置中的 Kimi Code CLI 路径正确。通常可以使用 `kimi acp` 作为命令。
- **检查 uv 路径**：如果使用 uv 安装，确保 `~/.local/bin` 在 PATH 中。可以使用绝对路径，如 `/Users/yourname/.local/bin/kimi acp`。
- **查看日志**：检查 `~/.kimi/logs/kimi.log` 中的错误信息。

## MCP 问题

### MCP 服务启动失败

添加 MCP 服务器后，如果工具未加载或报错，可能是以下原因：

- **命令不存在**：对于 stdio 类型的服务器，确保命令（如 `npx`）在 PATH 中。可以使用绝对路径配置。
- **配置格式错误**：检查 `~/.kimi/mcp.json` 是否为有效的 JSON 格式。运行 `kimi mcp list` 查看当前配置。

调试步骤：

```sh
# 查看已配置的服务器
kimi mcp list

# 测试服务器是否正常
kimi mcp test <server-name>
```

### OAuth 授权失败

对于需要 OAuth 授权的 MCP 服务器（如 Linear），如果授权失败：

- **检查网络连接**：确保能访问授权服务器。
- **重新授权**：运行 `kimi mcp auth <server-name>` 重新进行授权。
- **重置授权**：如果授权信息损坏，可以运行 `kimi mcp reset-auth <server-name>` 清除后重试。

### Header 格式错误

添加 HTTP 类型的 MCP 服务器时，Header 格式应为 `KEY: VALUE`（冒号后有空格）。例如：

```sh
# 正确
kimi mcp add --transport http context7 https://mcp.context7.com/mcp --header "CONTEXT7_API_KEY: your-key"

# 错误（缺少空格或使用等号）
kimi mcp add --transport http context7 https://mcp.context7.com/mcp --header "CONTEXT7_API_KEY=your-key"
```

## Print/Wire 模式问题

### JSONL 输入格式无效

使用 `--input-format stream-json` 时，输入必须是有效的 JSONL（每行一个 JSON 对象）。常见问题：

- **JSON 格式错误**：确保每行是完整的 JSON 对象，没有语法错误。
- **编码问题**：确保输入使用 UTF-8 编码。
- **换行符问题**：Windows 用户注意检查换行符是否为 `\n` 而非 `\r\n`。

正确的输入格式示例：

```json
{"role": "user", "content": "你好"}
```

### Print 模式无输出

如果 `--print` 模式下没有输出，可能是：

- **未提供输入**：需要通过 `--prompt`（或 `--command`）或 stdin 提供输入。例如：`kimi --print --prompt "你好"`。
- **输出被缓冲**：尝试使用 `--output-format stream-json` 获取流式输出。
- **配置未完成**：确保已通过 `/login` 配置 API 密钥和模型。

## 更新与升级

### macOS 首次运行缓慢

macOS 的 Gatekeeper 安全机制会在首次运行新程序时进行检查，导致启动变慢。解决方法：

- **等待检查完成**：首次运行时耐心等待，后续启动会恢复正常。
- **添加到开发者工具**：在「系统设置 → 隐私与安全性 → 开发者工具」中添加你的终端应用。

### 如何升级 Kimi Code CLI

使用 uv 升级到最新版本：

```sh
uv tool upgrade kimi-cli --no-cache
```

添加 `--no-cache` 参数可以确保获取最新版本。

### 启动时弹出更新提醒

当后台检查发现新版本时，Kimi Code CLI 会在 Shell 启动前显示一个阻断式更新提醒，列出当前版本和最新版本信息。你可以通过以下按键选择操作：

- **Enter**：立即升级到最新版本
- **q**：暂时跳过，下次启动时继续提醒
- **s**：跳过该版本，不再提醒（直到有更新的版本发布）

### 如何禁用更新提醒

如果不希望 Kimi Code CLI 在后台检查更新，可以设置环境变量：

```sh
export KIMI_CLI_NO_AUTO_UPDATE=1
```

可以将此行添加到你的 shell 配置文件（如 `~/.zshrc` 或 `~/.bashrc`）中。

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

某些错误会阻止在 VS Code 中发送消息，如 Kimi Code CLI 未找到、版本过低、未登录或会话忙碌。错误将以 toast 提示，您的输入将被保留以便重试。

## 反馈与联系

### 文档未能解决问题

如果以上内容未能解决您的问题，欢迎通过邮件联系我们：[code@moonshot.ai](mailto:code@moonshot.ai)。请在邮件中描述您遇到的问题、操作步骤及相关日志信息，我们会尽快回复。