---
title: "What can Kimi do?"
slug: "capability"
order: 2
extract_headings: true
preview: false
---

<SeoMeta
  title="What can Kimi do? - Kimi Help Center"
  description="FAQs about Kimi’s capabilities: online search and browser operation, controlling a computer desktop (Kimi Computer Use), generating images/videos/voice, writing code, building websites, creating PPTs and spreadsheets, file processing, memory, multilingual support, and context length."
/>

# What can Kimi do?

## Can Kimi search the internet and browse webpages?

Yes. Kimi automatically decides whether online access is needed for a question and uses built-in search tools to retrieve information. In **Kimi Code** and **Kimi Work**, with **WebBridge**, Kimi can also operate a browser like a person—browsing, clicking, scrolling, extracting data, and completing multi-step web tasks.

## Can Kimi operate my computer desktop?

In regular chats and Agent tasks, Kimi **does not have permission** to operate your computer. **In Kimi Work, you can choose to enable this yourself**.

In Kimi Work, with **Kimi Computer Use**, Kimi can click, type, scroll, drag, and read an app’s interface content or screenshots on your desktop for you. For example: “Click X for me,” “Enter … in Y,” “Check the current status of Z app,” or “List the apps currently open.” All operations run in the background, so Kimi will not take over your mouse or switch the foreground window.

**How to install**: In Kimi Work, click “Plugins”, select “Kimi Computer Use”, and click Install. You can also send the following instruction in “Work” mode to install it:

<CodePreview
  files={[
    {
      name: "install.txt",
      language: "text",
      content: "Please install kimi computer-use for me: curl -fsSL https://cdn.kimi.com/kimi-computer-use/latest/setup_macos.sh | bash",
    },
  ]}
/>

## Can Kimi generate images, videos, and voice?

Yes. Kimi can generate images, videos, and audio through creative design plugins. Install the corresponding plugin from the plugin marketplace before use:

- **Image generation**: Generate high-quality images from text descriptions. Supports 1K/2K/4K resolutions, multiple aspect ratios, optional opaque or transparent backgrounds, and JPG / PNG output.
- **Video generation**: Generate high-quality videos from text descriptions, with optional reference images. Supports aspect ratios such as 16:9, 4:3, 1:1, 3:4, 9:16, and 21:9, with durations of 4–12 seconds.
- **Audio generation**: Supports text-to-speech with multiple Mandarin voices, or sound effect generation from English descriptions, with durations of 0.5–22 seconds.

## Can Kimi write code, build websites, and create PPTs and spreadsheets?

Yes. As an AI Agent that can execute tasks autonomously, Kimi supports website building, PPT creation, document and spreadsheet processing, Deep Research, and more.

## What files can Kimi process?

Kimi supports common formats such as PDF, Word, Excel, PPT, images, TXT, and video. **Each file must be no larger than 100 MB, and you can upload up to 50 files at a time**.

## Does Kimi have memory?

Yes. [Memory](/features/memory-space) automatically saves key information so Kimi can understand you better. If you need to keep memory and materials separate by project, use the [Project](/features/project) feature.

## Does Kimi support multiple languages?

Yes. You can switch the interface language in **“Settings” → “General” → “Language”**. Currently supported languages include German, Russian, French, Traditional Chinese, Korean, Portuguese, Thai, Turkish, Spanish, Italian, Indonesian, English, and Vietnamese. K2.6 and K3 both support multilingual conversation, retrieval, and creation.

## How much content can Kimi process at once?

K2.6 has a single-turn context of about **128K tokens (roughly 50,000–60,000 Chinese characters)**. For ultra-long documents, **K3 provides a 1 million-token context** (requires the highest membership tier). For details, see [What should I do when a chat exceeds 200,000 Chinese characters?](/others/chat-issues).
