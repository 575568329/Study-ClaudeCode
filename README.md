# ClaudeCode学习项目

使用Claude Code作为AI导师，系统化学习ClaudeCode的全部能力。

![ClaudeCode](https://img.shields.io/badge/ClaudeCode-Learning-blue)
![Obsidian](https://img.shields.io/badge/Obsidian-Vault-purple)
![Progress](https://img.shields.io/badge/Progress-0%25-red)

## 🎯 项目特点

- **🤖 AI驱动学习**：Claude Code担任私人技术导师，使用苏格拉底教学法
- **📊 全面进度跟踪**：100个技能点的详细掌握情况，量化学习进度
- **🧠 Obsidian知识管理**：双向链接、图谱视图、标签系统
- **📝 每日学习会话**：完整的学习历程记录，AI自动记录

## 📚 学习内容

### 🟢 阶段1：基础使用（30个技能）
- CLI命令和工作流
- 文件操作（Read/Edit/Write）
- 搜索工具（Glob/Grep）
- Bash命令执行

### 🟡 阶段2：高级功能（25个技能）
- Skills系统使用和开发
- Hooks自动化配置
- Agent工具和并行任务
- TodoWrite任务管理

### 🟠 阶段3：工具开发（25个技能）
- MCP服务器开发（Python/Node）
- 自定义Skills开发
- Git Worktree隔离开发
- 团队协作模式

### 🔴 阶段4：项目实战（20个技能）
- 完整项目开发流程
- TDD测试驱动开发
- 代码审查和最佳实践
- 调试和问题解决

## 🚀 快速开始

### 1. 用Obsidian打开

```bash
# 打开Obsidian，选择此目录作为Vault
# 或者命令行（如果配置了）
obsidian://open?vault=claudecode-study
```

### 2. 阅读入门指南

在Obsidian中打开 `00-Start Here.md`

### 3. 开始第一次学习会话

```bash
# 启动Claude Code
claude-code

# 开始提问！
```

## 📖 项目结构

```
claudecode-study/                 # Obsidian Vault根目录
│
├── 00-Start Here.md              # 入口笔记（必读！）
├── 01-Quick-Reference.md         # 快速参考
│
├── 10-Daily-Sessions/            # 每日学习会话
│   ├── _Template.md              # 会话模板
│   └── YYYY-MM-DD.md             # 每日记录
│
├── 20-Progress-Tracking/         # 进度跟踪
│   ├── Skills-Mastered.md        # 技能掌握总览 ⭐
│   ├── Knowledge-Gaps.md         # 知识盲区
│   └── Learning-Roadmap.md       # 学习路线图
│
├── 30-Knowledge-Base/            # 知识库
│   ├── 31-Basic-Usage/           # 基础使用
│   ├── 32-Advanced-Features/     # 高级功能
│   ├── 33-MCP-Development/       # MCP开发
│   └── 34-Project-Practice/      # 项目实战
│
├── 40-Resources/                 # 学习资源
│   ├── Official-Docs.md          # 官方文档
│   ├── Useful-Commands.md        # 常用命令
│   └── Code-Snippets.md          # 代码片段
│
├── 99-Index/                     # 索引
│   ├── Topics.md                 # 主题索引
│   └── Commands.md               # 命令索引
│
├── CLAUDE.md                     # Claude Code导师指令 ⭐
├── README.md                     # 本文件
│
└── docs/                         # 项目文档
    └── plans/                    # 设计和实施计划
        └── 20260326-*.md
```

## 💡 核心理念

### AI驱动的交互式学习

Claude Code不仅是工具，更是你的私人技术导师：

1. **苏格拉底教学法**：先问你知道什么，再构建新知识
2. **理解检查**：解释后验证你的理解程度
3. **适应性教学**：根据反馈调整教学方法
4. **自动记录**：每次会话自动详细记录

### Obsidian知识管理

充分利用Obsidian的特性：

1. **双向链接**：连接相关概念和学习会话
2. **标签系统**：多维度组织（难度、领域、状态）
3. **图谱视图**：可视化知识网络
4. **MOC笔记**：构建内容地图

### 全面进度跟踪

- ✅ 100个技能点的详细清单
- 📊 实时进度百分比
- ❌ 知识盲区识别和优先级
- 📅 学习历史和时间线

## 📊 学习进度

| 阶段 | 技能数 | 掌握 | 进度 |
|------|--------|------|------|
| 🟢 基础使用 | 30 | 0 | 0% |
| 🟡 高级功能 | 25 | 0 | 0% |
| 🟠 工具开发 | 25 | 0 | 0% |
| 🔴 项目实战 | 20 | 0 | 0% |
| **总计** | **100** | **0** | **0%** |

查看详细进度：在Obsidian中打开 `20-Progress-Tracking/Skills-Mastered.md`

## 🎓 使用方法

### 日常学习流程

1. **准备**（5分钟）
   - 打开Obsidian查看今日会话笔记
   - 回顾昨日学习内容
   - 确定今日学习目标

2. **学习**（30-60分钟）
   - 启动Claude Code
   - 提问 → 解释 → 理解检查
   - 实践验证

3. **记录**（自动）
   - Claude自动更新会话笔记
   - 创建/更新知识库笔记
   - 添加双向链接

4. **复习**（5-10分钟）
   - 查看知识图谱
   - 检查反向链接
   - 规划明日学习

### 学习建议

- **持续一致**：每日学习，积少成多
- **主动思考**：多问为什么，理解原理
- **实践验证**：每个概念都要动手实践
- **知识关联**：充分利用双向链接
- **定期复习**：每周回顾本周学习内容

## 🔧 技术栈

- **Claude Code**: AI驱动的CLI工具
- **Obsidian**: 知识管理和笔记系统
- **Git**: 版本控制和备份
- **Markdown**: 文档格式

## 📖 灵感来源

本项目设计灵感来自 [CFP-Study](D:/study/CFP-Study-main) 项目，成功使用AI驱动的苏格拉底教学法通过了CFP考试。

## 🤝 贡献

欢迎改进这个学习项目：

1. Fork本项目
2. 创建你的学习分支
3. 记录你的学习过程
4. 分享你的学习经验

## 📝 许可证

MIT License - 自由使用和修改

## 🎉 开始学习

准备好了吗？

1. ✅ 用Obsidian打开此目录
2. ✅ 阅读 `00-Start Here.md`
3. ✅ 运行 `claude-code`
4. ✅ 开始你的第一次学习会话！

---

**Happy Learning! 🚀**

*有任何问题？查看 `00-Start Here.md` 或 `01-Quick-Reference.md`*
