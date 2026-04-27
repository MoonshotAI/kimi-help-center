# `kimi info` 子命令

`kimi info` 显示 Kimi Code CLI 的版本和协议信息。

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "kimi info [--json]",
    },
  ]}
/>

## 选项

| 选项 | 说明 |
|------|------|
| `--json` | 以 JSON 格式输出 |

## 输出内容

| 字段 | 说明 |
|------|------|
| `kimi_cli_version` | Kimi Code CLI 版本号 |
| `agent_spec_versions` | 支持的 Agent 规格版本列表 |
| `wire_protocol_version` | Wire 协议版本 |
| `python_version` | Python 运行时版本 |

## 示例

**文本输出**

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "$ kimi info\nkimi-cli version: 1.20.0\nagent spec versions: 1\nwire protocol: 1.7\npython version: 3.13.1",
    },
  ]}
/>

**JSON 输出**

<CodePreview
  files={[
    {
      name: "command.sh",
      language: "bash",
      content: "$ kimi info --json\n{\"kimi_cli_version\": \"1.20.0\", \"agent_spec_versions\": [\"1\"], \"wire_protocol_version\": \"1.7\", \"python_version\": \"3.13.1\"}",
    },
  ]}
/>
