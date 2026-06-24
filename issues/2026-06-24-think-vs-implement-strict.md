---
id: 2026-06-24-think-vs-implement-strict
date: 2026-06-24
type: issue
severity: high
category: extreme
applies_to: [all]
related_prompts: ["思维 vs 实现分离", "不要绝对化"]
tags: [philosophy, design]
status: resolved
---

# 错误："完全照搬"和"完全放弃"都是错的

## 错误模式
- ❌ 完全照搬："OpenCode 的 5 档 Claude Code 也用 5 档"
- ❌ 完全放弃："5 档是 OpenCode 特定，Claude Code 不要"
- ✅ 正确：思维继承 + 实现重写

## 根因
接收项目经验时"非黑即白"思维，不区分"思维模式"和"实现方式"。

## 修正
- 思维模式（5 步流程 / 门下省 / 5 档 role / 状态机）= 跨平台**继承**
- 实现方式（OpenCode batch_call_models / Claude Code Plan subagent / Kimi coder）= 平台特定**重写**

## 反问测试
> "这个设计在另一个平台能用吗？"
- 能用 → 思维（继承）
- 不能用 → 实现（重写）

## 避免
收到经验时先二分（思维 / 实现），再决定继承还是重写。
