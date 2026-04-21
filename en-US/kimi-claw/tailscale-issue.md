---
title: "Tailscale disconnection"
slug: "tailscale-issue"
order: 11
extract_headings: false
preview: false
---

<SeoMeta
  title="Tailscale disconnection - Kimi Help Center"
  description="If Kimi Claw loses connectivity after you set up Tailscale, the cause is almost always a DNS override — Tailscale replaces the system's DNS settings, which b..."
/>

If Kimi Claw loses connectivity after you set up Tailscale, the cause is almost always a DNS override — Tailscale replaces the system's DNS settings, which breaks Kimi Claw's ability to resolve hostnames.

## How to fix？

1. Open the [Tailscale DNS settings page](https://login.tailscale.com/admin/dns).
2. Under **Nameservers → Global nameservers**, click **Add nameserver**.
3. Add these public DNS servers:
   - **Google Public DNS** — `8.8.8.8` / `8.8.4.4`
   - **Cloudflare Public DNS** — `1.1.1.1` / `1.0.0.1`
4. Enable the **Override DNS Servers** toggle in the top-right corner.
5. Wait about **30 seconds** for the connection to restore.

## How to prevent？

If you're about to set up Tailscale, configure the DNS settings above **before** enabling Tailscale. This avoids any connectivity interruption.
