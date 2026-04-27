---
title: "准备工作"
slug: "preparation"
order: 0
extract_headings: false
preview: true
preview_content: "使用 Kimi Code 前需要了解的基础知识：终端、PowerShell、CLI 及安全注意事项。"
---
<SeoMeta
  title="使用 Kimi Code 前的准备工作 - Kimi 帮助中心"
  description="了解终端、PowerShell、CLI 的基础概念，以及如何安全地使用 Kimi Code CLI 进行开发。"
/>
# 准备工作

在使用 Kimi Code 之前，你需要了解几个基础概念。这些知识能帮助你更顺畅地安装和使用 Kimi Code。

## 终端是什么

**终端**是一个通过输入文字命令来操作电脑的窗口。

你可以把它理解为一个"文字版的文件管理器"：在终端里，你通过输入命令（如 `ls`、`cd`、`mkdir`）来查看文件夹内容、切换目录、创建文件等，而不是用鼠标点击图标。

### 怎么打开终端

| 操作系统 | 打开方式 |
|---------|---------|
| **macOS** | 按 `Cmd + 空格`，输入 "Terminal" 或 "终端"，回车打开 |
| **Windows** | 按 `Win + R`，输入 `powershell` 或 `wt`；<br>或在开始菜单搜索 "PowerShell"/"终端" |
| **Linux** | 按 `Ctrl + Alt + T`，或从应用菜单中找到"终端" |

### 怎么查看自己的操作系统

- **macOS**：点击屏幕左上角的苹果图标 → "关于本机"
- **Windows**：按 `Win + Pause/Break` 键，或右键点击"此电脑" → "属性"
- **Linux**：在终端中运行 `uname -a` 或 `cat /etc/os-release`

## PowerShell 是什么

**PowerShell** 是 Windows 上常用的终端工具，功能比普通命令提示符（CMD）更强大。Kimi Code CLI 在 Windows 上的安装和操作都需要在 PowerShell 中完成。

Windows 上有两个不同的"命令行"工具，不要混淆：

| 工具 | 说明 | 是否适用 |
|-----|------|---------|
| **CMD（命令提示符）** | Windows 最基础的命令行工具 | ❌ 不推荐 |
| **PowerShell** | 功能更强大的现代命令行工具 | ✅ 推荐 |

> **提示**：Kimi Code CLI 的安装命令需要在 PowerShell 中运行，CMD 中可能无法正常执行。

## 工作目录

Kimi Code CLI 启动时会以你当前所在的文件夹作为**工作目录**，它只能读取和修改工作目录内的文件。

**启动前先确认终端的当前路径**：

- 终端提示符通常会显示当前目录，如 `~/projects/my-app$`
- 输入 `pwd`（macOS/Linux）或 `cd`（Windows）可查看完整路径
- 用 `cd 文件夹名` 进入目标项目目录后再运行 `kimi`

> **示例**：假设你的项目在 `~/Documents/my-project`，启动流程是：
> 1. 打开终端
> 2. 输入 `cd ~/Documents/my-project`
> 3. 输入 `kimi` 启动

## 命令怎么运行

在终端或 PowerShell 中运行命令很简单：

1. **复制命令**：从文档中复制命令文本
   - macOS/Linux：`curl -LsSf https://code.kimi.com/install.sh | bash`
   - Windows：`Invoke-RestMethod https://code.kimi.com/install.ps1 | Invoke-Expression`
2. **粘贴到终端**：在终端窗口中按右键或 `Cmd/Ctrl + V` 粘贴
3. **按下回车**：按 `Enter` 键执行命令
4. **等待完成**：终端会显示执行过程和结果

> **注意**：在终端中，`Ctrl+C` 通常是**中断当前命令**，而不是复制。复制请用 `Cmd/Ctrl + Shift + C`，粘贴用 `Cmd/Ctrl + Shift + V`，或直接用鼠标右键菜单。

> **提示**：如果命令执行过程中需要输入密码，终端不会显示任何字符（这是正常的安全机制），直接输入后回车即可。

## CLI 是什么

**CLI** 是 **C**ommand-**L**ine **I**nterface（命令行界面）的缩写，意思是通过输入文字命令来使用工具，而不是通过图形界面点击按钮。

Kimi Code CLI 就是一个命令行工具：你在终端中输入 `kimi` 启动它，然后通过文字命令与 AI 交互，让它帮你阅读代码、修改文件、执行命令等。

## 网络环境

使用 Kimi Code 需要能够访问 Kimi 的服务器。如果你的网络环境有以下限制，可能需要调整：

- **公司/学校网络**：部分内网环境可能限制访问外部 API。如有代理，可在配置中设置代理地址。
- **VPN/代理**：如果使用了全局代理，确保代理不会拦截或干扰到 `api.kimi.com` 或 `api.moonshot.cn` 的请求。
- **防火墙**：检查系统或路由器防火墙是否阻止了终端程序的网络访问。

## 安全注意事项

Kimi Code CLI 是一个功能强大的 AI Agent，它可能会：

- **读取**你电脑上的文件内容
- **修改**你的代码和配置文件
- **执行**Shell 命令（如安装依赖、运行测试）

**在使用时请注意**：

- **不要在敏感目录中启动**：避免在包含密码、密钥、个人隐私文件的目录中运行 Kimi Code CLI。
- **仔细审查操作**：Kimi Code 在执行文件修改或命令前会征求你的确认，不要习惯性地点击"同意"。
- **先理解再执行**：如果你不确定某个操作的影响，可以让 Kimi Code 先解释清楚这个操作会做什么，再决定是否继续。
- **备份重要代码**：在对重要项目使用 Kimi Code 之前，建议先提交代码到版本控制（如 Git），以便随时回退。

> **建议**：初次使用时，可以在一个测试项目或副本项目中熟悉 Kimi Code CLI 的工作方式，熟悉后再用于正式项目。
