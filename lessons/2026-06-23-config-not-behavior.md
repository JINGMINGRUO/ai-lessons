---
id: 2026-06-23-config-not-behavior
date: 2026-06-23
type: lesson
severity: high
applies_to: [all]
related_prompts: ["配置 ≠ 行为"]
related_issues: [2026-06-23-config-not-effective, 2026-06-23-kimi-config-not-effective]
tags: [config, behavior, validation]
---

# 经验：配置 ≠ 行为

## 原则

**配置文件存在不代表生效**。必须测端到端行为（跑实际功能，看实际输出）。

## 为什么

- Kimi 0.18.0/0.19.1 config.toml [models.xxx] 写了但 subagent **不读**
- 健康检查 50/50 PASS 测了字段，没测行为 → 假绿灯

## 实测方法

1. 跑实际功能
2. 看真实输出（log / response / 文件）
3. 不只看 config 字段在不在

## 健康检查原则

健康检查要测**真行为**，不是测字段。

## 应用

→ 已加入 `system-prompt.md` 的【配置 ≠ 行为】段
