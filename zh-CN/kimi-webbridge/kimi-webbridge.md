---
title: "Kimi WebBridge产品介绍"
slug: "kimi-webbridge-introduction"
order: 1
extract_headings: false
preview: false
---

<SeoMeta
  title="Kimi WebBridge 产品介绍 - Kimi Help Center"
  description="Kimi WebBridge 是一款专为 AI Agent 设计的浏览器插件，支持 Chrome 和 Edge，让 Agent 像真人一样与网页交互。"
  ogType="article"
/>

# Kimi WebBridge产品介绍

Kimi WebBridge 是一款专为 AI Agent 设计的浏览器插件。与云端浏览器自动化方案不同，Kimi WebBridge 直接在你正在使用的 Chrome 或 Edge 浏览器中执行操作，能够自动获取你的登录态，让 Agent 像真人一样与网页交互。

<VideoList
  column={1}
  list={[
    {
      url: "./videos/H265_LoRes_WebBridge_用户教程_CN.mp4",
      type: "video",
      caption: "Kimi WebBridge 视频教程",
    },
  ]}
/>

<Frames
  src="./images/introduction-cn.png"
  alt="introduction-cn"
/>

<Callout type="tip">
建议在主力工作电脑上部署 Kimi WebBridge，以获得最佳的浏览器自动化体验。
</Callout>

<Callout type="info">
WebBridge 通过本地桥接服务和浏览器扩展协同工作，所有执行都在你本地完成，登录态和网页内容不会离开你的设备。
</Callout>


| 项目 | 系统要求 |
|------|------|
| 操作系统 | macOS 或 Windows |
| 浏览器 | Chrome 或 Edge |
| 网络 | 需要稳定的网络连接 |
| 配套应用 | Kimi Work 或其他 Local Agent |

## Step 1: 下载 Kimi WebBridge 插件

你可以通过以下方式下载：

**方式一：应用商店安装**

- Chrome 用户：前往 [Chrome Web Store](https://chromewebstore.google.com/detail/kimi-webbridge/fldmhceldgbpfpkbgopacenieobmligc)
- Edge 用户：前往 [Edge Add-ons](https://microsoftedge.microsoft.com/addons/detail/kimi-webbridge/bnlffdbcfnanfbknnlaflhlhkocccckg)

**方式二：手动安装**

如果你暂时无法访问浏览器应用商店，可以使用手动安装方式。

然后根据你使用的浏览器完成安装：

**Chrome：**

1. 前往 [Kimi WebBridge 官网](https://www.kimi.com/zh-cn/features/webbridge) 下载插件安装包。
2. 解压下载好的文件
3. 在浏览器地址栏输入 `chrome://extensions/`
4. 打开右上角的“开发者模式”
5. 点击“加载已解压的扩展程序”
6. 在文件选择窗口中，选中解压后的 WebBridge 文件夹

<Frames
  src="./images/installation_chrome_cn.png"
  alt="installation_chrome_cn"
/>

**Edge：**

1. 前往 [Kimi WebBridge 官网](https://www.kimi.com/zh-cn/features/webbridge) 下载插件安装包。
2. 解压下载好的文件
3. 在浏览器地址栏输入 `edge://extensions/`
4. 打开左下角的“开发者模式”
5. 点击“加载已解压的扩展程序”
6. 在文件选择窗口中，选中解压后的 WebBridge 文件夹

<Frames
  src="./images/installation_edge_cn.png"
  alt="installation_chrome_cn"
/>

安装完成后，你会在浏览器扩展列表中看到 WebBridge。为了后续使用更方便，建议将它固定到浏览器工具栏。

## Step 2: 选择使用方式并完成配置

### 方式一：搭配 Kimi Work Desktop

1. 通过[官网](https://www.kimi.com/zh-cn/products/kimi-work)下载 Kimi Work

2. 安装成功后即可在 Kimi Work 中发送指令，例如：

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "使用Kimi WebBridge 帮我打开小红书，搜索关于 Kimi K2.6 发布的帖子",
    },
  ]}
/>

### 方式二：搭配 Local Agent

支持 Claude Code、Codex、Cursor、Kimi Code、Hermes Claw 等。


1. 在 Agent 中直接发送以下指令，即可自动完成 WebBridge 安装。Agent 会根据你的操作系统自动执行对应的安装流程。

如果你是 macOS 用户，请使用以下命令：

<CodePreview
  files={[
    {
      name: "macos.sh",
      language: "bash",
      content:
        "curl -fsSL https://kimi-web-img.moonshot.cn/webbridge/install_skill.sh | bash -s -- -y",
    },
  ]}
/>

如果你是 Windows 用户，请使用以下命令：

<CodePreview
  files={[
    {
      name: "windows.ps1",
      language: "powershell",
      content:
        "irm https://kimi-web-img.moonshot.cn/webbridge/install.ps1 | iex",
    },
  ]}
/>

2. 开始使用

插件连接成功后即可发送指令，例如：

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "使用Kimi WebBridge 帮我打开小红书，搜索关于 Kimi K2.6 发布的帖子",
    },
  ]}
/>

