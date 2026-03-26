# Claude Code CLI命令参考

**最后更新**：2026-03-26
**难度**：⭐⭐ 基础

## 📋 命令分类总览

| 分类 | 命令数 | 用途 |
|------|--------|------|
| Git & 代码管理 | 4个 | 提交、审查、PR管理 |
| 功能开发 | 2个 | 功能开发、SDK创建 |
| 配置管理 | 4个 | 配置、hook、列表 |
| 插件开发 | 2个 | 插件创建、示例 |
| 工具类 | 2个 | 帮助、清理 |
| Astron平台 | 7个 | MaaS模型管理 |
| 自定义Skills | 3个 | 统计、记忆、审查 |

---

## 🔥 核心命令详解（最常用）

### 1. `/commit` - 智能Git提交

**作用**：自动分析代码变更，生成规范的commit message并提交

**工作流程**：
```
1. 自动运行 git status 查看变更
2. 运行 git diff 查看具体改动
3. 分析改动内容，生成commit message
4. 自动 git add + git commit
```

**何时使用**：
- ✅ 完成一个功能点
- ✅ 修复一个bug
- ✅ 重构代码
- ❌ 大型改动（建议手动写详细message）

**示例**：
```bash
/commit
```

**权限要求**：需要允许 `git add`, `git status`, `git commit`

---

### 2. `/feature-dev` - 功能开发助手

**作用**：完整的功能开发流程（探索→设计→实现）

**核心原则**：
- 🔍 **先理解后行动**：探索代码库，理解现有模式
- ❓ **主动提问**：明确模糊需求，不假设
- 🏗️ **架构设计**：提供多个实现方案及权衡
- 📝 **进度跟踪**：使用TodoWrite跟踪进度

**5个阶段**：

| 阶段 | 目标 | 输出 |
|------|------|------|
| **Phase 1: Discovery** | 理解需求 | 需求确认清单 |
| **Phase 2: Codebase Exploration** | 探索代码库 | 现有模式总结 |
| **Phase 3: Clarifying Questions** | 明确细节 | 边界条件、错误处理 |
| **Phase 4: Architecture Design** | 架构设计 | 实现方案对比 |
| **Phase 5: Implementation** | 编写代码 | 完整功能实现 |

**何时使用**：
- ✅ 新功能开发
- ✅ 大型重构
- ✅ 需要深度理解代码库的任务

**示例**：
```bash
/feature-dev 添加用户头像上传功能
```

---

### 3. `/code-review` - PR代码审查

**作用**：并行多Agent审查Pull Request

**审查维度**（5个Agent并行）：

| Agent | 审查重点 | 发现问题类型 |
|-------|---------|-------------|
| #1 | CLAUDE.md合规性 | 编码规范、最佳实践 |
| #2 | 明显Bug扫描 | 逻辑错误、边界条件 |
| #3 | Git历史上下文 | 历史遗留问题 |
| #4 | 历史PR检查 | 重复出现的Bug |
| #5 | 代码注释检查 | 不符合注释说明的实现 |

**过滤标准**：
- 置信度 < 80分 → 过滤掉
- 只保留高置信度问题
- 避免误报和nitpicks

**何时使用**：
- ✅ 需要审查PR时
- ✅ 代码质量控制
- ❌ 简单的typo修复

**示例**：
```bash
/code-review
```

---

### 4. `/help` - 帮助命令

**作用**：显示所有可用命令和Skills

**何时使用**：
- 忘记命令名称
- 想了解新安装的Skills

**示例**：
```bash
/help
```

---

### 5. `/configure` - 配置管理

**作用**：修改Claude Code配置（settings.json）

**常见配置项**：
- 主题设置
- 模型选择
- 权限配置
- 环境变量
- Hooks配置

**何时使用**：
- 首次设置Claude Code
- 修改全局配置
- 添加自动化hooks

**示例**：
```bash
/configure
# 进入交互式配置向导
```

---

## 🛠️ Git工作流命令

### `/commit-push-pr`

**作用**：提交代码 + 推送 + 创建PR（一站式）

**工作流程**：
```
1. /commit 提交代码
2. git push 推送到远程
3. gh pr create 创建Pull Request
```

