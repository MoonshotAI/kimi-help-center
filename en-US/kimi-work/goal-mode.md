---
title: "Goal Mode"
slug: "goal-mode"
order: 2
extract_headings: false
preview: false
---

<SeoMeta
  title="Kimi Work Goal Mode - Kimi Help Center"
  description="Learn about Goal mode in Kimi Work: the Loop mechanism that lets an Agent work continuously toward a single goal for up to 24 hours, plus how to enable it and which tasks it suits."
/>

# Goal Mode

Goal mode lets an Agent work continuously toward a single goal (for up to 24 hours), acting like a project assistant that keeps pushing the task forward.

## How It Works: The Loop Mechanism

- **Goal-oriented autonomous loop**: You only need to set a clear endpoint, and Kimi automatically enters a continuous loop, advancing on its own until the goal is reached — no manual intervention required.
- **Self-evolving strategy**: During execution, the Agent continuously compares the current state against the goal, converging and evolving its approach.
- **No goal drift, no state buildup**: The Agent first extracts a "what counts as success" standard from the goal and provides stable tracking. The model makes every decision against the same endpoint, acting only on the real current state. The anchor stays fixed, so it doesn't go off track.
- **Human in the loop**: The AI's process is fully transparent, and you can interrupt the loop at any time. If you notice it drifting or getting stuck, simply adjust the current state or add instructions to steer it and let the Agent continue.

## How to Enable

1. Open the latest Kimi desktop client and switch to "Work" mode in the left sidebar;
2. Click the "+" at the bottom-left of the input box and select "Goal";
3. Enter a goal that takes a long time to complete, and Kimi starts pushing the task forward continuously.

## Suitable Tasks

Goal mode works best for tasks that meet all four conditions — a clear goal, an uncertain path, a need for multiple attempts, and verifiable results — such as migrating code, organizing massive amounts of material, reproducing paper results, or building a personal knowledge base.

<Callout type="tip">
Example: Kimi Work can spend a few hours automatically organizing 80 papers, 2,000 pages of PDFs, and 1 million words into an Obsidian knowledge base.
</Callout>
