---
title: "Uninstall the Kimi plugin"
slug: "uninstall-plugin"
order: 10
extract_headings: false
preview: false
---

<SeoMeta
  title="Uninstall the Kimi plugin - Kimi Help Center"
  description="This only applies to self-hosted OpenClaw devices that you linked to Kimi. Make sure you're running this on your own machine."
  pageUrl="https://www.kimi.com/help/kimi-claw/uninstall-plugin"
/>

# Uninstall the Kimi plugin

<Callout type="warning">
**This only applies to self-hosted OpenClaw devices** that you linked to Kimi. Make sure you're running this on your own machine.
</Callout>

## Uninstall command

Run the following on the device where OpenClaw is installed:

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "bash \u003c(curl -fsSL https://cdn.kimi.com/kimi-claw/uninstall.sh)",
    },
  ]}
/>

## Critical warning

<Callout type="warning">
**Never run this command on a one-click deployed Kimi Claw instance.**
Executing the uninstall script on a cloud-deployed Kimi Claw will **permanently sever the connection** with no way to recover. This command is strictly for removing the Kimi plugin from self-hosted OpenClaw devices.
</Callout>
