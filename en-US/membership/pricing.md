---
title: "Pricing details"
slug: "membership-pricing"
order: 4
extract_headings: true
preview: false
---

<SeoMeta
  title="Pricing details - Kimi Help Center"
  description="Kimi offers four membership tiers, each available as a monthly or annual subscription. Annual billing saves you up to $480/year."
/>

# Pricing details

Kimi offers four membership tiers, each available as a monthly or annual subscription. Annual billing saves you up to **$480/year**.

## Plans at a glance

| Feature | Moderato ($19/mo) | Allegretto ($39/mo) | Allegro ($99/mo) | Vivace ($199/mo) |
|---------|-------------------|---------------------|-------------------|-------------------|
| Agent credits* | 60 | 150 | 360 | 720 |
| Agent concurrent tasks | 2 | 2 | 4 | 4 |
| Agent speed priority | 4× | 4× | 4× | 4× |
| Agent Swarm (beta) | 25 uses | 50 uses | 120 uses | 240 uses |
| Agent Swarm concurrent subtasks | 2 | 4 | 4 | 8 |
| Kimi Code credits | 1× | 5× | 15× | 30× |
| Kimi Claw | — | ✅ | ✅ | ✅ |
| Kimi Claw Android | — | ✅ | ✅ | ✅ |
| Professional database | 2,000 calls | 5,000 calls | 12,000 calls | 24,000 calls |

\* Approximate values based on typical task token consumption. Monthly credits are converted to the equivalent number of tasks for the same feature; for reference only.

## Monthly vs. annual pricing

| Plan | Monthly | Annual (per month) | Annual Total | You Save |
| --- | --- | --- | --- | --- |
| Moderato | $19/mo | $15/mo | $180/yr | $48/yr |
| Allegretto | $39/mo | $31/mo | $372/yr | $96/yr |
| Allegro | $99/mo | $79/mo | $948/yr | $240/yr |
| Vivace | $199/mo | $159/mo | $1,908/yr | $480/yr |

## Credit allocation

All Kimi membership features share a single credit pool, metered by token usage. Kimi Code also has its own 5-hour / weekly rate limit that applies only to Kimi Code and does not affect other features. In Chat, K2.6 is free and does not consume credits. Higher tiers include a proportionally larger credit pool, supporting more frequent and complex workflows. See [Credit Update & Usage Rules](/membership/update-rules) for details.

## Credit FAQ

### What is the “Claw-云主机” 0.6% charge deducted every day at 4 PM?

This is the sandbox running cost of your Kimi Claw cloud host. Kimi Claw is an OpenClaw deployment in the cloud: every time you invoke Claw, the system starts an isolated cloud sandbox to execute code, operate the browser, or call tools. Sandboxes are not “free standby”—they are billed continuously by runtime and resource consumption. Even when you are not actively running tasks, a deployed cloud host retains its runtime environment and data, so about 0.6% of your membership credits is deducted each day, settled at 4:00 PM.

If you do not plan to use Kimi Claw for a while, save important files such as memory, soul, and workspace files locally first, then delete the cloud host; no further charges apply after deletion, and you can redeploy anytime.

### What is the “Agent Website - Cloud Service” 0.08% charge?

This is the cloud service fee for a website you published with Agent. A published website continuously occupies cloud resources to stay online and accessible, so about 0.08% of your membership credits is deducted. If you no longer need the website online, click “Unpublish” to stop the charges.
