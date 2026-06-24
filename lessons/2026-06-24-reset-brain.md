---
id: 2026-06-24-reset-brain
date: 2026-06-24
type: lesson
severity: high
applies_to: [all]
related_prompts: ["重置脑子"]
related_issues: [2026-06-24-dont-read-official, 2026-06-24-carry-over-5tier]
tags: [cognitive-bias, fresh-start]
---

# 经验：每次接新平台先重置脑子

## 原则

每次接新平台任务，**先列 3 个假设问"对吗"再动手**。禁止 carry over 旧平台结构到新平台。

## 为什么

- 5+ 次用户纠正我 carry over 旧项目（Kimi / OpenCode）到 Claude Code
- 每次说"哦好的下次注意"，下次又用同样思路
- 习惯性 carry over 是最大错误源

## 重置方法

1. 假设旧平台知识 = **错的**
2. 列新平台硬性事实（只查官方）
3. 列"我需要继承什么"（思维模式）
4. 列"我需要重写什么"（实现方式）
5. 才动手

## 反问测试

> "用户说'查官方'了吗？"
- 是 → 不要查旧项目
- 否 → 才考虑继承

## 应用

→ 已加入 `system-prompt.md` 的【重置脑子】段
