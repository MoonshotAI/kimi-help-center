---
title: "PPT 常见问题与排查"
slug: "ppt-troubleshooting"
order: 3
extract_headings: false
preview: true
preview_content: "PPT 功能找不到、打不开或预览异常的排查方法与反馈指引。"
---
<SeoMeta
  title="PPT 找不到或打不开怎么办？常见问题排查 - Kimi 帮助中心"
  description="PPT 功能入口找不到、文件打不开或下载异常？本文提供全面排查方案，涵盖各端入口指引、浏览器拦截修复和文件损坏处理。"
  pageUrl="https://www.kimi.com/help/ppt/ppt-troubleshooting"
/>

# 常见问题与排查

如果你遇到 PPT 功能入口找不到、生成的 PPT 无法打开或下载后文件异常等问题，可参考以下排查步骤。


## PPT 功能入口

1. **网页版**：打开 [kimi.com](https://www.kimi.com/)，在对话输入框下方点击「PPT」快捷入口，或直接访问 [PPT 助手](https://www.kimi.com/slides)
2. **App 端**：打开 Kimi App，点击输入框下方工具栏中的「PPT」按钮
3. **Agent 模式**：在通用 Agent 模式下直接描述 PPT 需求，Kimi 会自动调用 PPT 生成能力


## 生成 PPT 时卡住怎么办

当前 PPT 在生成流程中卡住有以下情况：
- 生成 PPT 时任务中断：点击下方右侧按钮继续任务即可，模型会继续完成 PPT 的制作。
- PPT 任务已取消：通常是 PPT 助手生成失败导致的，新建对话输入相同任务指令再次生成即可。

<Callout type="info">
如需进一步帮助，可通过产品内「👎」反馈通道联系工作人员，或发送邮件至 [support@moonshot.cn](mailto:support@moonshot.cn)。
</Callout>


## PPT 卡片弹出和预览问题

模型完成 PPT 制作后，对话末尾会提示"可点击下方卡片预览"并弹出 PPT 卡片，点击该卡片即可顺利进入 PPT 编辑页。

<Frames
  src="./images/ppt/pptcard.png"
  alt="image"
/>
如果点击 PPT 卡片未能顺利进入编辑页，请尝试刷新页面后重新打开；如仍无法打开，可清除浏览器缓存后重试。 

### PPT 卡片未正常弹出

- 使用 Chrome、Safari、Firefox 等其他浏览器打开同一对话，查看是否能正常显示 PPT 卡片
- 在手机 App 或其他电脑上登录同一账号，查看该对话中是否有 PPT 结果
- 如果多个浏览器和设备均无法看到正确的 PPT 卡片，请参考下方 [Bug 反馈指引](#bug-反馈指引) 提交反馈，并新建对话重新生成

<Callout type="tip">
如果确认多设备、多浏览器均无法查看，请发送邮件至 [support@moonshot.cn](mailto:support@moonshot.cn) 反馈，附上对话链接和问题截图。经核实确认为 Bug 后，我们将为你补偿相应额度。
</Callout>

### PPT 预览空白或样式错乱

- 建议使用 Chrome、Edge、Safari 等主流浏览器的最新版本
- 检查网络连接是否稳定，PPT 预览需要加载在线资源
- 尝试切换浏览器或使用无痕模式排除插件干扰


## PPT如何下载
- **网页版**： 在PPT编辑界面，点击右上角的【下载】按钮，即可点击确认开始下载文件。如果下载遇到问题，请检查当前网络连接是否稳定，或更换浏览器重试
- **App端** ： PPT 生成后，点击【导出】即可选择分享到微信等应用


## PPT 下载后打不开

- **网页版**：尝试刷新页面后重新打开；如仍无法打开，清除浏览器缓存后重试
- **下载后打不开**：确认使用 Microsoft PowerPoint、WPS 或 Keynote 等支持 `.pptx` 格式的软件打开；部分旧版本办公软件可能不兼容
- **文件为 0KB 或损坏**：通常为生成过程异常导致，请新建对话重新生成

<Callout type="tip">
部分旧版办公软件可能不兼容，下载后若无法打开，建议下载最新办公软件。
</Callout>



## Bug 反馈指引

如果以上方法无法解决问题，请通过产品内「👎」反馈通道或发送邮件至 [support@moonshot.cn](mailto:support@moonshot.cn) 提交反馈。为了帮助我们更快定位问题，请尽量提供以下信息：

| 信息类型       | 具体内容                                                   |
|----------------|------------------------------------------------------------|
| **浏览器信息** | 浏览器名称及版本号（如 Chrome 126、Safari 18.1、Edge 126） |
| **系统信息**   | 电脑：操作系统及版本（如 macOS 15.4、Windows 11 24H2）；手机：系统及版本（如 iOS 18.4、Android 15、鸿蒙 5.0）以及手机型号 |
| **问题截图**   | 截取异常页面的完整浏览器窗口或 App 界面                     |
| **操作步骤**   | 简述触发问题的操作流程，方便复现                            |

<Callout type="tip">
**如何查看浏览器版本：** Chrome 点击右上角「⋮ → 帮助 → 关于 Google Chrome」；Safari 点击菜单栏「Safari 浏览器 → 关于 Safari」；Edge 点击右上角「⋯ → 帮助和反馈 → 关于 Microsoft Edge」。
</Callout>

## 反馈入口

**网页版：** 官网左下角「账号 → 用户反馈 → 帮助与反馈」

<Frames
  src="./images/ppt/contact-feedback-01.png"
  alt="反馈入口"
/>

**PPT 结果页面：** 点击 PPT 结果页面右下角「☰」菜单按钮 →「用户反馈」→「PPT 专属反馈入口」，进入 PPT 反馈页面填写反馈信息

<Frames
  src="./images/ppt/troubleshooting-01.png"
  alt="PPT专属反馈入口"
/>
