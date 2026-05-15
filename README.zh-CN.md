# html-effectiveness-docs

`html-effectiveness-docs` 是一个面向项目文档的 agent skill。它帮助 agent 把复杂项目知识做成可阅读、可比较、可交接、可继续执行的 HTML 工作界面，并把最终结论同步回 Markdown 长期文档。

这个 skill 参考了 [The unreasonable effectiveness of HTML](https://thariqs.github.io/html-effectiveness/) 展示的模式：当文档需要对比、空间结构、视觉状态、交互反馈或交接清晰度时，一个自包含 HTML 文件往往比一大段线性 Markdown 更有效。

## Clone

```bash
git clone https://github.com/rwang23/html-effectiveness-docs.git
```

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
- 项目智能 dashboard，把 docs、代码、配置、运行脚本、测试和外部集成证据结合起来
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
  project-intelligence.md
  markdown-sync.md
  quality-bar.md
  html-patterns.md
```

`SKILL.md` 保持短小，只负责触发、路由和入口说明。

`references/` 存放具体方法：

- `routing.md`：判断用户请求属于哪类文档任务。
- `workflows.md`：定义默认工作流。
- `artifact-types.md`：定义支持的 HTML artifact 类型。
- `project-intelligence.md`：定义项目级 artifact 如何从文档、代码、配置、运行时、测试和脚本中抽取背景、结构、技术栈、当前状态、风险和证据。
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

## 安装

这是一个普通的 Agent Skills 风格目录：一个包含 `SKILL.md` 和 `references/` 的文件夹。

### Codex 安装方式

```powershell
git clone https://github.com/rwang23/html-effectiveness-docs.git "$env:USERPROFILE\.codex\skills\html-effectiveness-docs"
```

安装后重启 Codex 或重新加载 skills。

### Claude Code 安装方式

个人 skill：

```bash
git clone https://github.com/rwang23/html-effectiveness-docs.git ~/.claude/skills/html-effectiveness-docs
```

项目 skill：

```bash
git clone https://github.com/rwang23/html-effectiveness-docs.git .claude/skills/html-effectiveness-docs
```

Claude Code 会从 `~/.claude/skills/` 和项目 `.claude/skills/` 目录发现 skills。

### OpenCode 安装方式

OpenCode 原生全局 skill：

```bash
git clone https://github.com/rwang23/html-effectiveness-docs.git ~/.config/opencode/skill/html-effectiveness-docs
```

OpenCode 项目 skill：

```bash
git clone https://github.com/rwang23/html-effectiveness-docs.git .opencode/skill/html-effectiveness-docs
```

OpenCode 也可以发现 Claude-compatible skill 路径，所以 Claude Code 的安装路径也适合作为共享方案。

### OpenClaw 安装方式

全局 skill：

```bash
git clone https://github.com/rwang23/html-effectiveness-docs.git ~/.openclaw/skills/html-effectiveness-docs
```

工作区 skill：

```bash
git clone https://github.com/rwang23/html-effectiveness-docs.git skills/html-effectiveness-docs
```

如果 OpenClaw 环境允许 skills 访问工具或 shell，加载前建议先阅读 `SKILL.md` 和 `references/` 内容。

### Hermes 安装方式

本地 skill：

```bash
git clone https://github.com/rwang23/html-effectiveness-docs.git ~/.hermes/skills/html-effectiveness-docs
```

Hermes 也可以扫描外部 skill 目录。如果你把共享 skills 放在 `~/.agents/skills`，可以 clone 到那里，并在 `~/.hermes/config.yaml` 的 `skills.external_dirs` 中加入该目录。

### 通用手动安装

1. Clone 这个仓库。
2. 把整个文件夹放到你的 agent skills 目录。
3. 保持 `SKILL.md` 和 `references/` 在同一个目录下。
4. 重启 agent 或重新加载 skill index。

## 使用原则

- 不要为了好看而生成 HTML。
- 只有当信息需要比较、结构、视觉、交互或快速浏览时才使用 HTML。
- HTML artifact 应该是自包含、可直接打开的文件。
- HTML 中产生的关键结论必须同步回 Markdown。
- 每个 artifact 都应该帮助读者做决定或继续执行。
- 输出完成前要验证文件存在、内容一致性和交互可用性。
