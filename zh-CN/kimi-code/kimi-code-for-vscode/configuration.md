# 配置

在 VS Code 设置的 "Kimi" 部分进行配置（也可通过操作菜单 → **General Config** 打开）。

### 操作审批

| 设置项 | 默认值 | 说明 |
| --- | --- | --- |
| `kimi.yoloMode` | `false` | 自动批准所有工具调用。适用于信任工作流程且追求效率的场景 |

### 文件与编辑器

| 设置项 | 默认值 | 说明 |
| --- | --- | --- |
| `kimi.autosave` | `true` | Kimi 读写文件前自动保存 |
| `kimi.editorContext` | `never` | 控制何时共享当前编辑器的文件和光标位置（`never` / `onConversationStart` / `onFileChange`） |

### 输入与快捷键

| 设置项 | 默认值 | 说明 |
| --- | --- | --- |
| `kimi.useCtrlEnterToSend` | `false` | 使用 Ctrl/Cmd+Enter 发送消息 |
| `kimi.enableNewConversationShortcut` | `false` | 启用 Cmd/Ctrl+N 新建对话快捷键（启用后将占用系统默认的"新建文件"快捷键） |

### 模型与推理

| 设置项 | 默认值 | 说明 |
| --- | --- | --- |
| `kimi.alwaysExpandThinking` | `false` | 默认展开思考/推理过程 |

### 高级

| 设置项 | 默认值 | 说明 |
| --- | --- | --- |
| `kimi.executablePath` | `""` | 自定义 Kimi Code CLI 路径（空值使用内置） |
| `kimi.environmentVariables` | `{}` | 传递给 Kimi Code CLI 的环境变量 |
