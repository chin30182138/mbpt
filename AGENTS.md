# Knowledge Base Operating Rules

This workspace is an LLM-maintained wiki for MBPT 神獸人格學. Follow these rules whenever you ingest sources, answer questions, or maintain the wiki.

## Architecture

- `raw/` is the source layer. Treat files here as immutable evidence. Read them, cite them, but do not rewrite them unless the user explicitly asks.
- `wiki/` is the compiled knowledge layer. You own maintenance here: create pages, update links, revise summaries, mark contradictions, and keep synthesis current.
- `templates/` stores page formats. Use them when creating new wiki pages.
- `wiki/index.md` is the content map. Read it before answering knowledge-base questions and update it after every meaningful wiki edit.
- `wiki/log.md` is the chronological record. Append one entry per ingest, query worth preserving, or lint pass.

## Page Conventions

- Write wiki pages in Traditional Chinese unless the source is primarily English and a technical term is clearer in English.
- Use Obsidian-style links: `[[Page Name]]`.
- Prefer descriptive filenames with spaces allowed.
- Add YAML frontmatter to wiki pages with `type`, `created`, `updated`, `status`, `tags`, and `sources`.
- Keep claims traceable. When a claim comes from a source, mention the source page or raw path.
- If sources disagree, add a conflict section and explain the disagreement.

## Domain Notes

- Treat MBPT 神獸人格學 as a living framework.
- Distinguish clearly between evidence, interpretation, and naming/design choices.
- Preserve naming consistency for 神獸類型 and related model pages.
