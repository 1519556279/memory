# Memory — 全局记忆系统

## 模块索引

本 skill 由 6 个模块组成，按编号顺序加载：

| 模块 | 文件 | 说明 |
|------|------|------|
| 01 | modules/01-core.md | 核心概念与初始化流程 |
| 02 | modules/02-storage.md | 记忆存储格式（preferences/facts/index/archive） |
| 03 | modules/03-index.md | 索引结构与检索方式 |
| 04 | modules/04-compression.md | 上下文压缩机制 |
| 05 | modules/05-retrieval.md | 记忆检索与上下文注入 |
| 06 | modules/06-commands.md | 手动命令参考 |

## 快速开始

当检测到用户需求涉及「记忆/记得/忘记/记住」时，加载对应模块执行。

### 新对话启动

1. 加载 01-core.md，执行初始化检测
2. 如有记忆文件，加载并输出恢复报告

### 自动记忆保存

1. 加载 02-storage.md，了解存储格式
2. 根据对话内容提取偏好/事实，写入对应文件

### 记忆检索

1. 加载 03-index.md，了解索引结构
2. 加载 05-retrieval.md，检索并注入上下文

### 上下文压缩

1. 加载 04-compression.md
2. 对话超过 50 轮时自动压缩

### 用户手动命令

1. 加载 06-commands.md
2. 根据命令类型执行对应操作

## 存储位置

```
~/.reasonix/memory/projects/<project-id>/
```
