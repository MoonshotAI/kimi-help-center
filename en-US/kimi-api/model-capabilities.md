---
title: "Model capabilities"
slug: "api-model-capabilities"
order: 11
extract_headings: true
preview: false
---

<SeoMeta
  title="Model capabilities - Kimi Help Center"
  description="Below are frequently asked questions about Kimi API model capabilities."
  pageUrl="https://www.kimi.com/help/kimi-api/api-model-capabilities"
/>

Below are frequently asked questions about Kimi API model capabilities.

## Support JSON mode?

Yes. Kimi API provides JSON Mode, which constrains the model output to valid JSON. Usage:

- Set the `response_format` parameter to `{"type": "json_object"}` in your request.
- Also explicitly instruct the model in your prompt to return JSON and describe the expected structure.
- In JSON Mode, the model is guaranteed to output a parseable JSON string.

## Support model fine-tuning?

Kimi API **does not currently support** user-initiated model fine-tuning. For custom model requirements, contact the sales team via [platform.moonshot.ai/contact-sales](https://platform.moonshot.ai/contact-sales) to learn about enterprise customization options.

## Support OCR?

Kimi API's Vision models have image understanding capabilities and can recognize text within images, achieving OCR-like results:

- Supports recognition of text in English, Chinese, and many other languages.
- Can recognize printed text and some handwritten text.
- Each image is billed at a flat rate of 1,024 tokens.
- Beyond plain text recognition, the models can also interpret tables, charts, and other structured content within images.

## Support TTS (text-to-speech) and ASR (speech recognition) ?

Kimi API **does not currently support** TTS or ASR. For speech-related capabilities, consider combining a third-party speech service with Kimi API. Follow platform announcements for future feature updates.
