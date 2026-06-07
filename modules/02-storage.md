# Module 02: Storage - 记忆存储

## preferences.md 格式

按日期分组，每条一行。

```markdown
# 偏好记录

## 2024-06-07
- 编程偏好：TypeScript，2 空格缩进，不用 any
- 写作偏好：仙侠小说，主角名林峰
- 设计偏好：Apple 风格，简洁配色

## 2024-06-08
- 工具偏好：用 pnpm 代替 npm
```

### 自动保存触发条件

| 触发场景 | 示例对话 | 保存内容 |
|---------|---------|---------|
| 你明确说喜欢什么 | "我喜欢用 TypeScript" | 编程偏好：TypeScript |
| 你明确说讨厌什么 | "我不喜欢 any 类型" | 编程偏好：禁止 any |
| 你提出要求 | "代码用 2 空格缩进" | 编程偏好：2 空格 |

## facts.md 格式

用于记录关键事实、决策、项目状态。

```markdown
# 关键事实

## 2024-06-07
- 安装了 tianming-skill（小说创作）
- 删除了 novel-memory-manager
```

### 自动保存触发条件

| 触发场景 | 示例对话 | 保存内容 |
|---------|---------|---------|
| 你做了决定 | "把这个功能删掉" | 删除了 xxx |
| 项目进度 | "已经写到第 5 章了" | 小说进度：第 5 章 |
| 安装/卸载 | "帮我装个 xxx" | 安装了 xxx |

## archive.jsonl 格式

每行一条 JSON。

```jsonl
{"date":"2024-06-07","summary":"讨论了记忆skill的设计","tags":["记忆","设计"],"tokens_saved":2800,"importance":3}
```

## index.json 格式

索引文件，加速检索。

```json
{
  "preferences": [
    {"id":"pref-001","content":"TypeScript","tags":["代码"],"date":"2024-06-07","keywords":["typescript","ts"]}
  ],
  "facts": [
    {"id":"fact-001","content":"删除了 computer-control","tags":["项目"],"date":"2024-06-07","keywords":["删除","computer-control"]}
  ],
  "lastUpdated": "2024-06-08"
}
```

## 保存规则

- 相同日期的内容追加到当天分组下
- 每天一个分区，按日期倒序排列
- 文件大小超过 100KB 时自动归档旧内容
- 使用 UTF-8 编码
