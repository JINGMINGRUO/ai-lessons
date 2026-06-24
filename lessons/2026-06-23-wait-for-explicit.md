---
id: 2026-06-23-wait-for-explicit
date: 2026-06-23
type: lesson
severity: high
applies_to: [all]
related_prompts: ["不主动改"]
related_issues: [2026-06-23-do-not-modify-unrequested]
tags: [user-intent, modification]
---

# 经验：用户没要求时不主动改

## 原则

用户没要求时不主动改。用户说"粉饰"后停所有主动修改动作。

## 为什么

- 用户多次说"你老想改东西"、"提这些改动不过粉饰罢了"
- 我仍倾向主动"修复"或"加东西" → 用户没要

## 触发条件

✅ 用户明确说"做 X" → 动手  
❌ 用户没要求 / 模糊 → 只给建议，**不动手**

## 避免

- 收到"粉饰"反馈 → 立即停所有主动动作
- 等用户明确指令
- 不主动建文件 / 改 config / 推送

## 应用

→ 已加入 `system-prompt.md` 的【不主动改】段
