---
title: "Kimi Agent overview"
slug: "agent-overview"
order: 1
extract_headings: false
preview: true
preview_content: "Learn about Kimi Agent's autonomous task execution, 20+ tools, and supported use cases."
---

<SeoMeta
  title="Kimi Agent Overview - Kimi Help Center"
  description="Discover Kimi Agent's capabilities, evolution, and use cases."
/>

# Kimi Agent overview

Kimi Agent is an autonomous AI assistant that handles complex tasks end-to-end. Powered by Kimi K3, it uses 20+ tools to build websites, generate documents, analyze data, and more.

## Product evolution
- **September 5, 2025**: Kimi K2 released — 32B active / 1T total parameters
- **September 26, 2025**: "OK Computer" Agent mode launched
- **January 27, 2026**: Kimi K2.5 released — improved Office skills and Agent capabilities
- **February 2026**: Kimi Claw public beta launched
- **April 20, 2026**: Kimi K2.6 released and open-sourced — leading coding, long-horizon execution, and Agent Swarm
- **July 16, 2026**: Kimi K3 released — the world's first open 3T-class model (2.8T parameters, native vision, 1M-token context) and Kimi's most powerful model, powering chat, Agent, and Agent Swarm; available via the Kimi App, kimi.com, Kimi Work, Kimi Code, and the Kimi API, with full weights on July 27, 2026

## Core capabilities
| Feature | Description |
|---------|-------------|
| **Websites** | Generate and deploy responsive web apps |
| **Docs** | Word, PDF, Markdown editing and generation |
| **Sheets** | Excel/CSV data analysis and visualization |
| **Slides** | Automated PPT generation |
| **Deep Research** | 10,000+ word research reports |
| **Agent Swarm** | Up to 300 sub-agents working in parallel |
| **Kimi Claw** | Cloud automation with 5,000+ skills |

<Frames
  src="./images/overview/agent-workflow.png"
  alt="agent workflow"
/>

## How it works?
1. **Task Planning**: Decomposes your request into sub-tasks
2. **Tool Invocation**: Uses 20+ tools as needed
3. **Autonomous Execution**: Completes research, design, development
4. **Error Handling**: Self-corrects without user intervention
5. **Deliverables**: Office files, web apps, or reports

## Getting started
- **Web**: [kimi.com/agent](https://www.kimi.com/agent)
- **Mobile**: open the Kimi app and select the K3 or K3 Swarm model in the model switch button
Describe your task clearly, watch execution progress, then download or share results.

## Use cases
- Website development (zero coding required)
- Content generation with multimedia
- Document comparison and translation
- Data analysis (up to 1,000-row Excel)
- Slide generation
- Document conversion

<ColumnsContent
  columns={[
    {
      title: "Features & Limits",
      description: "Capabilities and quotas",
      pageUrl: "/agent/agent-features-and-limits",
      type: "document",
    },
    {
      title: "credits & Billing",
      description: "Pricing and membership details",
      pageUrl: "/agent/quota-and-billing",
      type: "data",
    },
    {
      title: "Agent Swarm",
      description: "Multi-agent collaboration",
      pageUrl: "/agent/agent-swarm",
      type: "comment",
    },
    {
      title: "Kimi Claw",
      description: "Cloud automation agent",
      pageUrl: "/kimi-claw/overview",
      type: "kimiclaw",
    },
  ]}
/>
