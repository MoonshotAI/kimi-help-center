---
title: "Plugins"
slug: "plugins"
order: 6
extract_headings: false
preview: true
preview_content: "Connect external tools to Kimi so it can use apps and services to complete tasks. Once a plugin is installed, Kimi can call third-party capabilities — such as financial data, office software, and design tools — to help you get work done."
---

<SeoMeta
  title="What Are Kimi Plugins? How to Install and Use Them - Kimi Help Center"
  description="Learn about Kimi plugins: connect external services such as financial data, office software, and design tools to Kimi, and call them directly while completing tasks. Covers where plugins work, installing and authorizing, invoking them, the plugin categories, and credit usage."
/>

# Plugins

Plugins connect external tools to Kimi so it can use apps and services to complete tasks. Once you install a plugin, Kimi can directly call the corresponding third-party capability while completing a task — for example, querying financial data, operating office software, or using design tools. You can explicitly ask to use a specific plugin, and Kimi will also call one automatically when appropriate.

## Where you can use plugins

You can use plugins when you switch the model to **K3** or **K3 Swarm**, and in the **Deep Research, Websites, and PPT** scenarios.

You can also use plugins in the **Kimi Work desktop app**; for the built-in plugin list on desktop, see the [Kimi Work Plugin Center](/kimi-work/plugin-center).

<Callout type="info">
Plugins are not yet supported in Kimi Claw or Kimi Plus conversations.
</Callout>

## Installing plugins

- **Entry points**: on the web, the **Plugins** tab in the sidebar, the **+** in the input box, or type "/"; on mobile, the **+** in the input box or "/".
- Search or browse in the plugin marketplace, open a plugin's details, and click install.
- Some plugins require **OAuth authorization** (you are taken to the third-party sign-in; once authorized, you can use it); some plugins are **pre-installed** and need no manual installation.
- **Enterprise-only plugins**: non-enterprise users can see them, but the "Install" button is greyed out.
- You can't install or use plugins while signed out.

## Using plugins

- After installing, type "/" in the input box or click **+** → Plugins, then select the plugin to invoke it; you can **invoke multiple plugins at once**.
- You can also just describe what you need (for example, "look up this company on Tianyancha"), and Kimi will pick the right plugin automatically.
- When Kimi calls a plugin's tools, it shows "Using the xx plugin" in its reply.

## Plugin categories and list

The plugin marketplace is organized into the categories below. The plugins you actually see vary by **region (domestic / overseas)** and **surface**, and some plugins appear in more than one category.

- **Finance**: Financial Investment Analysis, Investment Banking & Private Equity, Corporate Finance & Accounting, Wind Financial Data, S&P Global Market Intelligence, Hundsun Gildata, Tonghuashun iFinD, SEC, Global Financial Database, World Bank Open Data, IMF (International Monetary Fund) Database, Stripe, Tianyancha
- **Productivity**: Notion, Baidu Netdisk
- **Development**: GitHub, Supabase, Neon, Cloudflare
- **Creative**: Inspiration Pool, Image Generation, Video Generation, Audio Generation, Canva
- **General**: Vivify

## Credits

Some plugins call tools or services to complete a task and **consume your membership credits based on actual usage**; plugins with no call cost don't incur extra charges.

## Data and permissions

- When you select or explicitly ask to use a plugin, Kimi prioritizes the tools that plugin provides and generates its answer based on the results those tools return; after connecting a plugin, Kimi accesses relevant content within the scope you authorize.
- If a plugin is provided by a third party, its data-processing rules are set independently by that company, and the data is subject to its terms of service and privacy policy — we recommend reviewing them before authorizing.
- You can **uninstall a plugin or revoke authorization at any time**. After uninstalling, the related OAuth authorization is revoked; to use the plugin again, you'll need to reinstall and re-authorize.

## FAQ

### Do plugins consume my membership credits?
Some do. When Kimi calls a plugin's tools or services to complete a task, credits are consumed based on actual usage; plugins with no call cost don't incur extra charges.

### Can I use multiple plugins at once?
Yes. You can invoke multiple plugins at once via "/" or **+**.

### Why can't I see a certain plugin?
The available plugins vary by region (domestic / overseas) and surface; in addition, some plugins are available only to enterprise users.
