# Roadmap — Geniale-Gemini-prompts

**Stand:** 2026-09-06  
**Zielbild:** ein Toolbox-Repo — Architect Prime (Compiler) plus kanonische Gems.  
**Schwester-Repo:** [grapefruit89/gemini-Gem](https://github.com/grapefruit89/gemini-Gem)

Audit und Begründung: [`AUDIT.md`](AUDIT.md).

## Status

| Phase | Inhalt | Status |
| :---: | :--- | :--- |
| 0 | Einstiegsdoku, Audit, Broken Refs | **erledigt** |
| 1 | kebab-case, Endungen, Duplikate nach `archive/` | **erledigt** (Branch `kebab-case-paths`) |
| 1b | Inhalte aus `gemini-Gem` übernehmen | offen |
| 2 | Few-Shots, Frontmatter, usage-Beispiel | offen |
| 3 | CONTRIBUTING, Templates, optionales Release | offen |

Phase-1-Mapping liegt in der historischen Fassung auf `main` und ist auf diesem Branch umgesetzt:

- `The Prompt Forge/` → `forge/`
- `Chat Refactor/` → `pipelines/chat-refactor/`
- kanonische Gems → `gems/`
- Duplikate/Legacy → `archive/`

Noch auf den alten Pfaden (vollständiger Inhalt, API-Limit):

- `Lifecoach/Ikigai.xml` (Kopie `gems/lifecoach-ikigai.xml` ist ein Stub — vor Merge lokal `git mv`)
- `GeminiGEM/U-Block Light Filter Helper` (Kopie `archive/gems-legacy/ublock-lite-helper.xml` ist ein Stub)

Nächster Schritt: Phase 1b, danach Tag `v0.1.0`.
