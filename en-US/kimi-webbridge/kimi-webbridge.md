---
title: "Kimi WebBridge Introduction"
slug: "kimi-webbridge-introduction"
order: 1
extract_headings: false
preview: false
---

<SeoMeta
  title="Kimi WebBridge Introduction - Kimi Help Center"
  description="Kimi WebBridge is a browser extension designed for AI Agents. It runs directly in your Chrome or Edge browser, leveraging your existing login sessions to let Agents interact with web pages like a human."
  ogType="article"
/>

# Kimi WebBridge Introduction

Kimi WebBridge is a browser extension designed for AI Agents. Unlike cloud-based browser automation solutions, Kimi WebBridge runs directly in your Chrome or Edge browser, automatically leveraging your existing login sessions to let Agents interact with web pages like a human.

<VideoList
  column={1}
  list={[
    {
      url: "./videos/H265_LoRes_WebBridge_用户教程_EN.mp4",
      type: "video",
      caption: "Kimi WebBridge tutorial",
    },
  ]}
/>

<Callout type="tip">
We recommend deploying Kimi WebBridge on your primary work computer for the best browser automation experience.
</Callout>

<Callout type="info">
WebBridge works through a local bridge service and a browser extension. All execution happens locally on your device—login states and web page content never leave your machine.
</Callout>

<Frames
  src="./images/introduction.png"
  alt="WebBridge Introduction"
/>

## Step 1: download the Kimi WebBridge extension

You can download it through the following methods:

**Method 1: install from web store**

- For Chrome users: Go to [Chrome Web Store](https://chromewebstore.google.com/detail/kimi-webbridge/fldmhceldgbpfpkbgopacenieobmligc)
- For Edge users: Go to [Edge Add-ons](https://microsoftedge.microsoft.com/addons/detail/kimi-webbridge/bnlffdbcfnanfbknnlaflhlhkocccckg)

**Method 2: manual installation**

If you cannot access the web store, you can use the manual installation method.

Then follow the steps for your browser:

**Chrome:**

1. Download the extension package from the [Kimi WebBridge official website](https://www.kimi.com/features/webbridge).
2. Extract the downloaded file
3. Open `chrome://extensions/` in the address bar
4. Enable "Developer mode" in the top-right corner
5. Click "Load unpacked"
6. In the file picker, select the extracted WebBridge folder

<Frames
  src="./images/installation_chrome_en.png"
  alt="installation_chrome_en"
/>

**Edge:**

1. Download the extension package from the [Kimi WebBridge official website](https://www.kimi.com/features/webbridge).
2. Extract the downloaded file
3. Open `edge://extensions/` in the address bar
4. Enable "Developer mode" in the bottom-left corner
5. Click "Load unpacked"
6. In the file picker, select the extracted WebBridge folder

<Frames
  src="./images/installation_edge_en.png"
  alt="installation_edge_en"
/>

After installation, you should see WebBridge in your browser's extensions list. For easier access, we recommend pinning it to the browser toolbar.

## Step 2: Choose your setup method and complete configuration

### Method 1: Using with Kimi Work Desktop

1. Download Kimi Work from the [official website](https://www.kimi.com/zh-cn/products/kimi-work)

2. Once installed, you can send instructions in Kimi Work, for example:

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "Use Kimi Webbridge and open Xiaohongshu, search for posts about the Kimi K2.6 release",
    },
  ]}
/>

### Method 2: Pair with Local Agents

Supports Claude Code, Codex, Cursor, Kimi Code, Hermes Claw, and more.

1. Send the following command directly in the Agent to automatically install WebBridge. The Agent will run the appropriate setup based on your operating system.

If you are a macOS user, use the command below:

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

If you are a Windows user, use the command below:

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

2. Start Using

Once the extension is connected, you can send instructions.

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "Use Kimi WebBridge open X.com and search for posts about the Kimi K2.6 release",
    },
  ]}
/>


