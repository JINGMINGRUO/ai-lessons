---
id: 2026-06-23-edict-borrow-no-verify
date: 2026-06-23
type: issue
severity: medium
category: carry-over
applies_to: [all]
related_prompts: ["重置脑子", "承诺前实测"]
tags: [edict, borrow, batch]
status: resolved
---

# 错误：借鉴 edict 一次 3 个 commit 233 行没先验证

## 错误理解
一次做：
- Tier 1 借鉴（9 业务圣旨 + 5 阶段 + 状态机 + T2 5 维）
- A1-A6 借鉴（6 审核约束）
- A7-A9 借鉴（状态机扩展）

3 个 commit 233 行，没先 1 个小改动验证假设。

## 根因
速度 > 准确。急着批量做。

## 修正
- 借鉴前先 1-2 个小 commit 验证假设
- 大改动前先暂停，确认方向

## 避免
【重置脑子】每个 commit 前自问"这 1 个改动能独立验证吗"。
