---
name: writing-report-skill-by-sheng
description: >-
  Drafts, revises, or polishes completed Chinese academic research reports
  (postdoc completion reports, theses, closing / progress / technical reports).
  Requires existing results and a user-locked research framework before writing
  body text. Dispatches to framework, abstract, introduction, related work,
  conclusion, technical-chapter intro / prelim / summary, a four-subsection
  result, or Chinese academic polishing. Use when the user @ this skill or asks
  to write or polish 研究报告, 出站报告, 学位论文, 结题报告, 进展报告, 技术报告, 研究框架,
  研究框图, 总体框架图, 摘要, Abstract, 关键词, 绪论, 相关工作, 国内外研究现状, 结论, 章引言,
  预备知识, 本章小结, 一项工作, 一项成果, 研究动机, 方法设计, 实验分析, 本节小结, 润色, 去AI味, 学术文风.
license: MIT
compatibility: Any agent that supports Agent Skills, including Cursor, Codex, and Claude Code.
metadata:
  version: "1.0.0"
  author: JiaweiSheng
  short-description: Draft Chinese research reports from a locked framework
---

# 中文学术研究报告写作（writing-report-skill-by-sheng）

仓库与安装目录均为 `writing-report-skill-by-sheng`。**须在对话中显式 @ / 点名本 skill**，不要假定已自动加载。英文对照见 [SKILL.en.md](SKILL.en.md)，供阅读，不参与 Agent 执行。

只读本文件做派发。**未点名的子文件不要整本读入。** 读任一子文件时，同时遵守下文“行文通则”。读 `section/` 下任一文件时，**同时读** [section/consistency.md](section/consistency.md)。写完任一章/节后，若用户未禁止，再读 [polish/academic-zh.md](polish/academic-zh.md) 过一遍。写/润相关工作章时，[chapter/related-work.md](chapter/related-work.md) 的四段骨架（已选段首、末句“然而，”、`\textbf{总结分析：}`）优先于 polish 的去同构。

## 适用范围与前提

写的是**已完成工作**的中文研究报告，不是立项书。体裁包括出站报告、学位论文、结题 / 进展 / 技术报告等。有哪个槽位就按派发表写，没有的跳过（例如进展报告可无相关工作章）。主语「本文 / 本报告」随体裁选一种，全书统一。

**两条前提，缺一则停写正文：**

1. **已有研究成果与素材。** 论文、实验主表、方法说明、已有章节等，用来登记每项成果。没有素材不要编方法名、不要编柱。
2. **研究框架已手工锁定。** 柱划分、每柱两点难点、成果归属、顺承箭头须由用户拍板。代理只协助清点与填格，不替用户发明课题。未锁定时只读 [chapter/research-framework.md](chapter/research-framework.md)，不要写摘要、绪论或工作章。

基金 / 开题等「拟开展」文本不要用本 skill 当正文模板。任务书若出现，只抽应用口径。

**先锁框架、再建台账、后写句子。** 台账字段见下文；取值从已锁框架与**当前稿**抽取，本 skill 不预填任何课题词。用户当场改定一词后，全书与台账同步该词，禁止用近义润回去。

## 派发

| 用户说法或当前 `\section`/`\subsection` | 只读 |
|---|---|
| 做研究框架 / 研究框图 / 总体框架图 / 框架未锁 / 只有论文清单 | [chapter/research-framework.md](chapter/research-framework.md)（先清点素材，用户拍板后再锁台账；未锁定不得写正文） |
| 写摘要 / 中文摘要 / Abstract / 关键词 / 打开 Frontmatter | [chapter/abstract.md](chapter/abstract.md)（两块：总述漏斗 + 按柱分条；条内提出—通过—提升，不报数字） |
| 写绪论 / 第 1 章 / 研究背景 / 研究问题 / 贡献 | [chapter/introduction.md](chapter/introduction.md)（先读模式、改定经验与台账字段，再写；背景与意义分成两个 `\section`） |
| 写相关工作 / 国内外研究现状 | [chapter/related-work.md](chapter/related-work.md)（四段骨架优先于 polish 去同构） |
| 写结论 / 总结与展望 | [chapter/conclusion.md](chapter/conclusion.md)（两节：工作总结 / 未来工作展望） |
| 写章引言 / 章首引言 / 工作章 `\section{引言}` | [chapter/technical-chapter-intro.md](chapter/technical-chapter-intro.md) |
| 写预备知识 / 工作章 `\section{预备知识}` | [chapter/technical-chapter-prelim.md](chapter/technical-chapter-prelim.md) |
| 写本章小结 / 工作章 `\section{本章小结}` | [chapter/technical-chapter-summary.md](chapter/technical-chapter-summary.md) |
| 完整润色某成果 / 写某工作整节 / 点名方法名且未只点某一小节 | [section/0-work.md](section/0-work.md) + [section/consistency.md](section/consistency.md) |
| 写研究动机 / 节引言 / `\subsection{研究动机}` | [section/1-motivation.md](section/1-motivation.md) + [section/consistency.md](section/consistency.md) |
| 写方法设计 / `\subsection{方法设计}` | [section/2-method.md](section/2-method.md) + [section/consistency.md](section/consistency.md) |
| 写实验分析 / `\subsection{实验分析}` | [section/3-experiment.md](section/3-experiment.md) + [section/consistency.md](section/consistency.md) |
| 写本节小结 / `\subsection{本节小结}` | [section/4-summary.md](section/4-summary.md) + [section/consistency.md](section/consistency.md) |
| 润色 / 去 AI 味 / 改学术文风 | [polish/academic-zh.md](polish/academic-zh.md) |

