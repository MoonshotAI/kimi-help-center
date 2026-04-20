---
title: "数据处理与安全"
slug: "api-data-security"
order: 13
extract_headings: true
preview: true
preview_content: "Kimi API 数据处理声明、安全机制与文件删除接口。"
---
<SeoMeta
  title="Kimi API 数据安全与隐私保护 - Kimi 帮助中心"
  description="了解 Kimi API 的数据安全措施、隐私保护策略和合规认证。你的数据不会被用于模型训练，全链路加密传输，保障企业数据安全。"
  pageUrl="https://www.kimi.com/help/kimi-api/api-data-security"
/>

# 数据处理与安全

Kimi API 高度重视用户数据安全和隐私保护，以下是相关常见问题。

## 用户数据会被用于模型训练吗？

**不会。** 通过 API 提交的用户数据（包括输入内容和模型输出）不会被用于训练或改进 Kimi 的模型。你的数据仅用于完成当次 API 请求，处理完成后不会被持久化存储用于训练目的。

## 私域数据安全如何保障？

Kimi API 采取多重措施保障你的私域数据安全：

- **传输加密**：所有 API 通信均使用 HTTPS/TLS 加密。
- **数据隔离**：不同用户的数据严格隔离，互不可见。
- **不用于训练**：API 数据不会被用于模型训练。
- **访问控制**：API Key 认证机制确保只有授权请求才能访问你的数据。
- **合规认证**：平台通过相关安全合规认证。

如有更高安全需求，可联系销售团队了解企业级安全方案。

## 内容安全审查机制

Kimi API 内置内容安全审查机制：

- 系统会自动检测和过滤违规内容（涉及违法、暴力、色情等）。
- 触发内容安全审查时，API 将返回相应的错误提示。
- 内容审查不会存储或泄露你的原始数据。
- 如遇误触发，可通过 request_id 联系客服反馈。

## 如何删除已上传的文件？

通过文件接口上传的文件可以随时删除：

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "DELETE https://api.moonshot.cn/v1/files/{file_id}",
    },
  ]}
/>

在请求头中携带 API Key，传入文件 ID 即可删除。删除后文件将无法再被引用，相关数据会从服务器中清除。

你也可以在控制台的文件管理页面手动查看和删除已上传的文件。
