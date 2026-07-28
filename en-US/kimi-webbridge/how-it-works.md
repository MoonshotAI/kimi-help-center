---
title: "How Kimi WebBridge Works"
slug: "kimi-webbridge-how-it-works"
order: 2
extract_headings: true
preview: false
---

<SeoMeta
  title="How Kimi WebBridge Works - Kimi Help Center"
  description="Learn how Kimi WebBridge connects your browser to AI Agents locally, enabling secure web navigation, clicks, screenshots, and more."
  ogType="article"
/>

# How Kimi WebBridge Works

## Workflow

Kimi WebBridge operates as follows:

1. **Local Bridge Service**: A local service runs on your computer to receive instructions from the Agent
2. **Browser Extension**: Executes specific actions in the browser based on the Chrome DevTools Protocol
3. **Security Isolation**: All execution happens locally—login states and web page content never leave your device

<Frames
  src="./images/workflow.png"
  alt="workflow"
/>

## Extension Interface

Click the WebBridge icon in the browser toolbar to check the current connection status:

**Connected**: WebBridge is working properly and can collaborate with the Agent.

**Disconnected**: Check your configuration or re-run the connection command.

<Frames
  src="./images/connection.png"
  alt="WebBridge Connection"
/>

## Features

| Feature | Description |
|---------|-------------|
| Web Navigation | Automatically open specified URLs |
| Element Clicking | Simulate clicks on buttons, links, and other page elements |
| Form Filling | Automatically input text and select options |
| Page Screenshots | Capture the current page or a specific area |
| Content Extraction | Read page text, tables, and other structured data |
| Login Session Persistence | Use existing login states saved in the browser |

Use cases:

- E-commerce price comparison: Automatically search for products and compare prices across multiple platforms
- Information research: Deeply browse web pages and extract structured information
- Form filling: Automatically fill out various online forms
- Data entry: Automatically organize and enter web data into a specified format

For more use cases, please refer to the [Kimi WebBridge official website](https://www.kimi.com/features/webbridge).
