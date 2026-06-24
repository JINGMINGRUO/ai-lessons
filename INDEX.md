# INDEX（AI 读这个文件判断读哪些）

## 自动加载

- `system-prompt.md`（必读，包含【自动加载】【自动同步】2 条核心 + 全部凝练规则）

## Issues（详细错误，按日期降序）

| 日期 | id | severity | applies_to | 一句话 |
|---|---|---|---|---|
| 2026-06-24 | claude-explore-plan-misread | critical | claude-code | 把 Explore/Plan/GP 误读为 3 档 model 角色 |
| 2026-06-24 | carry-over-5tier | critical | all | 把 OpenCode 5 档全盘搬到 Claude Code（太绝对化）|
| 2026-06-24 | think-vs-implement-strict | high | all | "完全照搬"和"完全放弃"都是错的 |
| 2026-06-23 | kimi-config-not-effective | critical | kimi | config.toml [models.xxx] 对 subagent 无效 |
| 2026-06-23 | kimi-skill-path-wrong | high | kimi | Kimi 0.18.0 扫 `~/.agents/skills/` 不是 KIMI_SHARE_DIR |
| 2026-06-23 | kimi-healthcheck-fake-green | high | kimi | 50/50 PASS 没测 subagent 实际 model |
| 2026-06-23 | kim-upgrade-worse | medium | kimi | Kimi 0.19.1 升级让 explore 从 flash 变 pro（更贵）|
| 2026-06-23 | edict-borrow-no-verify | medium | all | 借鉴 edict 3 commit 233 行没先验证 |
| 2026-06-23 | promise-before-test | high | all | 承诺能力前未实测 |
| 2026-06-23 | config-not-effective | high | all | 配置存在 ≠ 行为生效 |
| 2026-06-23 | finish-vs-decorate | medium | all | 报告分清"完成"vs"粉饰" |
| 2026-06-23 | do-not-modify-unrequested | high | all | 不主动改（用户没要求时不改）|
| 2026-06-24 | dont-read-official | critical | all | 平台硬性事实只查官方，不查我们历史项目 |
| 2026-06-24 | document-not-finished | medium | all | 抓官方文档要读完，不截断 |

## Lessons（凝练原则，按日期降序）

| 日期 | id | severity | applies_to | 一句话 |
|---|---|---|---|---|
| 2026-06-24 | think-vs-implement | critical | all | 接收经验时分离"思维模式"和"实现方式" |
| 2026-06-23 | promise-before-test | critical | all | 任何"应该是这样"的能力承诺 30 分钟内实测 |
| 2026-06-23 | config-not-behavior | high | all | 配置文件存在 ≠ 行为生效，必须测端到端 |
| 2026-06-24 | reset-brain | high | all | 每次接新平台先列 3 个假设问"对吗"再动手 |
| 2026-06-23 | finish-vs-decorate | medium | all | 报告前自问能不能说"实测过"，不能就标"粉饰" |
| 2026-06-23 | wait-for-explicit | high | all | 用户没要求时不主动改，等明确指令 |

## 自动流程

**触发**：用户说"修问题"/"总结一下"/指出错误时

**AI 流程**（按 system-prompt.md【自动同步】段）：

1. WebFetch INDEX.md 找相关 issue/lesson
2. WebFetch 相关文件看详情
3. 创建 `issues/YYYY-MM-DD-<id>.md`（带 frontmatter）
4. 提炼 `lessons/YYYY-MM-DD-<id>.md`（带 frontmatter）
5. 更新 `system-prompt.md`（加 1-2 段）
6. 更新 INDEX.md（表格加新行）
7. `git add` + `git commit -m "..."` — **不 push**（用户决定）
