---
id: 2026-06-24-think-vs-implement
date: 2026-06-24
type: lesson
severity: critical
applies_to: [all]
related_prompts: ["思维 vs 实现分离"]
related_issues: [2026-06-24-carry-over-5tier, 2026-06-24-think-vs-implement-strict]
tags: [philosophy, design, carry-over]
---

# 经验：项目经验必须分离"思维模式"和"实现方式"

## 核心原则

接收项目经验时**强制二分**：

- **思维模式**（5 步流程 / 门下省 / T1 决策 T2 审核 T3 检索 T4 batch 纯推理 T4 task 执行）= 跨平台**继承**
- **实现方式**（OpenCode batch_call_models / Claude Code Plan subagent / Kimi coder）= 平台特定**重写**

## 反问测试

> "这个设计在另一个平台能用吗？"
- 能用 → 思维（**继承**）
- 不能用 → 实现（**重写**）

## 错误模式

❌ **完全照搬**："OpenCode 的 5 档 Claude Code 也用 5 档"  
❌ **完全放弃**："5 档是 OpenCode 特定，Claude Code 不要"  
✅ **正确**："思维继承 + 实现重写"

## 实际例子

| 设计 | OpenCode | Claude Code | Kimi |
|------|----------|-------------|------|
| T1 决策（思维）| 主会话 (Opus) | 主会话 (Opus) | 主会话 (t1-opus) |
| T2 审核（思维）| Sonnet subagent | Plan subagent | coder subagent |
| T3 检索（思维）| Haiku subagent | Explore subagent | explore subagent |
| T4 batch（思维）| batch_call_models | Explore 配 prompt | explore subagent |
| T4 task（思维）| Task 工具 | general-purpose subagent | coder subagent |

## 应用

→ 已加入 `system-prompt.md` 的【思维 vs 实现分离】段
