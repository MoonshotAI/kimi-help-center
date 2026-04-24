---
title: "Memory loss & context"
slug: "memory-loss"
order: 7
extract_headings: true
preview: false
---

<SeoMeta
  title="Memory loss \u0026 context - Kimi Help Center"
  description="OpenClaw automatically resets the conversation at 4:00 AM daily. This prevents overly long contexts from causing hallucinations or degraded response quality."
/>

## Why is yesterday's conversation gone?

OpenClaw automatically resets the conversation at **4:00 AM daily**. This prevents overly long contexts from causing hallucinations or degraded response quality.

If you need to adjust when the reset happens, you can modify the schedule in `config.yaml`.

**Best practice:** For anything important — preferences, project details, recurring instructions — explicitly tell Kimi Claw to save it: _"Remember this to Memory."_ Information stored in Memory persists across conversation resets.

## Kimi Claw lost its memory?

The daily 4 AM reset clears the active conversation context. If something wasn't saved to **Memory**, it's gone.

**How to fix it：**
- During a conversation, say _"Remember X to Memory"_ and Kimi Claw will write it to long-term storage.
- Review stored memories via **Workspace → AGENTS.md → #MEMORY**.

<Frames
  src="./images/memory-loss/claw-memory.png"
  alt="Claw Memory"
/>

- Use the `/memory` command at any time to view and manage saved memories.

## How long is memory kept after subscription ends?

Memory files live in your Workspace, and you can view or download them at any time.

- After your membership expires, the cloud instance is **retained for 7 days**.
- Renew within 7 days and all data — memory, configuration, skills — is fully restored.
- After 7 days the instance may be reclaimed and data permanently deleted.
- A memory export/backup feature is in development for easier migration.
