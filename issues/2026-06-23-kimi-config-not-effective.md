---
id: 2026-06-23-kimi-config-not-effective
date: 2026-06-23
type: issue
severity: critical
category: config-vs-behavior
applies_to: [kimi]
related_prompts: ["配置 ≠ 行为", "承诺前实测"]
tags: [kimi, subagent, config, max_tokens]
status: resolved
---

# 错误：Kimi 0.18.0/0.19.1 config.toml [models.xxx] 对 subagent 无效

## 错误理解
SKILL.md 表格写"T2=t2-pro/T3=minimax-m3/T4=mimo-v2.5"，认为 Kimi Agent tool 会读 config 选 model。

## 正确理解
实测 Kimi 0.18.0/0.19.1 Agent tool：
- subagent_type → model 由 Kimi 平台**硬编码**
- `coder` / `plan` → deepseek-v4-pro（T1-Opus）
- `explore` → 0.18.0 = deepseek-v4-flash / 0.19.1 = deepseek-v4-pro
- config.toml [models.xxx] **完全不读**
- 升级 Kimi 0.19.1 反而让 explore 从 flash 变 pro（更贵）

## 根因
承诺能力前未实测。基于"应该是这样"假设。

## 修正
- SKILL.md 加【Kimi 0.18.0 subagent_type → model 映射（实测 2026-06-24）】段
- 6 model 表格标记为"设计意图"而非"实际行为"
- 借鉴 edict 等仍是 model-agnostic 价值

## 避免
承诺能力前 30 分钟内实测端到端。
