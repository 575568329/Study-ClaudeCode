# ClaudeCode常用命令

## CLI命令

### 启动和退出
```bash
# 启动Claude Code
claude-code

# 退出
Ctrl+C
或输入 /exit
```

### 帮助和信息
```bash
# 查看帮助
?

# 查看可用Skills
/help

# 清空对话
/clear
```

## 文件操作工具

### Read工具
```python
# 读取单个文件
Read: "path/to/file.md"

# 读取多个文件（并行）
Read: ["file1.md", "file2.md", "file3.md"]

# 读取特定行
Read: "file.md"
offset: 100
limit: 50
```

### Edit工具
```python
# 单处修改
Edit: "file.md"
old_string: "原始内容"
new_string: "新内容"

# 多处修改
Edit: "file.md"
old_string: "重复内容"
new_string: "新内容"
replace_all: true
```

### Write工具
```python
# 创建新文件
Write: "path/to/new-file.md"
content: "文件内容"
```

## 搜索工具

### Glob工具
```python
# 查找所有Python文件
Glob: "**/*.py"

# 查找特定目录
Glob: "src/**/*.ts"
```

### Grep工具
```python
# 搜索内容
Grep: "function"
path: "src/"
output_mode: "files_with_matches"

# 搜索并显示上下文
Grep: "TODO"
path: "."
-C: 3
```

## Bash命令

### 系统操作
```bash
# 列出文件
ls -la

# 创建目录
mkdir -p path/to/dir

# 查看文件内容
cat file.md
head -20 file.md
tail -50 file.md
```

### Git操作
```bash
# 状态
git status

# 提交
git add .
git commit -m "message"

# 推送
git push
```

## Skills使用

```bash
# 查看所有Skills
/help

# 调用Skill（无参数）
/commit

# 调用Skill（带参数）
/commit -m "fix bug"

# 查看特定Skill帮助
/skill-name help
```

## 更新日志

添加新命令时，请按类别整理并添加示例。
