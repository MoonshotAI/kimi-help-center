---
title: "Getting started with Kimi"
slug: "agentic-chat"
order: 2
extract_headings: false
preview: false
---

<SeoMeta
  title="Getting started with Kimi - Kimi Help Center"
  description="You can type questions in the chat box, upload files, or switch between models depending on your needs."
/>

You can type questions in the chat box, upload files, or switch between models depending on your needs.

Open [kimi.com](https://kimi.com) and try sending a message — say hello to Kimi:

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "Hi, Kimi!",
    },
  ]}
/>

## Powered by K2.6
Kimi K2.6 is an open-source model that builds on K2.5 with significant upgrades, focusing on state-of-the-art coding, long-horizon execution, and agent swarm capabilities. It achieves state-of-the-art performance across agent tasks, coding, image understanding, video understanding, and general intelligence benchmarks. K2.6 is also Kimi's **most versatile** model — its native multimodal architecture supports both visual and text input, thinking and non-thinking modes, as well as conversational and agentic tasks.
As a result, Kimi excels not only at Q&A conversations but also at autonomous task planning, tool invocation, and multi-step reasoning — supporting deep thinking and execution for complex tasks.
### Built-in tools
Available out of the box, no configuration needed:
| Tool | Description |
|------|------------|
| **Web Search** | Real-time web search for the latest news and information |
| **Fetch Tool** | Direct access to specific URLs (web pages, documents, images, and other online resources) |
| **Data Source** | Connect to professional databases; query database listings and retrieve data |
| **Image Search** | Text-to-image and image-to-image search for quick visual content discovery |
| **IPython** | Execute Python code for data analysis and visualization |
| **Memory** | Smart memory that records your personal preferences and habits |

## Visual & multimodal capabilities
K2.6 supports full-scenario understanding of images, videos, and office documents (PDF/Word/Excel), using a **native multimodal architecture** (not bolt-on OCR). It can directly parse document content and perform intermediate-to-advanced office tasks (such as writing Excel formulas or generating PPT outlines/VBA code).
### Multimodal input support
- **Images**: PNG, JPEG, WebP, GIF, etc. (via URL, Base64, or local file upload)
- **Video**: MP4, etc. (via video_url or image frame sequences + fps parameter)
- **Documents**: PDF, Word, Excel, TXT, Markdown, etc.
- **Online resources**: URLs, article links
- **Image search**: Upload an image to search for related or similar images
- **Video understanding**: Supports video understanding — it can analyze screen recordings and replicate interaction logic
- **Visual coding**: Upload screenshots or screen recordings to generate frontend code (HTML/Vue/React, etc.); can automatically reproduce web pages from design mockups

### Output formats
- Plain text / mixed text-and-image: Standard conversational replies
- Markdown: Rich text with headings, lists, tables, and links
- Code blocks: HTML/Vue/React/Python/JSON/Mermaid, etc. (with language identifiers)
- JSON structured data: Forced JSON mode output
- Mermaid diagrams: Flowcharts, sequence diagrams, mind maps, etc.
- LaTeX math formulas: Inline and block-level mathematical expressions
- Dual-mode output (Thinking): Returns both `reasoning_content` (thinking process) and `content` (final answer)
- Tool call format: Function Calling standard format (for developers)

### Important notes

<Callout type="warning">
1. **Image generation limitation**: Standard chat mode only supports image *search*, not image *generation* (image generation requires K2.6 Agent mode).
2. **File output limitation**: Only text content is supported as output (e.g., PPT outlines, Word body text, code). Direct binary file output (`.pptx`, `.docx`, `.xlsx`, `.pdf`) is not supported.
3. For image generation or complex editable document output, use [K2.6 Agent](https://www.kimi.com/agent) or the code execution tool.
</Callout>

## Sessions vs. conversation turns
When you click "New Chat", think of it as starting a long conversation with Kimi.
| Concept | Analogy | Technical Definition |
|---------|---------|---------------------|
| **Session** | An entire meeting (from start to finish) | A complete chat process with a clear beginning and end |
| **Turn** | One exchange (you speak, Kimi replies) | Your input and Kimi's response form one round-trip |

### Key differences
**Session**
- **Continuous memory**: Kimi remembers all context within the current chat
- **Cross-turn context**: Each reply references prior conversation content as context for the next turn
- **Defined boundaries**: Clicking "New Chat" = fresh start; previous context is cleared
**Turn**
- **Cumulative count**: Turn 1, Turn 2, … incrementally added
- **Limited memory**: Too many turns (e.g., 50+) may cause Kimi to "forget" earlier content, especially for long-form writing or tasks with strict requirements
- **Context length constraint**: Limited by token count; when turns accumulate, the earliest content may be compressed

<Callout type="tip">
**Edge case**: If a single question-and-answer concludes the conversation, then 1 turn = 1 session.
</Callout>

## Why this distinction matters
Within a single session, each new question or instruction you send is answered with reference to all prior turns. As turns accumulate and content grows longer, response quality may gradually decline.

### Common scenarios
**Scenario 1: Switching topics**
- Wrong: Asking "help me calculate my taxes" in a session where you've been writing a 30,000-word novel
- Right: Start a new session for the tax question — avoid Kimi confusing novel characters with tax concepts
**Scenario 2: Long document processing**
- After dozens of turns, Kimi may "forget" rules or file summaries established at the start
- Solution: Proactively summarize mid-task ("Summarize our plan so far"), or start a new session
**Scenario 3: Understanding product limits**
- Context length limits are measured in tokens, but in everyday terms, think of it as "turns"
- If you see a "Start a new chat" prompt, it means the current session has too many turns
## Best practices

<Callout type="tip">
1. **Start a new session for each task**: Independent tasks — essay writing, research, debugging — should each get their own session to avoid context interference.
2. **Summarize periodically in long sessions**: After 20+ turns, proactively ask Kimi to summarize key information to prevent data loss.
3. **Clean up sensitive information promptly**: Chat history is retained; delete the entire session after handling private content.
</Callout>
