---
name: kb-organize
description: Use this skill when organizing an Obsidian knowledge base, ingesting Markdown notes, routing new materials, updating concept pages, maintaining backlinks, updating index/sources/log files, linting a Vault, creating README navigation pages, planning root migrations, or generating weekly knowledge-base maintenance reports.
---

# Knowledge Base Organizer

Use this skill for Obsidian knowledge-base maintenance.

## Core Model

Maintain a four-layer knowledge base:

```text
Raw material / external sources -> Concept pages -> Indexes -> Rules
```

- Raw material is preserved with clear source boundaries.
- Concept pages synthesize long-term judgments and append timelines.
- `index.md` and `sources.md` provide stable navigation.
- `AGENTS.md`, `00_schema/`, and this Skill define operating rules.

## Required Safety Rules

- If the user asks for read-only audit, do not write files.
- Before large batch writes, output a plan with affected paths, estimated write count, backlink impact, rollback approach, and risk points. Wait for confirmation.
- Preserve Obsidian wikilinks, especially `[[index]]`, `[[sources]]`, and `[[概念/...]]`.
- Use Vault-relative paths. Do not write local absolute paths, usernames, device names, or cloud/NAS absolute paths into reusable knowledge content.
- If source, purpose, privacy, or destination is unclear, route material to `inbox/` and mark it `待人工确认`.
- Do not delete user-authored content or concept-page history unless explicitly requested.
- Concept page timelines are append-only unless the user explicitly asks for historical cleanup.
- If conflict files, duplicate sync files, or filenames containing `conflict` appear, report them and do not auto-merge.
- For customer, contract, policy, financial, medical, ID, contact, household, or private schedule information: redact, anonymize, skip, or keep it out of global indexes and public templates.
- For unstable factual claims such as product terms, prices, returns, regulations, medical claims, or company facts, require a source or write `待补充资料`.

## References

Read only what is needed:

- `references/resolver.md` - routing decision tree and destination rules.
- `references/sync-policy.md` - private sync, GitHub publishing, conflict, and privacy rules.
- `references/tag-taxonomy.md` - registered tags and tag rules.
- `references/templates.md` - frontmatter and page templates.
- `references/karpathy-llm-wiki.md` - local summary of the LLM Wiki method.

If the same references also exist under `00_schema/references/`, prefer the Vault-local version because the user may have customized it.

## Workflow: Resolver Check Before Ingest

1. Read root `AGENTS.md` and `index.md` when present.
2. Read `00_schema/references/resolver.md` or bundled `references/resolver.md`.
3. Identify source: user-authored, external reference, project document, personal record, maintenance artifact, or unclear.
4. Identify purpose: active content, concept synthesis, source navigation, project documentation, private record, maintenance report, or temporary intake.
5. Identify privacy and fact risk.
6. Choose destination using the resolver. If unclear, use `inbox/` and mark `待人工确认`.
7. Check for same-name files, semantic duplicates, and sync-conflict filenames before writing.

## Workflow: Single File Ingest

1. Read the target file only when allowed by privacy and scope.
2. Determine whether it is original content, external material, private record, or project document.
3. Add or merge frontmatter without overwriting user fields.
4. Add relevant `[[概念/...]]` and collection links when appropriate.
5. Update the relevant concept page, `index.md`, `sources.md`, and `log.md` only if this write scope is requested or confirmed.
6. Report changed files, tags used, links created, and unresolved decisions.

## Workflow: Folder Batch Organization

1. Inventory Markdown files and subfolders.
2. Sample representative files before proposing tags.
3. Separate knowledge content from external raw material and private records.
4. Check for conflict filenames and semantic duplicates.
5. For large batches, produce a plan and wait for confirmation.
6. Process in small staged batches.
7. Prefer README navigation and lightweight index updates over broad rewrites.

## Workflow: Concept Page Create/Update

1. Search existing `概念/` pages first.
2. Preserve existing structure and user-written judgments.
3. Update "当前判断" only when the user requests synthesis or enough evidence exists.
4. Append to "核心要点", "相关文档", and "时间线"; do not delete history.
5. Add backlinks from edited source pages only when write scope includes them.

## Workflow: Indexes and Logs

- `index.md`: keep content-oriented and stable; add one-line summaries for durable entries.
- `sources.md`: register external source collections; do not edit original external articles.
- `log.md`: append entries using `## [YYYY-MM-DD] type | title`.
- `维护记录/`: put dry-runs, execution reports, validations, and weekly maintenance reports here, not in the Vault root.

## Workflow: Backlink Completion

1. Search existing `[[...]]` patterns and likely concept mentions.
2. Prefer stable concept links under `[[概念/...]]`.
3. Avoid mass link changes without a plan.
4. Preserve aliases and link display text.
5. Validate with search after edits and report unresolved links.

## Workflow: Knowledge Base Lint

Check for:

- Missing frontmatter.
- Unregistered tags.
- Broken or suspicious wikilinks.
- Orphan pages with no useful inbound/outbound links.
- Concept pages missing current judgment, related documents, or timeline.
- Source collections not reflected in `sources.md`.
- New durable files not reflected in `index.md`.
- Absolute local filesystem paths or device-specific paths.
- Sync-conflict files.
- Sensitive information that should be redacted or skipped.
- Unstable factual claims missing sources.

For lint-only requests, produce findings and proposed fixes. Write only after confirmation.

## Workflow: Weekly Maintenance

1. Summarize new or changed Markdown files since the last log entry when possible.
2. Identify index/source/concept updates needed.
3. Identify stale concept pages, README gaps, missing backlinks, and suspicious links.
4. Check only filenames/frontmatter for privacy-sensitive or large raw-material directories unless the user explicitly names files.
5. Propose a small maintenance batch.
6. After confirmation or when the requested scope is already small, update affected pages and append `log.md`.
7. Generate a result report under `维护记录/weekly/`.
8. Report changed files, skipped items, and next questions.