**何时使用**：
- ✅ 完成功能，准备提交PR
- ❌ 仅提交本地代码（用/commit）

---

### `/review-pr`

**作用**：PR审查工具（类似/code-review，但专门针对PR）

**何时使用**：
- 审查团队成员的PR
- PR合并前final check

---

## 🔧 配置类命令

### `/revise-claude-md`

**作用**：修改项目的CLAUDE.md文件

**何时使用**：
- 更新编码规范
- 添加项目特定指导
- 修改AI行为模式

---

### `/hookify`

**作用**：创建自动化hook

**Hooks类型**：
- `pre-prompt` - 每次对话前触发
- `pre-commit` - Git提交前触发
- `post-response` - AI响应后触发

**何时使用**：
- 自动化重复任务
- 强制执行规范（如自动运行lint）
- 自定义工作流

---

### `/list`

**作用**：列出所有可用命令和Skills

**何时使用**：
- 查看已安装的Skills
- 发现可用命令

---

## 🎨 插件开发命令

### `/create-plugin`

**作用**：创建新的Claude Code插件

**插件结构**：
```
my-plugin/
├── manifest.json      # 插件元数据
├── commands/          # 自定义命令
│   └── my-command.md
├── skills/            # 自定义Skills
│   └── my-skill/
│       └── SKILL.md
└── agents/            # 自定义Agents
    └── my-agent.md
```

**何时使用**：
- 开发团队特定工具
- 封装重复的工作流
- 分享最佳实践

---

## 📊 Astron MaaS平台命令（专用）

> **注**：这些命令用于与讯飞星火MaaS平台集成

| 命令 | 作用 |
|------|------|
| `/astron-login` | 登录MaaS平台 |
| `/astron-browse` | 浏览模型集市 |
| `/astron-compare` | 对比不同模型 |
| `/astron-recommend` | 智能推荐模型 |
| `/astron-service` | 管理推理服务 |
| `/astron-config` | 配置推理服务 |
| `/astron-logout` | 登出平台 |

**何时使用**：
- 需要使用国产大模型
- 模型对比和选型
- 部署推理服务

---

## 🎯 前端开发常用命令组合

### 场景1：日常开发

```bash
# 1. 开始新功能
/feature-dev 添加用户个人中心页面

# 2. 开发过程中
# 直接对话式开发

# 3. 完成后提交
/commit
```

### 场景2：代码审查

```bash
# 方案1：审查本地变更
/user-code-review author=你的名字

# 方案2：审查PR
/code-review
# 或
/review-pr
```

### 场景3：PR工作流

```bash
# 1. 开发完成
/commit-push-pr

# 2. 审查他人PR
/code-review
```

---

## 💡 使用技巧

### 技巧1：Tab自动补全

输入命令前几个字母后按Tab键自动补全：
```bash
/comm<Tab>  → �全为 /commit
```

### 技巧2：命令组合

多个命令可以组合使用：
```bash
/feature-dev 添加登录功能
# ... 开发完成后 ...
/commit
```

### 技巧3：参数传递

某些命令支持参数：
```bash
/user-code-review author=zhangsan branch=feature/login
```

### 技巧4：查看命令详情

想了解某个命令的详细信息？直接调用它！
```bash
/feature-dev
# 会显示完整的Phase 1-5流程说明
```

---

## ⚠️ 注意事项

1. **权限管理**：某些命令需要特定权限（如git操作）
2. **网络依赖**：部分命令需要网络（如code-review需要访问GitHub）
3. **Context限制**：复杂命令会消耗较多token
4. **版本差异**：不同版本的Claude Code可能有不同命令集

---

## 📚 进阶学习路径

1. **掌握基础**：/commit, /help, /list
2. **学习开发**：/feature-dev
3. **代码质量**：/code-review, /user-code-review
4. **自动化**：/hookify, 自定义Skills
5. **插件开发**：/create-plugin

---

## 🔗 相关链接

- [[Skills系统详解]]
- [[Hooks自动化指南]]
- [[插件开发教程]]
- [[10-Daily-Sessions/2026-03-26|今日学习会话]]
