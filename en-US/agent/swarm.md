---
title: "Agent Swarm"
slug: "agent-swarm"
order: 2
extract_headings: false
preview: false
---

<SeoMeta
  title="Agent Swarm - Kimi Help Center"
  description="Agent Swarm is a &quot;horizontal scaling&quot; architecture that coordinates up to 300 sub-agents working in parallel — no predefined roles or hand-crafted..."
/>

# Agent Swarm

<Callout type="info">
**Agent Swarm** is a "horizontal scaling" architecture that coordinates up to 300 sub-agents working in parallel — no predefined roles or hand-crafted workflows required. It completes tasks approximately **4.5× faster** than single-agent execution.
</Callout>

On January 27, 2026, Moonshot AI released Kimi K2.5, introducing Agent Swarm. On April 20, 2026, Moonshot AI released and open-sourced Kimi K2.6, bringing major upgrades to the Agent Swarm architecture:
- Up to **300 sub-agents** working simultaneously
- Over **4,000 tool calls** per task
- **4.5× faster** than single-agent sequential execution

Agent Swarm is currently powered by Kimi K3 (K3 Swarm), further improving large-scale parallel search and batch processing.

## The story behind

In 2025, the AI industry's dominant narrative focused on vertical scaling — bigger models, more parameters. But this hits a structural ceiling: the single sequential execution bottleneck.

Agent Swarm was born from a real scenario: when a team member tried to automate daily stock information collection and hit 100 lines of if-else code, she realized: "I'm hand-writing a multi-agent system." If models can use tools, why can't they self-architect?

Agent Swarm is a self-designed organizational structure — designed by AI, not humans. The main Agent (orchestrator) autonomously directs up to 300 sub-agents, executing up to 4,000 parallel workflow steps.

<Frames
  src="./images/swarm/swarm.png"
  alt="swarm"
/>

Agent Swarm uses the PARL (Parallel-Agent Reinforcement Learning) training method. Compared to single-agent approaches, it reduces critical steps by 3×–4.5× in large-scale search scenarios.

## How to use?

<Frames
  src="./images/swarm/screenshot-8.png"
  alt="screenshot 8"
/>

**Access Points:**
- **Web**: [kimi.com/agent-swarm](https://www.kimi.com/agent-swarm)
- **Mobile**: open the Kimi app and select the K3 Swarm model in the model switch button

<Callout type="info">
About the [Beta] tag: [Beta] indicates a trial marker for a product that is initially open to only a small number of users for small-scale validation and refinement; as the feature matures, the tag is gradually removed and the product is rolled out to everyone.
</Callout>

Agent Swarm is available to Moderato, Allegretto, Allegro, and Vivace members. Tasks consume significantly more credits than standard Agent tasks.

**Steps:**
1. Describe your task and send it (e.g., "Collect 200+ Paul Graham articles")
2. Watch real-time progress: task list creation, sub-agent spawning, parallel execution
3. Receive deliverables: code projects, file folders, data analysis, Office documents
4. Preview, download, or share results
5. In subsequent turns, Kimi automatically schedules between chat and Agent based on the task — no manual switching required

## Use cases

### Discovery at scale

**Case 1: Top 3 Creators Across 100 YouTube Niches**

Agent Swarm created 300 sub-agents for parallel search, generating structured tables with channel names, subscriber counts, and descriptions.

<Frames
  src="./images/swarm/youtube.png"
  alt="YouTube"
/>

<Chat title="View result" src="https://www.kimi.com/share/19c40eea-b272-8ef2-8000-0000af5e0baa?hide_sidebar=1&disable_auto_preview=1" />

**Case 2: Collecting 200+ Paul Graham Articles**

Agent Swarm deployed sub-agents to search, download, categorize, and summarize 200+ articles into thematic folders.

<Chat title="View result" src="https://www.kimi.com/chat/19dbe721-9af2-86eb-8000-09b25205727e?chat_enter_method=home" />

### Output at scale

**Case: 100-Page Literature Review from 40 PDFs**

Agent Swarm deployed multiple writing-focused sub-agents, each responsible for a chapter. Final output: a 100-page academic document with citations, methodology charts, and citation network analysis.

<Frames
  src="./images/swarm/literature-review.png"
  alt="literature review"
/>

### Perspective at scale

**Case: Product Launch Strategy Expert Review**
Agent Swarm deployed expert sub-agents with different perspectives (Product Manager, Investor, Customer Success) to review a launch strategy.

<Frames
  src="./images/swarm/expert-review.png"
  alt="expert review"
/>

<Chat title="View result" src="https://www.kimi.com/share/19c40bc9-31a2-8533-8000-0000bad59b7a?hide_sidebar=1&disable_auto_preview=1" />

**Case: *The Three-Body Problem* Rewritten in 20 Literary Styles**
20 "writer" sub-agents composed independently in distinct styles — from Virginia Woolf to Borges to Kafka.

<Chat title="View result" src="https://www.kimi.com/share/19c409c8-8692-821a-8000-0000070ad369?hide_sidebar=1&disable_auto_preview=1" />

## Technical deep dive

**Core Architecture: Commander + Specialists**

- **Orchestrator** = Coach/Commander: Sees the big picture, sets strategy
- **Sub-agents** = Players: Each focused on a specific role

**Key Design: Freeze the Players, Train Only the Coach**

All sub-agents retain existing capabilities; only the orchestrator improves through reinforcement learning. This provides clear accountability and training stability.

**Preventing "Laziness":**
- **Serial collapse**: Orchestrator handing everything to one sub-agent
- **Fake parallelism**: Meaningless sub-tasks to game metrics

**Solution: Three-Dimensional Reward Mechanism**
1. Quality of final result
2. True parallelism achieved
3. Sub-task completion rate

**Critical Steps Metric**

Agent Swarm calculates the slowest sub-agent's time at each stage. This forces genuine process optimization rather than blind task splitting.

**Context Sharding**

Each sub-agent focuses on its own "notebook," recording relevant details independently. Only key conclusions are reported to the orchestrator — preserving reasoning without overwhelming memory.

**Real-World Results**

On the BrowseComp benchmark:
- Accuracy: 15.9% (single agent) → 33.3%
- Critical steps reduced by ~40%

## Application scenarios

Agent Swarm is especially suited for:
1. **Large-scale information retrieval**: Massive internet data collection
2. **Batch downloads**: Large-scale file and resource collection
3. **Wide-scope reading**: Processing 100+ documents
4. **Long-form writing**: Content exceeding 100,000 words
5. **Complex programming**: Frontend development, code review, refactoring
6. **Office automation**: Professional documents, spreadsheets, presentations

**Further Reading:**
- [Kimi Agent Swarm: 100 Sub-Agents at Scale](https://www.kimi.com/blog/agent-swarm)
- [Kimi K2.5: Visual Agentic Intelligence​](https://www.kimi.com/blog/kimi-k2-5)
- [Kimi K2.6: Advancing Open-Source Coding](https://www.kimi.com/blog/kimi-k2-6)
- [Kimi K3](https://www.kimi.com/blog/kimi-k3)
