# html-effectiveness-docs

`html-effectiveness-docs` 是一个面向项目文档的 agent skill。它帮助 agent 把复杂项目知识做成可阅读、可比较、可交接、可继续执行的 HTML 工作界面，并把最终结论同步回 Markdown 长期文档。

这个 skill 参考了 [The unreasonable effectiveness of HTML](https://thariqs.github.io/html-effectiveness/) 展示的模式：当文档需要对比、空间结构、视觉状态、交互反馈或交接清晰度时，一个自包含 HTML 文件往往比一大段线性 Markdown 更有效。

## 背景

很多项目文档不好用，不是因为内容少，而是因为表达方式太线性。

架构、实现计划、设计系统、PR 评审、周报、事故复盘、交接文档，本质上通常包含：

- 模块关系
- 数据流
- 时间线
- 多方案对比
- 风险和缓解措施
- 决策依据
- 当前状态和下一步

这些信息如果全部写成长段 Markdown，读者很难快速抓住结构。HTML 更适合承载“工作界面”：并排比较、折叠信息、时间线、图表、可复制摘要、交互式选择和导出。

但 Markdown 仍然是长期事实源。所以这个 skill 采用双轨模型。

## 核心模型

```text
HTML artifact = 工作界面，用于探索、比较、评审、交互和交接
Markdown docs = 长期事实源，用于沉淀决策、任务、架构、记忆和项目状态
```

HTML 不是用来替代 Markdown 的。它负责让复杂信息更容易理解和决策；Markdown 负责保存最终结论。

## 能做什么

这个 skill 可以辅助 agent 创建：

- 多个技术方案或设计方向的并排比较
- 实现计划、里程碑、风险和验证计划
- 架构地图、模块关系、数据流和热路径
- 设计系统 tokens、组件状态和变体参考
- 文档审计、缺口检查、过期内容检查
- PR、架构、设计或文档评审
- 周报、事故复盘、项目状态报告
- 需要排序、勾选、筛选、调参或导出结果的交互式编辑器

## 设计方式

这个 skill 使用 Router + References 结构：

```text
SKILL.md
references/
  routing.md
  workflows.md
  artifact-types.md
  markdown-sync.md
  quality-bar.md
  html-patterns.md
```

`SKILL.md` 保持短小，只负责触发、路由和入口说明。

`references/` 存放具体方法：

- `routing.md`：判断用户请求属于哪类文档任务。
- `workflows.md`：定义默认工作流。
- `artifact-types.md`：定义支持的 HTML artifact 类型。
- `markdown-sync.md`：定义哪些结论要同步回 Markdown。
- `quality-bar.md`：定义完成标准和反模式。
- `html-patterns.md`：定义自包含 HTML 的写法和交互约束。

## 默认工作流

```text
Context Scan
-> Route
-> Artifact Plan
-> Create or Update Work Interface
-> Extract Decisions
-> Sync Markdown
-> Verify
-> Report
```

每次使用时，skill 会先读取项目本地规则，例如 `AGENTS.md`、`README`、`docs/`、`context/`，再决定应该输出 Markdown、HTML，还是双轨输出。

## 默认文件位置

最终可交付 HTML artifact 默认放在：

```text
docs/effectiveness-artifact/
```

临时探索、草稿和中间过程默认放在：

```text
context/raw/
```

长期事实源仍然写入项目文档，例如：

```text
docs/TODO.md
docs/active-tasks.md
docs/CHANGELOG.md
docs/memory.md
docs/FORYOU.md
docs/plan/
docs/report/
```

如果项目本地规则指定了其他目录，以项目规则为准。

## Clone

```bash
git clone https://github.com/rwang23/html-effectiveness-docs.git
```

## Codex 安装方式

把这个仓库 clone 到 Codex skills 目录：

```powershell
git clone https://github.com/rwang23/html-effectiveness-docs.git "$env:USERPROFILE\.codex\skills\html-effectiveness-docs"
```

然后重启 Codex 或重新加载 skills。

手动复制也可以：

```powershell
Copy-Item -Recurse -Force .\html-effectiveness-docs "$env:USERPROFILE\.codex\skills\html-effectiveness-docs"
```

## 其他 Agent 的安装方式

这个仓库本质上是纯 Markdown skill。只要你的 agent 系统支持本地 skill、规则文件、system prompt 或 reusable instruction，都可以使用。

通用方式：

1. Clone 这个仓库。
2. 把 `SKILL.md` 注册为 skill 入口。
3. 保持 `references/` 和 `SKILL.md` 在同一目录。
4. 让 agent 根据当前任务只读取相关 reference 文件。

Claude Code 风格的 agent 如果支持 skills，可以复制到类似目录：

```bash
git clone https://github.com/rwang23/html-effectiveness-docs.git ~/.claude/skills/html-effectiveness-docs
```

Cursor、Windsurf 或其他 IDE agent 可以把 `SKILL.md` 加入 rules/custom instructions，并保证 agent 能读取旁边的 `references/` 文件。

## 使用示例

```text
Use html-effectiveness-docs to compare three implementation approaches and create a final artifact under docs/effectiveness-artifact/.
```

```text
Use html-effectiveness-docs to audit our docs folder and sync durable action items back to docs/TODO.md.
```

```text
Use html-effectiveness-docs to create an architecture map of this repo, then write the durable mental model to docs/FORYOU.md.
```

## 使用原则

- 不要为了好看而生成 HTML。
- 只有当信息需要比较、结构、视觉、交互或快速浏览时才使用 HTML。
- HTML artifact 应该是自包含、可直接打开的文件。
- HTML 中产生的关键结论必须同步回 Markdown。
- 每个 artifact 都应该帮助读者做决定或继续执行。
- 输出完成前要验证文件存在、内容一致性和交互可用性。
