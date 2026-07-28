---
title: "Billing & finance"
slug: "api-billing-and-finance"
order: 10
extract_headings: true
preview: false
---

<SeoMeta
  title="Billing & finance - Kimi Help Center"
  description="Frequently asked questions about Kimi Open Platform billing, top-up, vouchers, invoices, and payment."
/>

# Billing & finance

Frequently asked questions about Kimi Open Platform billing, pricing, and payment.

## What is the pricing structure?

Kimi API is billed per token consumed — input tokens and output tokens are priced separately. Pricing varies by model, and web search incurs an additional fee of $0.004 per invocation.

<Callout type="tip">
For detailed pricing, see [platform.kimi.ai/docs/pricing/chat](https://platform.kimi.ai/docs/pricing/chat).
</Callout>

## How do I top up my account?

### Individual users

Go to the user top-up page and complete an online payment. Online top-ups support WeChat Pay and Alipay QR code payments. After the payment succeeds, your account tier will be adjusted based on your accumulated top-up amount.

### Business users

Please contact the Kimi sales team or follow the payment methods supported in your account. Supported options may include online payment or bank transfer, depending on your account region and billing setup. After the payment is received, your account tier will be adjusted based on your accumulated top-up amount.

## When will my top-up voucher arrive, and where can I check it?

First confirm whether your top-up qualifies for the campaign: participation count, eligible transactions, issuance timing, and validity are all governed by the [campaign rules page](https://platform.kimi.ai/docs/pricing/promotion) — not every top-up earns a voucher.

Once issued, you can check `voucher_balance` with the [balance API](https://platform.kimi.ai/docs/api/balance). If the voucher has not arrived after the issuance time stated on the campaign page, contact [api-service@moonshot.ai](mailto:api-service@moonshot.ai) with your organization ID, top-up time, amount, and payment receipt.

## How do I request an invoice?

1. Log in to the [platform.kimi.ai](https://platform.kimi.ai) console.
2. Navigate to **Billing → Invoice Management**.
3. Select the top-up records for which you need an invoice.
4. Fill in the invoice details and submit.
5. An electronic invoice will be sent to your email.

Invoice notes:

- The platform supports issuing invoices based on either consumed amount or top-up amount.
- Supported invoice titles and requirements may vary by account type and billing setup. Please follow the options shown on the invoice request page.
- The issuing entity is Beijing Moonshot AI Technology Co., Ltd.; the service category is information technology services; the tax-inclusive rate is 6%.
