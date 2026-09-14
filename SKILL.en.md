# Chinese Research-Report Writing (English note)

> This file is a reading aid for [`SKILL.md`](SKILL.md). Agents must execute the Chinese `SKILL.md`; do not treat this note as the runtime skill.

| Field | Value |
| --- | --- |
| Name | `writing-report-skill-by-sheng` |
| Description | Draft, revise, or polish completed Chinese academic research reports (postdoc completion reports, theses, closing / progress / technical reports). Requires existing results and a user-locked research framework. Triggers include 研究报告, 出站报告, 学位论文, 结题报告, 摘要, 绪论, 相关工作, 结论. |
| License | MIT |
| Compatibility | Any agent that supports Agent Skills, including Cursor, Codex, and Claude Code |
| Version | 1.0.0 |
| Author | JiaweiSheng |

Write a report of **completed work**, not a proposal of planned work. Lock the framework first, then fill the ledger, then write sentences. Do not invent topics, method names, or numbers.

```text
user-locked pillars / challenges / results
  -> ledger terms from the current draft
    -> chapter / section dispatch
      -> Chinese academic polish
```

## Route the request

Load only the needed file. Unnamed files must not be read in full.

- Research framework and overall figure (before body text): [chapter/research-framework.md](chapter/research-framework.md)
- Abstract: [chapter/abstract.md](chapter/abstract.md)
- Introduction: [chapter/introduction.md](chapter/introduction.md)
- Related work: [chapter/related-work.md](chapter/related-work.md)
- Conclusion: [chapter/conclusion.md](chapter/conclusion.md)
- Technical-chapter intro / prelim / summary: [chapter/technical-chapter-intro.md](chapter/technical-chapter-intro.md), [chapter/technical-chapter-prelim.md](chapter/technical-chapter-prelim.md), [chapter/technical-chapter-summary.md](chapter/technical-chapter-summary.md)
- One result, four subsections: [section/0-work.md](section/0-work.md) plus [section/consistency.md](section/consistency.md)
- Chinese academic polish: [polish/academic-zh.md](polish/academic-zh.md)

Invoke this skill explicitly (`@` / `/writing-report-skill-by-sheng`). Do not assume it is already loaded.

## Portable packaging

`SKILL.md` keeps only portable frontmatter: `name`, `description`, `license`, `compatibility`, `metadata`. Cursor `disable-model-invocation`, Claude `user-invocable`, and Codex UI copy live in sidecar files.

| Agent | Extra files |
| --- | --- |
| Cursor | none beyond `SKILL.md` |
| Codex | `agents/openai.yaml`, `.codex-plugin/` |
| Claude Code | `agents/claude.yaml`, `.claude-plugin/` |
| Agent Skills | `.agents/plugins/` |

Install locally with `./scripts/install.sh`. Start a new chat after installation.
