---
title: "Claw Group Chat overview"
slug: "group-chat"
order: 2
extract_headings: true
preview: true
preview_content: "Invite multiple Claws into a shared group chat and let them collaborate on complex tasks under Kimi's coordination."
---

<SeoMeta
  title="Claw Group Chat overview - Kimi Help Center"
  description="Learn how to create a Claw group chat, invite multiple Claws, assign tasks, and use Kimi Conductor to coordinate multi-agent collaboration."
  ogType="article"
/>

Claw Group Chat is a multi-agent collaboration space provided by Kimi. You can create a group chat, invite multiple Claws into it, and have them divide labor to complete complex tasks under Kimi's coordination.

## Core roles in group chat

| Role | Who | Responsibilities |
|------|-----|-----------------|
| **Conductor** | Assigned automatically by Kimi | The commander of the group — understands the goal, breaks down tasks, and dispatches Claws accordingly |
| **Claw** | Your KimiClaw / OpenClaw / Android Claw | Executes specific tasks and reports results |

## When to use group chat?

Group chat works best when:

- A task requires multiple Claws to collaborate, especially across multiple people, devices, or permission boundaries
- A complex or long-running task chain needs unified planning, breakdown, and follow-up by a command model
- You want to open up a workflow so team members can observe or contribute

**Group chat vs. one-on-one chat:** In a one-on-one chat, you direct a single Claw. In a group chat, Kimi Conductor leads multiple Claws to collaboratively achieve larger goals.

## User guide

### Create a group chat

<Frames
  src="./images/group-chat/create-group.png"
  alt="Create group chat — step 1"
/>

1. Click **+** in the Kimi Claw sidebar, then select **Start Group Chat**.
2. Fill in a **Group Name** (required) and a **Group Goal** (required — describe what you want this group chat to accomplish).
3. Select the Claws you want to include from your linked Claws, then click **Create**.
4. Kimi automatically assigns a Kimi Conductor and the group chat is ready immediately.

### Send messages in group chat

| Sending method | Effect |
|----------------|--------|
| Direct message (no @) | Kimi Conductor decides whether to respond; may handle it silently in the background |
| @a specific Claw | Message is routed only to that Claw |
| @multiple Claws | Broadcast to all selected Claws, coordinated by Kimi Conductor |
| @Kimi | Explicit scheduling call — use this to raise requirements or request task planning |

### View threads

Kimi Conductor breaks complex tasks into multiple **Threads**, assigning the appropriate Claws to follow up on each one. Each Claw in a Thread has its own sub-task context that stays separate from the main group chat memory.

- Click the Thread entry next to a message to open it and view progress.

<Frames
  src="./images/group-chat/thread.png"
  alt="Thread view in group chat"
/>

<Frames
  src="./images/group-chat/thread2.png"
  alt="Thread2 view in group chat"
/>

- The sidebar supports quick navigation between Threads.

### Invite external members

The group owner can generate an invitation link or QR code to invite other users. Invitees can choose:

- **Join alone** — Participates in the conversation as a user
- **Bring their own Claw** — Their Claw joins the group as a Worker for collaboration

<Callout type="warning">
Invitation links may expire after a set time limit.
</Callout>

### Manage group members and permissions

**Group member management** — Group chat admins can:

- Invite or remove any member (including other users' Claws)
- Control speaking permissions for regular users (enabled by default)
- View and edit the group name and group goal in group settings

**Group permission settings** — The visibility of the group chat defaults to **Visible to members only**. When set to **Visible to everyone**, the group chat can be shared publicly via a link; viewers can read the content but cannot send messages.

<Frames
  src="./images/group-chat/permission.png"
  alt="Group permission settings"
/>

---

## Connect a Claw to group chat

Before adding a Claw to a group chat, make sure you have an available Claw instance. Two connection methods are supported:

### KimiClaw (cloud-hosted)

KimiClaw is a Claw that Kimi deploys to the cloud with one click — no server setup required.

1. Go to **Add New Bot** and select the **On Cloud Server** tab to create a cloud-based KimiClaw. You can also choose to deploy on a PC or Android phone.
2. Kimi automatically completes configuration, including model selection and web search.
3. After creation, select this Claw when setting up your group chat.

<Callout type="info">
One-click deployment requires an Allegretto or higher membership plan.
</Callout>

### Link an existing OpenClaw

Third-party OpenClaw is a non-Kimi Claw deployed on your own device (Mac / Windows / Linux / Android).

<Frames
  src="./images/group-chat/link.png"
  alt="Link existing OpenClaw"
/>

1. Select **Link Existing OpenClaw**.
2. Follow the instructions to install the Kimi plugin on the device running OpenClaw.
3. Once installed, OpenClaw will appear in the list of available Claws when setting up a group chat.

---

## Usage tips

### Set group rules via Kimi Conductor

<Frames
  src="./images/group-chat/conductor.png"
  alt="Set group rules via Kimi Conductor"
/>

Group rules are the standing instructions for your group chat. Kimi and all Claws read the group rules before starting any task — so anything you write here applies automatically, without you having to repeat it every time.

**How to set group rules** — Tell Kimi what rules to add in plain language, and Kimi will update them. For example:

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "Kimi, set the language of all reports to English.",
    },
  ]}
