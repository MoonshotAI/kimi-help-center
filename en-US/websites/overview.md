---
title: "Kimi Websites"
slug: "Websites-overview"
order: 1
extract_headings: false
preview: true
preview_content: "Build and deploy websites from natural language descriptions, design mockups, or templates."
---

<SeoMeta
  title="Kimi Websites overview - Kimi Help Center"
  description="Build and deploy websites from natural language descriptions, design mockups, or templates."
/>

# Kimi Websites

<Callout type="info">
**Kimi Websites** is a Kimi Agent product feature powered by the latest Kimi K2.6 multimodal visual agent AI model. Its core capability is **Vibe Coding** — generating websites from natural language and deploying them online.
</Callout>

By understanding visual inputs (UI mockups, screenshots, interaction videos) and natural language instructions, Kimi translates user input into complete, runnable frontend code — covering not just static UI but also dynamic interactive behavior.

## Feature overview

| Feature | Description |
|---------|------------|
| **Conversational site building** | Describe your needs in natural language; AI automatically generates the website |
| **Image/Video understanding** | Upload design mockups/screenshots/screen recordings; AI parses and generates HTML pages |
| **Auto-deploy** | One-click deployment for instant publishing |
| **Multi-round editing** | Iterative website revisions with version comparison |
| **One-click sharing** | Generate accessible links for easy sharing |
| **Template selection** | Multiple preset templates for quick-start site building |
| **Code export** | Download packaged HTML/CSS/JS files for self-hosting |

## How to use Kimi Websites？

### Method 1: visit the Kimi Websites page

<Frames
  src="./images/overview/kimi-websites-homepage.png"
  alt="Kimi websites homepage"
/>

1. **Open browser**: Use Chrome, Safari, Edge, Firefox, or any major browser
2. **Go to**: [kimi.com/websites](https://www.kimi.com/zh/websites) (supports Chinese and English)
3. **Log in**: With your Kimi account (phone number or email)
4. **Enter your task**:

| Approach | Description |
|----------|-------------|
| **Text input** | Type your request in natural language |
| **Image/site cloning** | Upload a design mockup or screenshot |
| **Template-based** | Select a preset template and modify content |

5. **Start building**: Choose a template or start from conversation

<Frames
  src="./images/overview/screenshot-27.png"
  alt="screenshot 27"
/>

### Method 2: mobile app

iOS, Android, and HarmonyOS all have the official Kimi app. In the input area, tap the **Taskbar** → switch to **Websites Agent mode**, which includes multimodal generation tools and Agent capabilities.

### Method 3: use K2.6 Agent mode

Switch to K2.6 Agent mode and enter a website-building task. Kimi will invoke its visual coding capabilities and code execution tools.

## How do Kimi Websites work?

### Step 1: create a website via conversation

Describe your needs in natural language. Three creation methods are supported:

| Method | Description |
|--------|------------|
| **Text description** | Enter website requirements directly; AI generates automatically |
| **Design mockup parsing** | Upload a design file; AI recognizes and recreates as a web page |
| **Quick template build** | Select a preset template and modify content |

**Example prompt**:

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "Build a website for West Highland Terrier dogs with a black-and-white color scheme. Include three sections:\nA studio-quality photo calendar with AI-generated image display\nA \"Curly Lab\" care and grooming encyclopedia\nA merchandise store selling Westie-print hoodies and limited-edition silver-foil posters. The checkout page should include a charity module — donate $1 per item sold to stray dog rescue.",
    },
  ]}
/>

### Step 2: building process

<Frames
  src="./images/overview/screenshot-26.png"
  alt="screenshot 26"
/>

Kimi website activates the **webapp-building SKILL** — a dedicated multi-round code-generation agent:
1. **Requirement analysis**: Analyzes website modules, visual style, and interaction logic
2. **Task planning**: Decomposes into design, development, and asset preparation sub-tasks
3. **Tech stack selection**: Chooses appropriate architecture (e.g., React + Tailwind CSS)
4. **Asset generation**: Generates images, icons, and other visual assets
5. **Code construction**: Writes page structure, styling, and interaction code
6. **Multi-round optimization**: Self-adjusts based on preview results until complete

### Step 3: preview & adjust
- **Live preview**: Generates an HTML demo URL for immediate browser viewing
- **Conversational editing**: Continue the conversation to request changes, e.g., *"Make the navbar dark"*

<Callout type="tip">
**Example**: *"The colors aren't great — I'd like to drop the black-and-white requirement and make it a normal-looking website."*
Kimi will reorganize the to-do list and continue building.
</Callout>

<Frames
  src="./images/overview/web-case2.png"
  alt="web case2"
/>

### Step 4: visual online edit
- **Multi-round optimization**: Fine-tune details through ongoing conversation
- **Editing modes**:
  - **Annotation mode**: Click on areas to add natural-language annotations
  - **Selection mode**: Select any element and add annotations
  - Use rectangles, arrows, brushes, and color switching to mark up revision suggestions
- Send all revision suggestions to Kimi at once
### Step 5: deploy & publish
| Deployment Method | Description |
|-------------------|------------|
| **Auto-deploy** | One-click deployment with generated online link |
| **Download & self-host** | Download packaged code files and deploy to your own server |
| **Custom domain** | Bind the generated website to your own domain |

After generation, you can:
- Click different deployment versions to download version files
- Click the share button to get a publicly deployed link (or set to private)
- Click the edit button to continue revising
- Download the complete HTML/CSS/JS code for direct deployment or further refinement

<Frames
  src="./images/overview/web-case1.png"
  alt="web case1"
/>

## Target audience
| Audience | Use Case |
|----------|----------|
| **Developers** | Design product prototypes and frontend demos, drastically reducing build-from-scratch time |
| **Entrepreneurs** | Quickly build landing pages, product showcases, and company websites with limited resources |
| **Product Managers** | Rapidly turn PRDs or design mockups into demonstrable interactive prototypes |
| **Non-technical users** | No coding required — describe your idea or upload a reference image to go from concept to working web page |

## Reference scenarios
| Scenario | Example Prompt |
|----------|---------------|
| **Landing page from scratch** | Build a SaaS marketing landing page with a tech aesthetic — include hero section, feature overview, pricing, and CTA |
| **Video-to-site reproduction** | [Upload screen recording] Reproduce the website shown in this video, maintaining the original interaction effects |
| **Screenshot reproduction** | [Upload design mockup] Turn this design into runnable web page code |
| **Personal portfolio** | Build a photographer's portfolio site — minimalist black-and-white style with image masonry layout |
| **Data visualization page** | Create a visualization page showing 2025 AI company funding data with charts and filters |
| **Brand website** | Build a coffee brand website in muted earth tones — include home, products, and store locator pages |
| **Utility / Calculator** | Build a BMI calculator web page — clean interface, unit toggle support, with health level indicators |
