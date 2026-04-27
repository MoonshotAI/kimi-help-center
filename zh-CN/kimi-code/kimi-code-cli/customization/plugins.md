# 插件 (Beta)

> Beta 功能：插件系统目前处于 Beta 阶段，具体的实现细节和配置定义可能会在未来版本中调整。请谨慎在生产环境中使用，并关注后续更新。

插件系统让你可以为 Kimi Code CLI 添加自定义工具，扩展 AI 的能力。与 MCP 服务器不同，插件是轻量级的本地工具包，适合封装项目特定的脚本和实用程序。

## 插件是什么

一个插件就是一个包含 `plugin.json` 文件的目录。插件可以声明多个「工具」，每个工具是一个可执行命令（Python、TypeScript、Shell 脚本等），AI 可以调用这些工具来完成特定任务。

例如，你可以创建一个插件来：

- 封装内部 API 的调用脚本
- 提供项目特定的代码生成工具
- 集成专有服务或数据库查询

插件与 Agent Skills 的区别：

- **Skills**：通过 `SKILL.md` 提供知识性指导，AI 读取后遵循其中的规范
- **Plugins**：通过 `plugin.json` 声明可执行工具，AI 可以直接调用工具获取结果

## 安装插件

使用 `kimi plugin` 命令管理插件。

**从本地目录安装**

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "kimi plugin install /path/to/my-plugin",
    },
  ]}
/>

**从 ZIP 文件安装**

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "kimi plugin install my-plugin.zip",
    },
  ]}
/>

**从 Git 仓库安装**

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "# 安装根目录的插件\nkimi plugin install https://github.com/user/repo.git\n\n# 安装子目录中的插件（多插件仓库）\nkimi plugin install https://github.com/user/repo.git/plugins/my-plugin\n\n# 指定分支（使用浏览器 URL 格式）\nkimi plugin install https://github.com/user/repo/tree/develop/plugins/my-plugin",
    },
  ]}
/>

当 Git 仓库根目录没有 `plugin.json` 时，Kimi Code CLI 会检查根目录及其直接子目录，并列出可用的插件供你选择。

**列出已安装插件**

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "kimi plugin list",
    },
  ]}
/>

**查看插件详情**

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "kimi plugin info my-plugin",
    },
  ]}
/>

**移除插件**

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "kimi plugin remove my-plugin",
    },
  ]}
/>

## 创建插件

创建插件只需要三步：

1. 创建一个目录
2. 编写 `plugin.json` 文件
3. 实现工具脚本

**目录结构**

<CodePreview
  files={[
    {
      name: "example.txt",
      language: "text",
      content: "my-plugin/\n├── plugin.json       # 插件配置（必需）\n├── config.json       # 插件配置（可选，用于凭证注入）\n└── scripts/          # 工具脚本\n    ├── greet.py\n    └── calc.ts",
    },
  ]}
/>

**`plugin.json` 格式**

<CodePreview
  files={[
    {
      name: "example.json",
      language: "json",
      content: "{\n  \"name\": \"my-plugin\",\n  \"version\": \"1.0.0\",\n  \"description\": \"My custom plugin for project X\",\n  \"config_file\": \"config.json\",\n  \"inject\": {\n    \"api_key\": \"api_key\",\n    \"endpoint\": \"base_url\"\n  },\n  \"tools\": [\n    {\n      \"name\": \"greet\",\n      \"description\": \"Generate a greeting message\",\n      \"command\": [\"python3\", \"scripts/greet.py\"],\n      \"parameters\": {\n        \"type\": \"object\",\n        \"properties\": {\n          \"name\": {\n            \"type\": \"string\",\n            \"description\": \"Name to greet\"\n          }\n        },\n        \"required\": [\"name\"]\n      }\n    }\n  ]\n}",
    },
  ]}
/>

**字段说明**

| 字段 | 说明 | 是否必填 |
|------|------|----------|
| `name` | 插件名称，只能使用小写字母、数字和连字符 | 是 |
| `version` | 插件版本，语义化版本格式 | 是 |
| `description` | 插件描述 | 否 |
| `config_file` | 配置文件路径，用于凭证注入 | 否 |
| `inject` | 凭证注入映射，键为目标路径，值为源变量名 | 否 |
| `tools` | 工具列表 | 否 |

**工具字段说明**

| 字段 | 说明 | 是否必填 |
|------|------|----------|
| `name` | 工具名称 | 是 |
| `description` | 工具描述 | 是 |
| `command` | 执行命令，字符串数组 | 是 |
| `parameters` | JSON Schema 格式的参数定义 | 否 |

## 凭证注入

如果你的插件需要调用 LLM API，可以通过 `inject` 配置自动获取 Kimi Code CLI 的凭证配置。

**`inject` 配置示例**

<CodePreview
  files={[
    {
      name: "example.json",
      language: "json",
      content: "{\n  \"config_file\": \"config.json\",\n  \"inject\": {\n    \"llm.api_key\": \"api_key\",\n    \"llm.endpoint\": \"base_url\"\n  }\n}",
    },
  ]}
/>

**支持的注入变量**

| 变量名 | 说明 |
|--------|------|
| `api_key` | LLM 提供商的 API 密钥，支持 OAuth token 和静态 API key |
| `base_url` | LLM API 的基础 URL |

**`config.json` 模板**

<CodePreview
  files={[
    {
      name: "example.json",
      language: "json",
      content: "{\n  \"llm\": {\n    \"api_key\": \"\",\n    \"endpoint\": \"\"\n  }\n}",
    },
  ]}
/>

