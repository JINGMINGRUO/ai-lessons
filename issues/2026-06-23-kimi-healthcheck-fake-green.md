---
id: 2026-06-23-kimi-healthcheck-fake-green
date: 2026-06-23
type: issue
severity: high
category: validation
applies_to: [all]
related_prompts: ["配置 ≠ 行为", "完成 vs 粉饰"]
tags: [healthcheck, kimi, false-positive]
status: resolved
---

# 错误：48/50 健康检查 PASS 是假绿灯

## 错误理解
报告"健康检查 50/50 PASS，所有问题修复完成"。

## 正确理解
实际检查项只测了：
- config 字段存在
- 6 model log-level 0 errors
- config 段名匹配

**没测**：
- subagent 实际跑什么 model
- skill 实际加载的 SKILL.md 版本（Kimi 扫哪个 dir）
- platform 实际行为

## 根因
检查项只测了"配置存在"不是"行为生效"。承诺前没实测。

## 修正
v4 healthcheck 加行为检查项：
- Kimi 实际加载的 SKILL.md 大小/行数
- subagent 实际 model name
- skill 发现路径

## 避免
健康检查要测真行为，不是测字段。
