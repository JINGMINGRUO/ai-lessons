---
id: 2026-06-24-claude-explore-plan-misread
date: 2026-06-24
type: issue
severity: critical
category: misread
applies_to: [claude-code]
related_prompts: ["平台硬性事实", "思维 vs 实现分离"]
tags: [subagent, model, claude-code]
status: resolved
---

# 错误：把 Explore/Plan/GP 误读为 3 档 model 角色

## 错误理解
把 Claude Code 的 3 个 built-in subagent（Explore / Plan / general-purpose）当成 T1/T2/T3 三个 model 档（Opus/Sonnet/Haiku），认为"用 3 档 = 这 3 类"。

## 正确理解
3 类是**思维模式**：
- Explore = 搜索/查找（默认 Haiku, read-only）
- Plan = 规划/设计（默认 inherit, read-only）
- General-purpose = 综合/多步任务（默认 inherit, all tools）

Model 分配是**结果**，不是分类依据。

## 根因
1. 没读完整 docs.claude.com 文档（截断在 17541 bytes，漏掉"Explore / Plan / and general-purpose"列表）
2. Carry over Kimi/OpenCode 项目的"5 档"思维

## 修正
保留"思维模式"经验（5 档 = 决策/审核/检索/纯推理/工程执行），用 Claude Code 原生 subagent 重写实现：
- T1 决策 → 主会话 (Opus)
- T2 审核 → Plan subagent (read-only)
- T3 检索 → Explore subagent (Haiku, read-only)
- T4 batch 纯推理 → Explore subagent 配 prompt
- T4 task 工程执行 → general-purpose subagent

## 避免
- 每次接新平台先查官方文档
- 读完整（不截断）
- 列"思维 vs 实现"二分清单
