# 定制化

## MCP 服务器

MCP（Model Context Protocol）服务器可为 Kimi 扩展外部工具与服务。通过操作菜单（齿轮图标）→ **MCP Servers** 进行管理。

### 传输类型

支持两种传输类型：

- **stdio**：本地命令行工具，需指定命令、参数和环境变量
- **http**：远程服务，需指定 URL，可选 OAuth

### 推荐服务器

![Kimi Code MCP Servers](/images/zh/vscode/kimi-code-mcp.png)

提供推荐服务器的一键安装：

| 服务器 | 用途 |
| --- | --- |
| Playwright | 浏览器自动化 |
| Context7 | 实时文档 |
| GitHub | API 访问 |

部分服务器需 OAuth 认证，点击授权按钮打开流程，或重置凭证。保存前可测试连接以验证服务器可用性。
