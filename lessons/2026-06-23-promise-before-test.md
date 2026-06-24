---
id: 2026-06-23-promise-before-test
date: 2026-06-23
type: lesson
severity: critical
applies_to: [all]
related_prompts: ["承诺前实测"]
related_issues: [2026-06-23-promise-before-test]
tags: [validation, testing]
---

# 经验：承诺能力前必须实测

## 原则

任何"应该是这样"的能力承诺，**30 分钟内实测端到端行为**。

## 为什么

- "应该是这样"几乎 100% 是错的（基于文档 / 假设 / 旧经验）
- 不实测就承诺 → 后续整个项目基于错误假设

## 实测方法

1. 用 1-2 个小 prompt 直接试
2. 看 response / log 确认实际行为
3. **空话不算**——必须看到实际数据

## 反例

承诺"Kimi 可为不同 subagent 配不同 model" → 没实测 → 实际 Kimi 0.18.0/0.19.1 都是 hardcoded → 整个 SKILL.md 表格错。

## 应用

→ 已加入 `system-prompt.md` 的【承诺前实测】段
