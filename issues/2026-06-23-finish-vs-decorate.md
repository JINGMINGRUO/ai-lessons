---
id: 2026-06-23-finish-vs-decorate
date: 2026-06-23
type: issue
severity: medium
category: validation
applies_to: [all]
related_prompts: ["完成 vs 粉饰"]
tags: [reporting, honesty]
status: resolved
---

# 错误：报告分不清"完成"和"粉饰"

## 错误模式
- 之前每次都报告"完成"、"3 commit pushed"，但实际是修枝不修根
- 健康检查 50/50 PASS 但没测真行为

## 修正
报告前自问：
> 这个修复如果用户问"你确定吗"，能不能说"实测过"？
- 能 → "完成"
- 不能 → "粉饰"或"待验证"

## 避免
报告要标实测状态。
