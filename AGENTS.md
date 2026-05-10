# Knowledge Base Rules

This folder is an Obsidian-compatible personal knowledge base starter kit maintained with AI assistance.

## Canonical Structure

- `index.md` is the main knowledge index.
- `sources.md` is the external source index.
- `log.md` is the append-only maintenance log.
- `inbox/` is a temporary holding area for unclear material.
- `00_schema/` stores rules, templates, tag registries, and routing references.
- `概念/` stores concept pages.
- `维护记录/` stores maintenance reports, dry-runs, validations, and templates.

## Operating Rules

- Use `.agents/skills/kb-organize/SKILL.md` for ingest, backlink maintenance, index updates, lint, weekly maintenance, and migration workflows.
- Preserve Obsidian wikilinks in the form `[[...]]`.
- Use Vault-relative paths. Do not write local absolute paths, local usernames, device names, or cloud-drive absolute paths into reusable knowledge content.
- If source, purpose, privacy, or destination is unclear, put the material under `inbox/` and mark it `待人工确认`.
- Do not delete user-authored content or concept-page history.
- Concept page timelines are append-only unless the user explicitly requests historical cleanup.

## Privacy and Sync

- This starter kit is designed for a private local knowledge base by default.
- GitHub is optional, not the default sync method.
- Before publishing any real Vault to GitHub, scan for customer information, contracts, policy details, financial data, medical records, IDs, phone numbers, addresses, and private schedules.
- If conflict files, duplicate sync files, or filenames containing `conflict` appear, report them and do not auto-merge.

## External Materials

- External source material should stay in a clearly separated source area.
- Do not mix external references into user-authored original content without a clear source boundary.
- Allowed operations for external materials: read, summarize, index, cite, and link.
- Do not directly edit original external articles or source documents.

## Maintenance Output

- After each maintenance task, generate a result report or operation log under `维护记录/`.
- Do not place maintenance reports in the Vault root.
- Record important changes in `log.md` using append-only entries.