安装时，Kimi Code CLI 会将当前配置的 API 密钥和 base URL 注入到指定的配置文件中。如果配置了 OAuth，会自动获取并注入有效的 token。之后在应用启动时，Kimi Code CLI 也会尝试将最新的凭证（如刷新后的 OAuth token）写入已安装插件的配置文件中。

> 一般情况下，不需要为了更新凭证而重新安装插件：切换 LLM 提供商或重新授权后，重启 Kimi Code CLI 即可自动刷新配置文件中的凭证，插件工具在实际运行时也会通过环境变量获得当前有效的凭证。只有在修改了插件本身的配置结构（例如 `config_file` 或 `inject` 映射）时，才需要重新安装插件。

> 关于 inject 键名：`inject` 中的键名（如 `llm.api_key`）也会被用作环境变量名传递给插件工具子进程。由于这些名称包含点号，在某些运行环境中访问可能不便（例如 POSIX shell 中 `$llm.api_key` 是无效的）。你可以通过字典/映射方式访问：
> - **Node.js**: `process.env["llm.api_key"]`
> - **Python**: `os.environ["llm.api_key"]`
> 如果希望使用更友好的环境变量名，建议在插件中使用大写下划线格式（如 `LLM_API_KEY`），并相应调整配置文件结构。

## 工具脚本规范

工具脚本通过标准输入接收参数，通过标准输出返回结果。

**输入格式**

脚本从 `stdin` 接收 JSON 对象：

<CodePreview
  files={[
    {
      name: "example.json",
      language: "json",
      content: "{\n  \"name\": \"World\"\n}",
    },
  ]}
/>

**输出格式**

脚本向 `stdout` 输出的内容会作为字符串返回给 Agent。如果需要结构化输出，建议输出 JSON 文本：

<CodePreview
  files={[
    {
      name: "example.json",
      language: "json",
      content: "{\n  \"content\": \"Hello, World!\"\n}",
    },
  ]}
/>

**Python 示例**

<CodePreview
  files={[
    {
      name: "example.py",
      language: "python",
      content: "#!/usr/bin/env python3\nimport json\nimport sys\n\nparams = json.load(sys.stdin)\nname = params.get(\"name\", \"Guest\")\n\nresult = {\"content\": f\"Hello, {name}!\"}\nprint(json.dumps(result))",
    },
  ]}
/>

**TypeScript 示例**

<CodePreview
  files={[
    {
      name: "example.ts",
      language: "typescript",
      content: "#!/usr/bin/env tsx\nimport * as readline from \"readline\";\n\nconst rl = readline.createInterface({\n  input: process.stdin,\n  output: process.stdout,\n  terminal: false,\n});\n\nlet input = \"\";\nrl.on(\"line\", (line) => {\n  input += line;\n});\n\nrl.on(\"close\", () => {\n  const params = JSON.parse(input);\n  const name = params.name || \"Guest\";\n  console.log(JSON.stringify({ content: `Hello, ${name}!` }));\n});",
    },
  ]}
/>

## 附带 Skill

插件可以在根目录（与 `plugin.json` 同级）放一个 `SKILL.md`。Kimi Code CLI 启动时会自动发现，无需额外注册——因为 `~/.kimi/plugins/` 会被整体作为一个 skills root 加载（skill 发现机制详见 [Skills](./skills.md)）。

**目录结构**

<CodePreview
  files={[
    {
      name: "example.txt",
      language: "text",
      content: "my-plugin/\n├── plugin.json\n├── SKILL.md          # 可选：随插件分发的 skill\n└── scripts/",
    },
  ]}
/>

Skill 名称优先取 `SKILL.md` frontmatter 中的 `name`，否则使用插件目录名。该 skill 以 `extra` 作用域被发现，因此同名的项目级或用户级 skill 仍会覆盖它。

**限制**

- 一个插件只能被发现一个 `SKILL.md`。类似 `<plugin>/skills/<name>/SKILL.md` 的嵌套布局**不会**被扫到。

## 完整示例

<CodePreview
  files={[
    {
      name: "example.json",
      language: "json",
      content: "{\n  \"name\": \"sample-plugin\",\n  \"version\": \"1.0.0\",\n  \"description\": \"Sample plugin demonstrating Skills + Tools\",\n  \"tools\": [\n    {\n      \"name\": \"py_greet\",\n      \"description\": \"Generate a greeting message (Python tool)\",\n      \"command\": [\"python3\", \"scripts/greet.py\"],\n      \"parameters\": {\n        \"type\": \"object\",\n        \"properties\": {\n          \"name\": {\n            \"type\": \"string\",\n            \"description\": \"Name to greet\"\n          },\n          \"lang\": {\n            \"type\": \"string\",\n            \"enum\": [\"en\", \"zh\", \"ja\"],\n            \"description\": \"Language\"\n          }\n        },\n        \"required\": [\"name\"]\n      }\n    },\n    {\n      \"name\": \"ts_calc\",\n      \"description\": \"Evaluate a math expression (TypeScript tool)\",\n      \"command\": [\"npx\", \"tsx\", \"scripts/calc.ts\"],\n      \"parameters\": {\n        \"type\": \"object\",\n        \"properties\": {\n          \"expression\": {\n            \"type\": \"string\",\n            \"description\": \"Math expression to evaluate\"\n          }\n        },\n        \"required\": [\"expression\"]\n      }\n    }\n  ]\n}",
    },
  ]}
/>

## 插件安装位置

插件安装在 `~/.kimi/plugins/` 目录下。每个插件是一个独立的子目录，包含完整的 `plugin.json` 和脚本文件。

> 插件与 MCP 服务器是互补的扩展机制：
> - **MCP**：适合需要持续运行的服务、复杂的工具编排、跨进程通信
> - **插件**：适合简单的脚本封装、项目特定的工具、快速原型开发
