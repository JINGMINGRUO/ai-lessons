---
id: 2026-06-23-config-not-effective
date: 2026-06-23
type: issue
severity: high
category: config-vs-behavior
applies_to: [all]
related_prompts: ["配置 ≠ 行为"]
tags: [config, behavior, validation]
status: resolved
---

# 错误：配置文件存在不代表生效

## 错误理解
config.toml 写了 [models.t2-pro] 段就以为 T2 subagent 会用 t2-pro。

## 正确理解
- Kimi 0.18.0/0.19.1 subagent **不读** config.toml
- 验证"配置生效"必须测端到端行为（跑 subagent 看实际 model）

## 根因
"配置文件存在 = 生效"的假设。

## 修正
- 健康检查要测真行为（不是测字段）
- 报告前自问"配置真的生效吗"

## 避免
任何"配置有效"声明必须有端到端实测。