未点名子任务时：看当前打开的 `.tex` 光标所在 `\chapter` / `\section` / `\subsection`，按上表读一份。打开摘要源或光标在摘要段时，读 [chapter/abstract.md](chapter/abstract.md)。凡派到 `section/`，都加读 `consistency.md`，不要只改句子不锁术语、不对对应链。用户点名方法名或说“完整润色这一节 / 一项成果”时，走 `section/0-work.md`，不要只改光标所在那一个 `\subsection`。封面、参考文献本 skill 不覆盖。

写摘要 / 绪论 / 相关工作 / 工作章 / 结论之前，先确认研究框架已锁定（入口台账能填出各柱全称、每柱两点难点、每柱成果）。填不出：只读 [chapter/research-framework.md](chapter/research-framework.md)，并告知用户缺的是素材还是拍板，不要开始改 `.tex` 正文。

摘要回扣绪论锁词时：条件术语、对象句、整体难点、各柱章题须与当前稿台账同词；互为依据句与各柱具体难点不进摘要。相关工作章、结论回扣绪论锁词时，须与台账同词。

“写章引言”一律派到工作章引言，不要派到绪论。绪论只在用户明说第 1 章或“写绪论”时读取。

## 目录与级别

```
chapter/
  research-framework.md        研究框架与总体框架图（写正文之前）
  abstract.md                  中英文摘要（Frontmatter）
  introduction.md              第 1 章绪论
  related-work.md              国内外研究现状
  conclusion.md                总结与展望
  technical-chapter-intro.md   工作章 \section{引言}
  technical-chapter-prelim.md  工作章 \section{预备知识}
  technical-chapter-summary.md 工作章 \section{本章小结}
section/
  consistency.md               一项成果整节：术语锁、对应链、四小节前后一致
  0-work.md                    一项研究成果整节（四小节编排）
  1-motivation.md              \subsection{研究动机}
  2-method.md                  \subsection{方法设计}
  3-experiment.md              \subsection{实验分析}
  4-summary.md                 \subsection{本节小结}
polish/
  academic-zh.md               中文学术润色
```

工作章（绪论与相关工作之后、结论之前的技术章）：

```
\chapter
  \section{引言}                 → technical-chapter-intro
  \section{预备知识}             → technical-chapter-prelim
  \section{工作一/二/三}         → 0-work（点名整节时）
    \subsection{研究动机}        → 1-motivation
    \subsection{方法设计}        → 2-method
    \subsection{实验分析}        → 3-experiment
    \subsection{本节小结}        → 4-summary
  \section{本章小结}             → technical-chapter-summary
```

柱数、每柱工作数以已锁框架为准，不必固定为四柱三项。体裁没有工作章或相关工作章时，跳过对应派发，不要补写空章。

## 台账字段（内部草稿，不写入 `.tex`）

写任何全书层文字之前，从**已锁框架**与当前稿抽出下表。表建不成，回到 [chapter/research-framework.md](chapter/research-framework.md)，不要开始改句子。本 skill **不预填取值**。

| 字段 | 要求 |
|---|---|
| 总命题 / 目标 | 含锁定条件 + 研究目标；章首与研究问题开篇同词 |
| 研究对象 | 1 句；做法不是对象 |
| 做法 | 对对象做的事（当前稿原词，不要写成研究对象） |
| 主线 | 各柱短名的顺序（如 A → B → C） |
| 各柱中名 / 短名 / 全称 | 三层不得叠床；全称 = 工作章章题 |
| 整体难点 | 每柱一个情况名；用于背景 enumerate、研究问题标题 |
| 具体难点 | 每柱两点 `\textit{}` 短语；用于“缓解”、工作章引言 |
| 机制词 | 与研究内容、章引言三项工作句同一套 |
| 每柱成果 | 中文名 2–3 项；台账写清分打哪一难点 |
| 框架布局 | 横跨支撑 + 并列顺承 / 全并列；与总体框架图同构 |
| 互为依据 / 关系句 | 若当前稿有，全书原词；摘要默认不写；框图默认不画双向箭 |
| 应用名 | 章首可用缩写，研究意义 / 结论用全称 |
| 封面题目 | 正文只轻呼应，不写“方法研究”四字（若题目含此） |

