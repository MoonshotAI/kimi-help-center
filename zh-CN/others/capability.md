---
title: "Kimi 能做什么？"
slug: "capability"
order: 2
extract_headings: true
preview: false
---

<SeoMeta
  title="Kimi 能做什么？ - Kimi 帮助中心"
  description="关于 Kimi 能力的常见问答：联网搜索与浏览器操作、操作电脑桌面（Kimi Computer Use）、生成图片/视频/语音、写代码建网站做 PPT 表格、文件处理、记忆、多语言支持与上下文长度。"
/>

# Kimi 能做什么？

## Kimi 能联网搜索、浏览网页吗？

可以。Kimi 会根据问题自动判断是否需要联网，并内置搜索工具进行检索。在 **Kimi Code、Kimi Work** 中，通过 **WebBridge**，Kimi 还能像人一样操作浏览器——浏览、点击、滚动、抓取数据、完成多步网页任务。

## Kimi 能操作我的电脑桌面吗？

在普通对话和 Agent 任务中，Kimi **没有权限**操作你的电脑；**Kimi Work 支持你主动选择开启**。

在 Kimi Work 中，通过 **Kimi Computer Use**，Kimi 可以代替你在桌面上点击、输入、滚动、拖拽，读取某个 app 的界面内容或截图。例如「帮我点一下 X」「在 Y 里输入…」「看看 Z app 现在什么状态」「列一下当前打开的 app」。所有操作在后台执行，不会抢占你的鼠标，也不切换前台窗口。

**如何安装**：在 Kimi Work 点击「插件」，选择「Kimi Computer Use」，点击安装。也可以在「Work」模式下发送以下指令安装：

<CodePreview
  files={[
    {
      name: "install.txt",
      language: "text",
      content: "帮我安装一下 kimi computer-use，curl -fsSL https://cdn.kimi.com/kimi-computer-use/latest/setup_macos.sh | bash",
    },
  ]}
/>

## Kimi 能生成图片、视频、语音吗？

可以，通过创意设计类插件生成图像、视频和音频（在插件市场安装对应插件后使用）：

- **图像生成**：根据文字描述生成高质量图像，支持 1K/2K/4K 分辨率与多种比例，可选不透明或透明背景，输出 JPG / PNG。
- **视频生成**：根据文字描述（可搭配参考图）生成高质量视频，支持 16:9、4:3、1:1、3:4、9:16、21:9 等比例，时长 4–12 秒。
- **音频生成**：支持文字转语音（多种普通话音色），或根据英文描述生成音效（时长 0.5–22 秒）。

## Kimi 能写代码、建网站、做 PPT 和表格吗？

可以。作为能自主执行任务的 AI Agent，Kimi 支持建站、PPT 制作、文档与表格处理、深度研究等。

## Kimi 支持处理哪些文件？

支持 PDF、Word、Excel、PPT、图片、TXT、视频等常见格式，**单个文件不超过 100MB，单次最多 50 个文件**。

## Kimi 有记忆吗？

有。[记忆](/features/memory-space)会自动保留关键信息，让 Kimi 更懂你；如需按项目隔离记忆与资料，可使用[项目](/features/project)功能。

## Kimi 支持多语言吗？

支持。界面语言可在 **「设置」→「通用」→「语言」** 中切换，目前支持：德语、俄语、法语、繁体中文、韩语、葡萄牙语、泰语、土耳其语、西班牙语、意大利语、印度尼西亚语、英语、越南语。K2.6、K3 均支持多语言的对话、检索与创作。

## Kimi 单次能处理多长的内容？

K2.6 的单轮上下文约为 **128K token（约 5-6 万汉字）**；处理超长文档时，**K3 提供 100 万 token 上下文**（需最高档会员权益）。更多见[会话超 20 万字了怎么办？](/others/chat-issues)。
