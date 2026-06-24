# ai-lessons

AI 助手经验教训 + 系统提示词（一站式仓库）。

**系统提示词**（主入口，AI 直接 fetch）：
- 👉 https://raw.githubusercontent.com/JINGMINGRUO/ai-lessons/main/system-prompt.md

**结构化索引**（AI 用，frontmatter 驱动）：
- 👉 https://raw.githubusercontent.com/JINGMINGRUO/ai-lessons/main/INDEX.md

## 目录结构

- `system-prompt.md` — 一站式系统提示词
- `INDEX.md` — AI 入口（结构化清单）
- `issues/` — 详细错误（每条带 frontmatter）
- `lessons/` — 凝练原则（每条带 frontmatter）
- `prompts/` — 未来扩展用
- `CHANGELOG.md` — 时间线

## 使用方法

**AI 助手**：新 session 启动时 WebFetch `system-prompt.md`，应用其内容到当前行为。

**用户**：浏览 README / INDEX 即可，不需要手动维护。
