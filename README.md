# 个人知识库启动包

这是一套基于 Obsidian + AI 的个人知识库维护模板。它的目标不是替你一次性整理所有资料，而是给 AI 一套稳定规则，让它在你持续写作、阅读和复盘时，帮你维护索引、标签、双链、概念页和维护日志。

## 这次更新

当前包封装了新版 `kb-organize` Skill：

- Codex 标准路径：`.agents/skills/kb-organize/`
- Claude Code 标准路径：`.claude/skills/kb-organize/`
- 兼容旧启动包路径：`00_schema/SKILL.md`
- 新增 resolver 分流规则：`00_schema/references/resolver.md`
- 新增私有同步策略：`00_schema/references/sync-policy.md`
- 新增 inbox、维护记录、周度维护、README 稳定化和迁移 dry-run 规则

## 目录结构

```text
.
├── AGENTS.md
├── CLAUDE.md
├── .agents/
│   └── skills/
│       └── kb-organize/
│           ├── SKILL.md
│           ├── agents/openai.yaml
│           └── references/
├── .claude/
│   └── skills/
│       └── kb-organize/
│           ├── SKILL.md
│           └── references/
├── 00_schema/
│   ├── AGENTS.md
│   ├── SKILL.md
│   └── references/
├── inbox/
│   └── README.md
├── 概念/
│   └── 概念示例_你的核心主题.md
├── 维护记录/
│   └── templates/
├── index.md
├── sources.md
└── log.md
```

## 快速开始

1. 用 Obsidian 打开这个文件夹。
2. 根据你的业务和知识领域，修改 `AGENTS.md` 中的占位说明。
3. 对 Codex 或 Claude Code 说：`使用 $kb-organize 帮我维护这个知识库。`
4. 新材料归档前，先判断来源、用途、隐私和事实风险；不确定的材料先放入 `inbox/`。
5. 外部素材原文默认只读，提炼后的洞察再进入概念页、索引或你自己的原创内容。

## 核心原则

- 人负责判断什么值得记，AI 负责维护结构。
- 概念页是长期认知的编译层，不是原始资料堆放处。
- `index.md` 是总入口，`sources.md` 是外部来源入口，`log.md` 是追加式维护记录。
- 私有知识库默认不需要 GitHub 同步；如果要公开，请先做隐私扫描和脱敏。
- 涉及客户、合同、财务、医疗、保单、证件、联系方式等敏感信息时，不进入公共索引或公开仓库。

## License

MIT License
