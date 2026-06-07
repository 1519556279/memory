# Module 01: Core - 核心概念与初始化

## 什么是记忆系统

记忆系统是一个持久化存储层，让 AI 在跨会话时保持对你的了解。
它通过文件系统存储三类信息：

- **偏好** (Preferences)：你喜欢什么、不喜欢什么、你的习惯
- **事实** (Facts)：已做的决定、项目状态、重要事件
- **存档** (Archive)：压缩后的旧对话摘要（用于省 Tokens）

## 初始化流程

每次新对话开始，自动执行：

```
1. 检测记忆目录是否存在
   ~/.reasonix/memory/projects/<project-id>/

2. 如果存在，加载所有记忆文件
   - preferences.md -> 读取偏好
   - facts.md -> 读取关键事实
   - index.json -> 读取索引
   - archive.jsonl -> 读取最近的存档摘要

3. 输出恢复报告
```

## 恢复报告格式

```
🧠 记忆已恢复
━━━━━━━━━━━━━━━━━━
📋 偏好记录: N 条
   · [摘要]
📌 关键事实: N 条
   · [摘要]
📦 压缩存档: N 条
━━━━━━━━━━━━━━━━━━
```

## 记忆目录结构

```
~/.reasonix/memory/
└── projects/
    └── <project-id>/
        ├── preferences.md     <- 偏好（自动维护）
        ├── facts.md           <- 事实（自动维护）
        ├── index.json         <- 索引（自动维护）
        └── archive.jsonl      <- 存档（压缩时写入）
```
