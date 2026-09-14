# writing-report-skill-by-sheng

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Agent Skills](https://img.shields.io/badge/Agent%20Skills-Cursor%20%7C%20Codex%20%7C%20Claude%20Code-0A7A3E.svg)](https://agentskills.io)

起草、改写或润色**已完成工作**的中文学术研究报告。仓库与 Skill 名称均为 `writing-report-skill-by-sheng`。体裁包括博后出站报告、学位论文、结题 / 进展 / 技术报告。给定已有成果与素材后，默认按这条链路写作：

```text
已锁研究框架（柱 / 难点 / 成果归属）
  -> 从当前稿抽出台账
    -> 按章/节派发写作
      -> 中文学术润色
```

只学习结构、段落职责和锁词纪律，不预填任何课题词，不编造方法名、柱划分或实验数字。基金 / 开题等「拟开展」文本不要用本 Skill 当正文模板。

本 Skill 只负责研究报告正文。封面、参考文献不覆盖。

## 兼容性

本仓库遵循 [Agent Skills](https://agentskills.io) 开放格式。可执行核心为根目录 `SKILL.md`（中文，供 Agent 执行）。英文对照见 [`SKILL.en.md`](SKILL.en.md)，供阅读，不参与 Agent 执行。各平台专有配置置于独立文件，以保持可移植部分不受平台字段影响。

| 平台 | 安装位置 | 额外文件 | 调用方式 |
| --- | --- | --- | --- |
| Cursor | `~/.cursor/skills/writing-report-skill-by-sheng` | 无 | `@writing-report-skill-by-sheng` 或 `/writing-report-skill-by-sheng` |
| Codex | `~/.codex/skills/writing-report-skill-by-sheng` | `agents/openai.yaml`、`.codex-plugin/` | `$writing-report-skill-by-sheng` |
| Claude Code | `~/.claude/skills/writing-report-skill-by-sheng` 或插件市场 | `agents/claude.yaml`、`.claude-plugin/` | `/writing-report-skill-by-sheng` |
| Agent Skills | `~/.agents/skills/writing-report-skill-by-sheng` | `.agents/plugins/` | 按该客户端的 skill 调用语法 |

仓库名、Skill 名称与安装目录均为 `writing-report-skill-by-sheng`，与 `SKILL.md` 中的 `name` 字段一致。

`SKILL.md` 只保留可移植字段：`name`、`description`、`license`、`compatibility`、`metadata`。Cursor 的 `disable-model-invocation`、Claude 的 `user-invocable`、Codex 的界面文案都不写入该文件。本 Skill 设计为**显式调用**；Codex 侧 `allow_implicit_invocation` 为 `false`。

## 安装

在本仓库目录下执行：

```bash
./scripts/install.sh
```

脚本会把同一套 skill 安装到本机已存在的 Cursor、Codex、Claude Code、Agent Skills 目录。安装完成后，请新开对话再使用。

只安装某一个平台：

```bash
./scripts/install.sh --cursor
./scripts/install.sh --codex
./scripts/install.sh --claude
./scripts/install.sh --agents
```

发布到 GitHub 后，也可在对话中发送：

```text
请安装 https://github.com/JiaweiSheng/writing-report-skill-by-sheng.git
```

或：

```bash
npx skills add JiaweiSheng/writing-report-skill-by-sheng -g
```

### Cursor

```bash
git clone https://github.com/JiaweiSheng/writing-report-skill-by-sheng.git \
  ~/.cursor/skills/writing-report-skill-by-sheng
```

安装完成后，请新开 Agent 对话。也可通过 `/writing-report-skill-by-sheng` 手动调用。建议在 **Customize → Skills** 中设为手动调用，避免未点名时整本加载。

### Codex

```bash
git clone https://github.com/JiaweiSheng/writing-report-skill-by-sheng.git \
  ~/.codex/skills/writing-report-skill-by-sheng
```

Codex 读取 `SKILL.md` 以及 `agents/openai.yaml` 中的显示名称、简介与默认提示。请用 `$writing-report-skill-by-sheng` 显式调用。

### Claude Code

```bash
git clone https://github.com/JiaweiSheng/writing-report-skill-by-sheng.git \
  ~/.claude/skills/writing-report-skill-by-sheng
```

或通过插件市场安装：

```text
/plugin marketplace add JiaweiSheng/writing-report-skill-by-sheng
/plugin install writing-report-skill-by-sheng
```

## 使用示例

```text
@writing-report-skill-by-sheng 先锁研究框架，我只有论文清单

用 writing-report-skill-by-sheng 写中文摘要和 Abstract

写绪论第 1 章，背景与意义分成两个 section

润色这一节的研究动机，不要改锁词

完整润色这项成果的四个 subsection
```

未点名本 Skill 时不要假定已加载。框架未锁定时，只走研究框架，不要写摘要、绪论或工作章。

## 写作原则

- 先锁框架、再建台账、后写句子
- 不替用户发明课题，不预填课题词
- 用户当场改定一词后，全书与台账同步该词
- 主张强度不超过已有素材；缺数字标【待核】，不补造
- 体裁没有的章（如进展报告可无相关工作）跳过，不补空章

## 仓库结构

```text
.
├── SKILL.md                         # 可移植 Agent Skill 核心（中文，供执行）
├── SKILL.en.md                      # SKILL.md 的英文对照（供人阅读）
├── chapter/                         # 全书层与工作章槽位
├── section/                         # 一项成果四小节
├── polish/                          # 中文学术润色
├── agents/
│   ├── openai.yaml                  # Codex / OpenAI UI 元数据
│   └── claude.yaml                  # Claude Code 调用元数据
├── .claude-plugin/                  # Claude Code 插件与市场清单
├── .codex-plugin/                   # Codex 插件清单
├── .agents/plugins/                 # Agent Skills 市场清单
├── scripts/install.sh               # 本机多 Agent 安装
├── README.md
└── LICENSE
```

## 许可证

MIT。详见 [LICENSE](LICENSE)。
