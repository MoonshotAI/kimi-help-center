---
title: "Kimi WebBridge"
slug: "kimi-webbridge"
order: 15
extract_headings: false
preview: true
preview_content: "Let AI operate your browser — open pages, click buttons, fill forms, and automate repetitive web tasks."
---

<SeoMeta
  title="Kimi WebBridge - Kimi Help Center"
  description="Kimi WebBridge lets AI control your real Chrome browser with your login sessions, cookies, and accounts — to automate any web task."
  ogType="article"
/>

# Kimi WebBridge

Kimi WebBridge lets AI directly control your browser.

Not a simulator, not a scraper — it's your own Chrome browser, with your login sessions, your cookies, and all your accounts. AI can open pages, read content, click buttons, and fill out forms just like you would.

<Callout type="info">
Kimi WebBridge works with any local AI agent that supports MCP or shell skill installation, such as Kimi Desktop, Claude Code, Codex, and Open Claw.
</Callout>

<Frames
  src="./images/kimi-webbridge/kimi webbridge.png"
  alt="the main interface of kimi webbridge"
/>

---

## What Can You Do With It?

You talk — AI handles the clicking, form filling, screenshotting, and content reading. Hand off those repetitive web tasks:

- **Competitive analysis** — Automatically compare AI products like ChatGPT and Doubao across hundreds of test runs
- **Social media monitoring** — Browse Twitter/X, collect trending topics, and extract key insights
- **Recruitment automation** — Search job platforms like BOSS Zhipin, filter candidates, and organize results
- **Flight price comparison** — Search multiple travel sites and surface the best deals
- **Content research** — Scan trending topics across platforms and generate content angle suggestions

---

## Installation

### Step 1 — Install the Chrome Extension

Install the Kimi WebBridge browser extension from your browser's app store:

- **Chrome Web Store**: [Install from Chrome Web Store](https://chromewebstore.google.com)
- **Edge Add-ons Store**: Coming soon

If you cannot access the store directly, you can install it manually:

<Callout type="tip">
**Manual installation**

1. Download the extension package: [Download .zip](https://kimi-web-img.moonshot.cn/webbridge/install_skill.sh)
2. Unzip the file
3. Open `chrome://extensions/` in Chrome
4. Enable **Developer mode** (top-right toggle)
5. Click **Load unpacked** and select the unzipped folder
</Callout>

<Frames
  src="./images/kimi-webbridge/extension.png"
  alt="Chrome extensions page showing how to load the unpacked WebBridge extension"
/>

---

### Step 2 — Install the WebBridge Skill in Your Agent

Open your local AI agent and send one of the following messages depending on which agent you use.

**If you are using Kimi Desktop:**

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "Install Kimi Web Bridge: curl -fsSL https://kimi-web-img.moonshot.cn/webbridge/install_skill.sh | bash -s -- -y. Once installed, you can use my browser to perform any web operation.",
    },
  ]}
/>

**If you are using another AI agent (Claude Code, Codex, Open Claw, etc.):**

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "Install Kimi Web Bridge: curl -fsSL https://kimi-web-img.moonshot.cn/webbridge/install.sh | bash. Once installed, you can use my browser to perform any web operation.",
    },
  ]}
/>

---

### Step 3 — Test the Installation

Restart your agent to load the new skill, then send this message:

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "/skill:kimi-webbridge Open kimi.com for me",
    },
  ]}
/>

If the agent opens `kimi.com` in your browser, the installation is successful — your agent can now use the web.

<Frames
  src="./images/kimi-webbridge/test.png"
  alt="Agent successfully opening kimi.com in the browser after WebBridge installation"
/>

<Callout type="warning">
If the test fails, try restarting your agent first. The skill may need a fresh session to load correctly.
</Callout>

---

## Optional: Install Site-Specific CLI Tools

Without a site CLI, your agent can still operate any website — but it may need some time to explore the interface on its own.

With a site-specific CLI installed, the agent gains pre-built knowledge of that site's structure, which means **faster execution, fewer tokens used, and more accurate interactions**.

### Available CLIs

| CLI | Platform |
|---|---|
| `twitter-cli` | Twitter / X |
| `xiaohongshu-cli` | Xiaohongshu (Little Red Book) |
| `boss-cli` | BOSS Zhipin |
| `baidu-cli` | Baidu Search |
| `bing-cli` | Bing Search |
| `google-cli` | Google Search |
| `aichat-cli` | ChatGPT / Doubao |

You can also find additional community CLIs on the open-source community or in Kimi Gyro.

### How to Install a CLI?

You can paste the commands below directly into your terminal, or send them to your agent and let it handle the installation.

<CodePreview
  files={[
    {
      name: "install-cli.sh",
      language: "bash",
      content: `# Install gyro (Kimi's internal package manager) if you haven't already
sh -c "$(curl -fsSL https://gyro.msh.work/install/install.sh)"

# Browse available CLIs
gyro search cli

# Install the CLI you need — replace twitter-cli with your target CLI name
gyro install twitter-cli

# Keep it up to date
gyro upgrade twitter-cli`,
    },
  ]}
/>

<Callout type="tip">
Not comfortable with the terminal? Paste the commands above into your agent chat and ask it to run them for you.
</Callout>

---

## FAQ
 
### How does Kimi WebBridge work?
 
Kimi WebBridge pairs a local service with a browser extension. The agent sends commands to the local service, which uses Chrome DevTools Protocol to navigate, click, screenshot, and read pages in your existing Chrome or Edge browser — then sends the results back. Everything runs locally, so your login sessions and page content never leave your device.
 
### What if the extension shows as disconnected?
 
Make sure the Kimi WebBridge extension is installed in your browser. Then resend the connection command in Kimi Claw Desktop and run it again. Once it finishes, restart the Kimi Desktop App.
 
### Where is Kimi Claw Desktop?
 
Kimi Claw Desktop is a Kimi Claw that runs locally on your computer. Open the Kimi Desktop App, find Kimi Claw in the left sidebar, add a new Claw, and select **On my computer** to deploy.