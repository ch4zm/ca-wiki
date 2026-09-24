# ca-wiki

A knowledge base on cellular automata: rules, patterns, the people behind them, core
concepts, and analyses that tie sources together. It grows with every paper, web page,
book, or transcript fed into it. It is maintained by the
[`wiki-skills`](https://github.com/kfchou/wiki-skills) Claude Code plugin, following
[Karpathy's LLM Wiki pattern](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f).

The wiki is **not** meant to be hand-edited. You work with it through the `wiki-*` skills
in Claude Code.

## Quick start: fresh clone to first question

1. Install [Claude Code](https://claude.ai/code) and [`uv`](https://docs.astral.sh/uv/).
2. Install the plugin, from any directory in Claude Code:
   ```
   /plugin marketplace add kfchou/wiki-skills
   /plugin install wiki-skills@wiki-skills
   ```
   (To remove: `/plugin uninstall wiki-skills@wiki-skills` then
   `/plugin marketplace remove wiki-skills`.)
3. Re-arm the pre-commit hooks. `core.hooksPath` is repo-local config and does not survive
   a clone:
   ```bash
   git config core.hooksPath bin/hooks
   ```
4. Open Claude Code **in this repo** (the skills find the wiki via `SCHEMA.md`) and use the
   skills: `wiki-query` to ask questions, `wiki-ingest` to add a source, `wiki-lint` to
   health-check.

## Skills

- `wiki-init` - bootstrap a new wiki (already done here)
- `wiki-ingest` - add a source (paper, URL, file, transcript); one ingest may touch 10-15 pages
- `wiki-query` - answer a question from the wiki's pages, not general knowledge
- `wiki-lint` - find contradictions, orphans, broken links, stale claims, coverage gaps
- `wiki-audit` - fact-check one page's footnotes against its cited sources
- `wiki-update` - revise pages when knowledge changes or you want a direct edit
- `wiki-merge` - merge two pages for the same concept, or split an overloaded page

## Layout

```
ca-wiki/
├── SCHEMA.md         ← conventions + absolute path (how the skills find the wiki)
├── config/
│   └── link-style.md ← cross-reference emit/parse rules
├── bin/              ← helper scripts (index, log, lint, contradiction gate)
│   └── hooks/pre-commit
├── raw/              ← immutable source documents
├── wiki/
│   ├── index.md      ← GENERATED, gitignored; run bin/generate-index.py
│   ├── overview.md   ← evolving synthesis
│   └── pages/        ← all pages, flat, slug-named
└── assets/           ← images, PDFs, attachments
```

## Conventions

- `raw/` is immutable.
- Cross-references use markdown link style; see [`config/link-style.md`](config/link-style.md).
- `wiki/index.md` is generated: `python bin/generate-index.py`.
- The git history is the operation log: `python bin/render-log.py`.
- Pages carry citations, not revision history; see **Page Discipline** in [`SCHEMA.md`](SCHEMA.md).
- Index categories: Sources, Rules, Patterns, People, Concepts, Analyses.

## Help

- Skill or plugin issues: the [`wiki-skills`](https://github.com/kfchou/wiki-skills) repo.
- Authoritative conventions: [`SCHEMA.md`](SCHEMA.md).
