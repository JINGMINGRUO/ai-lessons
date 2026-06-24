---
id: 2026-06-23-promise-before-test
date: 2026-06-23
type: issue
severity: high
category: validation
applies_to: [all]
related_prompts: ["承诺前实测"]
tags: [validation, promise]
status: resolved
---

# 错误：承诺能力前未实测

## 错误理解
在 SKILL.md 表格中写"T2=t2-pro/T3=minimax-m3/T4=mimo-v2.5"等 subagent_type → model 映射，**没实测 Kimi Agent tool 实际行为**就承诺"不同 subagent 配不同 model"。

## 根因
基于"应该是这样"假设，没实测。

## 修正
- 实测 Kimi 0.18.0/0.19.1 Agent tool 实际行为
- 把"承诺能力前 30 分钟内实测"写进 system-prompt.md

## 避免
任何"应该是这样"的能力承诺，30 分钟内实测端到端行为。空话不算。
