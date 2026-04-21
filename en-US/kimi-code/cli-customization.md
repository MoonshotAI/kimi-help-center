---
title: "Customization & reference"
slug: "cli-customization"
order: 9
extract_headings: false
preview: false
---

<SeoMeta
  title="Customization \u0026 reference - Kimi Help Center"
  description="Kimi Code CLI offers extensive customization options, allowing you to tailor the AI's behavior and workflow to your needs."
/>

Kimi Code CLI offers extensive customization options, allowing you to tailor the AI's behavior and workflow to your needs.

## Configuration file

Kimi Code CLI uses `~/.kimi/config.toml` as its global configuration file, supporting both TOML and JSON formats. You can configure:

- **API Providers and Models**: Set up different model providers, API endpoints, and keys.
- **Default Model**: Specify the default model to use.
- **Runtime Parameters**: Adjust timeout, concurrency, output format, and other runtime settings.

> Use the `/config` command to quickly open the configuration file for editing.

## AGENTS.md project configuration

Place an `AGENTS.md` file in your project root to provide the AI with project-level context:

- **Project Background**: Describe the project's functionality, architecture, and tech stack.
- **Build Steps**: How to install dependencies, build the project, and run tests.
- **Code Conventions**: Naming conventions, directory structure rules, code style preferences.
- **Special Notes**: Security restrictions, performance requirements, and other important considerations.

Use the `/init` command to have the AI automatically scan your project and generate an initial `AGENTS.md`. You can also manually edit the file to add project-specific information. `AGENTS.md` files can be placed in any subdirectory — the AI will automatically load relevant configurations.

## Custom system prompt

You can customize the AI's system prompt in several ways:

- **Global system prompt**: Write it in `~/.kimi/AGENTS.md` — applies to all projects.
- **Project-level system prompt**: Write it in the project root's `AGENTS.md` — applies only to the current project.
- **Launch parameter**: Use the `--system-prompt` flag to specify at startup.

Project-level configuration overrides the global configuration, and the launch parameter has the highest priority.

## MCP integration

Kimi Code CLI supports the Model Context Protocol (MCP), enabling connections to external tools and data sources to extend the AI's capabilities:

- **MCP Server Configuration**: Add MCP server addresses in the configuration file so the AI can invoke external tools.
- **Built-in MCP Support**: Some commonly used MCP tools are built in and require no additional configuration.
- **Custom MCP Servers**: You can develop your own MCP servers to provide domain-specific capabilities.

MCP configuration can be placed in `~/.kimi/config.toml` or in project-level configuration files.

## Environment variables

Kimi Code CLI supports configuration via environment variables — useful for CI/CD pipelines and scripts:

| Environment Variable | Description |
| --- | --- |
| `KIMI_API_KEY` | API key |
| `KIMI_BASE_URL` | Custom API endpoint |
| `KIMI_MODEL` | Default model name |
| `KIMI_MAX_TOKENS` | Maximum output token count |

Environment variables take priority over settings in the configuration file.

## More references

- **Slash Command Reference**: Use `/help` to view all available commands.
- **CLI Parameter Reference**: Run `kimi --help` to view all launch parameters.
- **Official Documentation**: Visit [Kimi Code Docs](https://kimi.com/code/docs) for the latest complete documentation.
