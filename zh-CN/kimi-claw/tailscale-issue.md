---
title: "Tailscale 断开连接怎么办？"
slug: "tailscale-issue"
order: 19
extract_headings: false
preview: true
preview_content: "Tailscale 断开连接导致 Kimi Claw 异常的 DNS 修复方法。"
---

<SeoMeta
  title="Tailscale 导致 Kimi Claw 断连怎么修？ - Kimi 帮助中心"
  description="使用 Tailscale VPN 时 Kimi Claw 频繁断连？本文解析 Tailscale 覆盖 DNS 导致的连接问题，提供添加公共 DNS 和开启 Override 的修复步骤。"
/>
# Tailscale 断开连接

如果配置了 Tailscale 之后 Kimi Claw 断开了连接，这是由于系统的 DNS 配置被 Tailscale 覆盖导致的。

## 修复步骤

1. 打开 [Tailscale DNS 配置页面](https://login.tailscale.com/admin/dns)。
2. 在 **NameServer** 的 **Global nameservers** 处，点击 **Add nameserver**。
3. 添加以下公共 DNS 服务器：
   - **Google Public DNS**（8.8.8.8 / 8.8.4.4）
   - **Cloudflare Public DNS**（1.1.1.1 / 1.0.0.1）
4. 点击打开右上角的 **Override DNS Servers** 按钮。
5. 等待约 **30 秒**，连接即可恢复。

## 预防建议

如果你正准备配置 Tailscale，建议**先执行以上 DNS 配置步骤**，再启用 Tailscale，可以避免连接中断的问题。
