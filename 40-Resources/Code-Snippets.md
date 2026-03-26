# 代码片段收藏

## Claude Code相关

### Skills定义示例
```yaml
# ~/.claude/skills/my-skill.md
name: my-skill
description: 我的自定义Skill

parameters:
  - name: input
    description: 输入参数
    required: true

prompt: |
  请帮我处理这个：{{input}}
  使用以下步骤：
  1. 分析
  2. 处理
  3. 输出
```

### Hooks配置示例
```json
// ~/.claude/settings.json
{
  "hooks": {
    "PrePrompt": [
      {
        "type": "command",
        "command": "echo 'Starting session'"
      }
    ],
    "PreCommit": [
      {
        "type": "command",
        "command": "npm test"
      }
    ]
  }
}
```

## MCP开发

### FastMCP示例（Python）
```python
from fastmcp import FastMCP

mcp = FastMCP("My Server")

@mcp.tool()
def calculate(expression: str) -> float:
    """计算数学表达式"""
    return eval(expression)

if __name__ == "__main__":
    mcp.run()
```

### MCP SDK示例（TypeScript）
```typescript
import { Server } from "@modelcontextprotocol/sdk/server/index.js";

const server = new Server({
  name: "my-server",
  version: "1.0.0"
});

server.setRequestHandler(
  CallToolRequestSchema,
  async (request) => {
    // 工具实现
  }
);
```

## Obsidian

### Dataview查询
```dataview
TABLE difficulty, confidence
FROM #技能/已掌握
SORT difficulty DESC
```

### Templater模板
```javascript
---
date: <% tp.date.now("YYYY-MM-DD") %>
---
```

## 更新日志

添加新片段时，请标注语言和用途。
