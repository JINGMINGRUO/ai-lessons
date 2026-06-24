---
id: 2026-06-23-kimi-skill-path-wrong
date: 2026-06-23
type: issue
severity: high
category: config-vs-behavior
applies_to: [kimi]
related_prompts: ["平台硬性事实", "配置 ≠ 行为"]
tags: [kimi, skill-discovery, path]
status: resolved
---

# 错误：Kimi 0.18.0 skill 发现路径假设错

## 错误理解
以为 Kimi 扫 `~/.kimi/skills/`（KIMI_SHARE_DIR），所以 4 个 dir 同步就够。

## 正确理解
实测 Kimi 0.18.0 实际只扫 **`~/.agents/skills/`**。之前 3 个借鉴 commit 的 233 行 SKILL.md 同步到错目录，Kimi 实际加载的是 34776 bytes 旧版。

## 根因
1. 没查 Kimi 0.18.0 实际 skill 扫描机制
2. 4 个 dir 同步是基于"应该都扫"假设

## 修正
- 4 个 dir 全部同步到最新版（1070 行 / 49969 bytes）
- v4 healthcheck 修复：检查路径从 `E:\kimi-data\skills\` 改为 `C:\Users\ming\.agents\skills\`
- 加 "kimi subagent_type mapping" 检查项

## 避免
任何平台硬性事实（路径 / 扫描机制 / 配置方式）只查官方。
