---
id: 2026-06-23-kim-upgrade-worse
date: 2026-06-23
type: issue
severity: medium
category: regression
applies_to: [kimi]
related_prompts: ["承诺前实测", "完成 vs 粉饰"]
tags: [kimi, upgrade, regression]
status: resolved
---

# 错误：Kimi 0.19.1 升级让情况更糟

## 错误理解
升级到 Kimi 0.19.1 后报告"升级成功"。

## 正确理解
Kimi 0.19.1 explore subagent 从 v4-flash 升级到 v4-pro（更贵），且对 --model 参数更严格（带点的 model name 直接报错）。

实际没解决"只能用 2 个 model"的核心问题，反而变贵。

## 根因
升级后没立即实测 subagent 行为，依赖"应该更好"假设。

## 修正
回退到 Kimi 0.18.0（之前 healthcheck 50/50 PASS 的版本），保留 0.19.1 作为可选升级。

## 避免
升级 platform 后立即实测核心场景。