## 行文通则（凡写必守）

凡写入 `.tex` 正文，不论读哪一份子文件，均遵守下列八条。

1. **逐句换行。** `.tex` 源码里一句一行：句末 `。！？` 后换行。段与段之间空一行。不要把整段挤成一行。
2. **一句一意，勿写过长单句。** 一句只承载一个判断或一步因果。多层“的”字定语、一串分号、一句里塞两个“从而”的，拆成两句。
3. **正文不用破折号等 AI 标记。** 禁止 `——`、`--` 做插入语或举例。举例用“……，例如……”。不要用“转而”起句。`综上所述`、`值得注意的是` 是常见学术过渡，不是 AI 标记；原文有则保留，不要为去味而删，也不要为去味而主动插入；子文件已规定段首时不得用它们替换既定段首。连字符仅保留在英文复合词与数学式中。
4. **段首连词要有、且稳定。** 每段用段首句或段首连词标明本段功能。各部分的具体骨架以该子文件为准。润色时不得改写既定段首。写/润相关工作章时，related-work 的四段骨架优先于 polish 的去同构。未规定骨架时，用“然而 / 因此 / 此外 / 首先”一类学术连词起段，不要无连词起段，也不要用“据此提出”“针对上述问题”连用两次。
5. **正文不用直角引号。** 禁止 `「」`、`『』`。举例、引用、强调、概念对举用中文双引号“……”或单引号‘……’；术语、专名、代码用 `\emph{}` / `\texttt{}`。
6. **“有效性”宾语须落到机制或具体能力。** 禁止“验证了本方法/本章方法的有效性”“实验结果证明了有效性”。允许“说明/验证了……的有效性”当且仅当宾语是具体机制。章引言末句落到验证场景或具体能力，不要空写“验证了方法的有效性”。
7. **图表字号略小于正文，至少为 `\small`。** 图题、表题已由模板设为 `\small`；表内文字在 `table` / `table*` / `sidewaystable` 环境开头写 `\small`（列多时可 `\footnotesize`）。子图题同样不大于 `\small`。TikZ / pgfplots 图内文字用 `\small` 或更小；外嵌 PDF 的图内字体在绘图源中控制。
8. **整节术语同一套；成果经方法机制钩回难点与现实需求。** 一项成果四个 `\subsection` 的任务名、难点现象词、模块名、机制作用词不得换一套近义说法。该项成果须能经方法的关键变换追溯到章引言的难点，难点须能追溯到章引言的现实需求。对应靠机制，不靠“回应挑战一”这类编号。同章多项工作共同覆盖该章难点；单节写清本项位置，不侵占另一项的关键变换。细则见 [section/consistency.md](section/consistency.md)。

## 三级不要混

- **研究框架**（`chapter/research-framework.md`）是写正文之前的手工锁定：柱、难点两点、成果归属、总体框架图。不是绪论研究内容节，也不代替工作章方法。
- **摘要**（`chapter/abstract.md`）是全书代理：总述漏斗 + 按柱分条（短方面名 + 开展章题 + 提出—通过—有效提升了），不报数字、不写展望、条内不写针对具体难点。不是绪论缩写，也不是结论收口。两块结构：总述漏斗 + 按柱分条（学结构、不搬范例任务名）。
- **绪论**（`chapter/introduction.md`）是全书漏斗：研究背景、研究意义分成两个 `\section`，其后为研究问题 / 研究内容与贡献 / 论文组织结构。不是工作章的两点难点 + 若干项工作。缺口写进研究问题各问，不要在绪论展开谱系。锁词以当前稿台账为准。
- **相关工作**（`chapter/related-work.md`）是方法谱系与空白，不是绪论研究问题的扩写，也不是工作章预备知识。每个小节四段；相对绪论研究问题必须新增分类轴或代表机制。第二、三段段首选“第一类工作 / 另一类工作”或“在 A 方面 / 在 B 方面”，同一小节不混。第四段可用“本文开展【研究内容名】”，仍禁止成果简称。
- **工作章引言**（`technical-chapter-intro.md`）是该章路线图，在 `\section{引言}`。各章第一句都不承上，从现实需求起笔。
- **研究动机**（`section/1-motivation.md`）是单节开头（起承转合），在 `\subsection{研究动机}`。不要把“当关注点从 X 转向 Y”套进节动机。
- **本节小结**收一节；**本章小结**收一章；**结论**两节收全书（工作总结 / 未来工作展望），不要与本章小结、摘要或绪论贡献清单混淆。摘要与绪论贡献不报数字；结论若点证据，口径以各章主表为准。

主语：章内用“本章 / 本节”，不用“我们”；“本文 / 本报告”用于摘要、绪论、结论，以及相关工作各小节第四段“本文开展【研究内容名】”。