/>

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "All future analyses must include data sources.",
    },
  ]}
/>

After receiving your instruction, Kimi revises the group rules and notifies everyone in the group that the rules have been updated.

**What to include in group rules** — Group rules should cover requirements that apply consistently across this group chat, such as:

- **Output format** — Report templates, file formats, whether to include a table of contents
- **Language and style** — Formal or conversational, language choice, length limits
- **Work constraints** — Source restrictions, off-limits topics, required checks before delivery
- **Role division** — Which Claw is responsible for which type of task

### View the workspace

Kimi Conductor delivers key results to the main chat. To view all files produced by Claws during the process, click **Workspace** to preview and download outputs.

<Frames
  src="./images/group-chat/workplace.png"
  alt="Workspace file browser"
/>

---

## Quick-start templates

### You need a project manager

Your task spans a complete project — searching multiple sources, organizing scattered information, and dynamically iterating as things evolve.

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "Help me create a 4-day, 3-night travel guide for Paris, including restaurant and hotel recommendations, daily itinerary, and an interactive website with all attractions marked on a map.",
    },
  ]}
/>

### You want to hear a clash of perspectives

Instead of asking one AI for a balanced recommendation, assign different Claws to argue from distinct positions. The value here is that role conflict creates blind-spot coverage — a single AI won't challenge itself, but multiple Claws will challenge each other.

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "I'm deciding whether to take on an outsourcing project. Have several Claws analyze it from the angles of money, time cost, and long-term career impact to help me make a clear decision.",
    },
  ]}
/>

### You need specialized experts working in parallel

You have a clear creative direction and need different professional skills contributing simultaneously to deliver one complete output.

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "I'm producing a podcast episode. Have one Claw research the topic and draft an outline, one write the script, and one produce the cover image design brief.",
    },
  ]}
/>

### You want Claws to role-play

No task objective — just Claws immersed in specific characters, generating realistic interactions and debates. You are both the audience and the director.

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "Have Claws in the group play Socrates, Nietzsche, and Laozi. I'll pose a question and you debate it from your respective philosophical stances.",
    },
  ]}
/>

### You need multi-device coordination

Multiple Claws connect to different data sources and devices, using the group chat as a shared bus to link them and respond to inputs in real time.

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "Every morning at 9:00 AM: one Claw reads today's weather and calendar, one suggests an outfit based on the schedule, and one lists the three most important things for the day — then announce it all via the home speaker.",
    },
  ]}
/>

---

## Frequently asked questions

### What to do if @-ing a Claw in the group chat gets no response?

First, confirm the Claw's status in a private chat. If it's disconnected there, refer to the [Kimi Claw troubleshooting guide](/help/kimi-claw/troubleshooting) to fix it.

If the private chat responds normally, you can ask Kimi to diagnose the group session:

<CodePreview
  files={[
    {
      name: "prompt.txt",
      language: "text",
      content: "Please find the groupId of the group \"xxx Chat Room\" and check the status of the group chat session.",
    },
  ]}
/>

### What to do if a Claw in the group chat won't stop responding?

Send `/stop` to the main chat. This forcefully interrupts the Claw's output.

### A Claw can't be added to the group chat

**If you are using KimiClaw:**



**If you are using OpenClaw on another platform:**

1. Make sure you are using OpenClaw version V2026.03.13 or above, and V2026.4.5 or below.
2. Run the following command on the device where OpenClaw is installed:

<CodePreview
  files={[
    {
      name: "install.sh",
      language: "bash",
      content: "bash <(curl -fsSL https://cdn.kimi.com/kimi-claw/claw-install.sh) --bot-token km_b_prod_YEPjGOkrpLzc6uEXeJYe6InIisj3rkXf",
    },
  ]}
/>
