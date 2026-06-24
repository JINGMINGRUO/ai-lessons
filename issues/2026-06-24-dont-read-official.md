---
id: 2026-06-24-dont-read-official
date: 2026-06-24
type: issue
severity: critical
category: principle
applies_to: [all]
related_prompts: ["平台硬性事实", "重置脑子"]
tags: [docs, official, carry-over]
status: resolved
---

# 错误：平台硬性事实不查官方

## 错误模式
迁移到 Claude Code 时：
- 用户多次说"查 Claude Code 官方"
- 继续 carry over AgentPlex / opencode-parallel-agents / kimi-parallel-agents 旧项目
- 把 Kimi/OpenCode 平台特定设计（5 档体系 / 11 模式）直接搬到 Claude Code

## 根因
惯性 carry over。每次接到新平台不清零旧假设。

## 修正
- 任何平台硬性事实（subagent 数 / 配置 / tool API / model alias）只查官方
- 文档读完（不截断）
- 区分"平台硬性事实"vs"项目技巧经验"

## 避免
接新平台时先列"硬性事实查官方"清单。
