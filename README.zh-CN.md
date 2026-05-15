# html-effectiveness-docs

`html-effectiveness-docs` 是一个 Codex skill，用来帮助 agent 把项目文档做成更容易理解、比较、交接和继续执行的工作界面。

这个 skill 参考了 [The unreasonable effectiveness of HTML](https://thariqs.github.io/html-effectiveness/) 里展示的模式：当文档需要对比、空间结构、视觉状态、交互反馈或交接清晰度时，一个自包含 HTML 文件往往比一大段线性 Markdown 更有效。

## 核心理念

```text
HTML artifact = 工作界面，用于探索、比较、评审、交互和交接
Markdown docs = 长期事实源，用于沉淀决策、任务、架构、记忆和项目状态
```

HTML 不是用来替代 Markdown 的。它负责让复杂信息更容易看懂和决策；Markdown 负责保存最终结论。

## 适合什么场景

- 多个技术方案或设计方向的并排比较
- 实现计划、里程碑、风险和验证计划
- 架构地图、模块关系、数据流和热路径
- 设计系统 tokens、组件状态和变体参考
- 文档审计、缺口检查、过期内容检查
- PR、架构、设计或文档评审
- 周报、事故复盘、项目状态报告
- 需要排序、勾选、筛选、调参或导出结果的交互式编辑器

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

## 安装

把这个目录复制到：

```text
C:\Users\desre\.codex\skills\html-effectiveness-docs\
```

然后重启 Codex 或重新加载 skills。

## 目录结构

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

## 使用原则

- 不要为了好看而生成 HTML。
- 只有当信息需要比较、结构、视觉、交互或快速浏览时才使用 HTML。
- HTML 中产生的关键结论必须同步回 Markdown。
- 每个 artifact 都应该帮助读者做决定或继续执行。
- 输出完成前要验证文件存在、内容一致性和交互可用性。
