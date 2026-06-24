---
id: 2026-06-24-carry-over-5tier
date: 2026-06-24
type: issue
severity: critical
category: carry-over
applies_to: [claude-code]
related_prompts: ["重置脑子", "思维 vs 实现分离"]
tags: [opencode, claude-code, carry-over]
status: resolved
---

# 错误：把 OpenCode 5 档体系全盘搬到 Claude Code

## 错误理解
说"5 档 T1/T2/T3/T4 batch/T4 task 是 OpenCode 平台特定，Claude Code 根本不需要 5 档" — 直接放弃。

## 用户纠正
5 档 = 5 种**思维模式**（跨平台通用），不是 OpenCode 特定。思维继承，实现重写。

## 根因
太绝对化。接收经验时分不清"思维"和"实现"。

## 修正
5 档思维保留（决策/审核/检索/纯推理/工程执行），用 Claude Code 原生 subagent 重写：
- T1 决策 → 主会话
- T2 审核 → Plan subagent
- T3 检索 → Explore subagent
- T4 batch 纯推理 → Explore 配 prompt
- T4 task 工程执行 → general-purpose

## 避免
- 接收经验时分"思维 vs 实现"
- 反问测试："另一个平台能用吗" — 能用是思维（继承），不能用是实现（重写）
