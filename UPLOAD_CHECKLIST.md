# GitHub 上传检查清单

## 上传前

- 确认只上传本目录内容，不上传你的私人 Obsidian Vault。
- 确认没有客户、合同、保单、证件、联系方式、财务账户、医疗记录或私人日程。
- 确认没有本机绝对路径、用户名、设备名、NAS 路径或云盘路径。
- 确认 `.agents/skills/kb-organize/SKILL.md` 是 Codex 使用的主 Skill。
- 确认 `.claude/skills/kb-organize/SKILL.md` 是 Claude Code 使用的主 Skill。
- 确认 `CLAUDE.md` 只包含通用项目指令，不包含私人 Vault 信息。
- 确认 `00_schema/SKILL.md` 只作为旧启动包兼容入口。

## 推荐提交信息

```text
Update kb-organize public starter skill to v0.4
```

## 推荐发布说明

```text
v0.4-public-starter

- Add Codex-standard .agents/skills/kb-organize package.
- Add Claude Code-standard .claude/skills/kb-organize package and CLAUDE.md.
- Keep 00_schema/SKILL.md as a compatibility entry.
- Add resolver, sync policy, privacy guardrails, inbox workflow, weekly maintenance, lint, README stabilization, and maintenance-report workflows.
- Add public starter templates with no private Vault content.
```
