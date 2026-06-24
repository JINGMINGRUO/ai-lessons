---
id: 2026-06-24-document-not-finished
date: 2026-06-24
type: issue
severity: medium
category: validation
applies_to: [all]
related_prompts: ["平台硬性事实"]
tags: [docs, completion]
status: resolved
---

# 错误：抓官方文档没读完

## 错误模式
抓 docs.claude.com 截断在 17541 bytes，漏掉关键段（"Explore / Plan / and general-purpose"列表）。

## 根因
WebFetch 默认有截断，没明确指定读完。

## 修正
- WebFetch 后用 Grep / Read 工具搜关键内容确认读完
- 长文档分段读

## 避免
任何官方文档必须读完。
