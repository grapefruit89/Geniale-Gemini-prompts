# Roadmap — Geniale-Gemini-prompts

**Stand:** 2026-09-05  
**Zielbild:** ein Toolbox-Repo — Architect Prime (Compiler) plus kanonische Gems.  
**Schwester-Repo:** [grapefruit89/gemini-Gem](https://github.com/grapefruit89/gemini-Gem)

Audit und Begründung: [`AUDIT.md`](AUDIT.md).

---

## Prinzipien

1. Ein Produkt vorne (`forge/`), fertige Rollen daneben (`gems/`), Historie hinten (`archive/`).
2. Pfade in kebab-case: klein, ASCII, Bindestriche, Pflicht-Endung `.md` / `.xml` / `.json`.
3. Pro Rolle eine kanonische Datei. Ältere Varianten nach `archive/`, nicht parallel bewerben.
4. Persönliche Knowledge-Daten (Leselisten-URLs, Weinkeller) nicht unkommentiert als „Beispiel“ verkaufen.
5. `gemini-Gem` nach dem Merge nicht löschen — einfrieren und auf dieses Repo zeigen.

Positionierung (Vorschlag, noch offen): **B — Toolbox**  
Forge ist der Hook, Gems sind der Grund zum Klonen. Repo-Name bleibt.

---

## Status

| Phase | Inhalt | Status |
| :---: | :--- | :--- |
| 0 | Einstiegsdoku, Audit, Broken Refs | **erledigt** (2026-09-05, `e27a82e`) |
| 1 | kebab-case, Endungen, Duplikate nach `archive/` | offen |
| 1b | Inhalte aus `gemini-Gem` übernehmen | offen — wartet auf 3 Entscheidungen |
| 2 | Few-Shots, Frontmatter, usage-Beispiel | offen |
| 3 | CONTRIBUTING, Templates, optionales Release | offen |
| — | Website, App, CI, 20 neue Archetypen | bewusst nicht |

---

## Phase 0 — erledigt

- [`AUDIT.md`](AUDIT.md) im Root
- Root-[`README.md`](README.md) mit Quick Start und Repository-Karte
- Forge-README zeigt auf die echte Datei `v1.0 The Prompt Forge` (nicht auf das nicht existente `v80.1 Singularity Core.xml`)
- Platzhalter-READMEs in `Chat Refactor`, `GeminiGEM`, `Lifecoach` ersetzt

Nicht Teil von Phase 0 (kein Connector dafür): GitHub-About und Topics. Einmal manuell setzen:

```text
Description:
Architect Prime: Compiler für System-Prompts plus fertige Gemini-Gems (DE-Analyse, EN-XML).

Topics:
prompt-engineering  gemini  system-prompts  xml  meta-prompting  llm
```

---

## Phase 1 — Struktur (kebab-case)

Keine Inhaltsänderung, nur Pfade. Eine Konvention: Bindestrich, keine Leerzeichen, keine Umlaute in Dateinamen.

### Mapping

| Jetzt | Ziel |
| :--- | :--- |
| `The Prompt Forge/` | `forge/` |
| `The Prompt Forge/v1.0 The Prompt Forge` | `forge/architect-prime.xml` |
| `The Prompt Forge/golden_prompts.md` | `forge/golden-prompts.md` |
| `The Prompt Forge/readme.md` | `forge/README.md` |
| `Chat Refactor/` | `pipelines/chat-refactor/` |
| `1. Lead Forensic Context Architect` | `pipelines/chat-refactor/forensic-context-architect.xml` |
| `2. Extract to new Prompt` | `pipelines/chat-refactor/extract-to-prompt.xml` |
| `JSON-Logik-Extraktor` | `pipelines/chat-refactor/json-logic-extractor.md` |
| `1. JSON Logik Extraktor` | `archive/chat-refactor/forensic-architect-duplicate.xml` |
| `GeminiGEM/` | `gems/` (nach 1b die neueren Dateien aus `gemini-Gem`) |
| `Hörbücher neu` | `archive/gems-legacy/audiobook-recommender.xml` |
| `U-Block Light Filter Helper` | `archive/gems-legacy/ublock-lite-helper.xml` |
| `UserScriptRefactoring` | `archive/gems-legacy/userscript-architect.md` |
| `promt_refinement` | `archive/gems-legacy/prompt-refinement.md` |
| `v20  Grandmasters unwanted son` | `archive/forge/architect-prime-v20.xml` |
| `Lifecoach/Ikigai.xml` | `gems/lifecoach-ikigai.xml` |
| `Code Dokumentation` | `gems/code-documentation.md` |
| `Normale Dokumentation` | `gems/session-documentation.md` |

### Zielbaum nach Phase 1 + 1b

```text
.
├── README.md
├── AUDIT.md
├── ROADMAP.md
├── LICENSE
├── CHANGELOG.md
├── docs/
│   └── usage.md
├── forge/
│   ├── README.md
│   ├── architect-prime.xml
│   ├── golden-prompts.md
│   └── meta-gem-template.md
├── pipelines/
│   └── chat-refactor/
├── gems/
│   ├── README.md
│   ├── audiobook-recommender.md
│   ├── ublock-lite-helper.md
│   ├── userscript-architect.md
│   ├── kleinanzeigen.md
│   ├── wine-sommelier.md
│   ├── lifecoach-ikigai.xml
│   ├── code-documentation.md
│   ├── session-documentation.md
│   └── examples/
└── archive/
    ├── forge/
    ├── chat-refactor/
    └── gems-legacy/
```

Branch-Vorschlag: `refactor/v0.1`, danach Merge auf `main` und Tag `v0.1.0`.

---

## Phase 1b — Merge von `gemini-Gem`

[gemini-Gem](https://github.com/grapefruit89/gemini-Gem) ist das neuere Gems-Repo (2026-08-08): kebab-case, 5-Säulen-Format (Persona, Task, Context, Examples, Format), Kopieranleitung.  
Dieses Repo hat dieselben Themen oft nur als ältere XML-Skizze plus das Framework.

Nicht zwei Repos parallel pflegen. `gemini-Gem` wird Quelle der Wahrheit für fertige Gems, dieses Repo bleibt das Dach.

### Inventar `gemini-Gem`

| Datei | Bedeutung | Ziel hier |
| :--- | :--- | :--- |
| `audiobook-gem-v20.md` | Experience-Dimensionen, 6–8 Tipps | `gems/audiobook-recommender.md` (kanonisch) |
| `audiobook-gem-v10.md` | Vorgänger | `archive/gems-legacy/audiobook-gem-v10.md` |
| `ublock-gem-v10.md` | uBO Lite Architect | `gems/ublock-lite-helper.md` (kanonisch) |
| `userscript-gem-v10.md` | SPA / Tampermonkey | `gems/userscript-architect.md` (kanonisch) |
| `kleinanzeigen-gem-v15.md` | nur dort | `gems/kleinanzeigen.md` |
| `wine-gem-v10.md` | nur dort | `gems/wine-sommelier.md` |
| `Mein_Weinkeller.json` | persönliche Kellerdaten | siehe Entscheidungen |
| `meta-gem-template.md` | universelle Vorlage + verify-Skript | `forge/meta-gem-template.md` |

### Gewinner bei Überlapp

| Thema | Kanonisch | Alte Datei in diesem Repo |
| :--- | :--- | :--- |
| Hörbücher | `audiobook-gem-v20.md` | `GeminiGEM/Hörbücher neu` → archive |
| uBlock | `ublock-gem-v10.md` | `U-Block Light Filter Helper` → archive |
| Userscript | `userscript-gem-v10.md` | `UserScriptRefactoring` → archive |

Kein `git subtree`. Acht Dateien: kopieren, Herkunft in der Datei oder in `CHANGELOG.md` nennen.

Nach dem Copy: in `gemini-Gem` eine README mit Verweis auf dieses Repo, Repo dort nicht löschen.

### Persönliche Daten (Blocker)

In `gemini-Gem` stecken Arbeitsdaten, keine generischen Demos:

- StoryGraph `app.thestorygraph.com/books-read/mbaum`
- Hardcover `hardcover.app/@m7c5/books/read`
- `Mein_Weinkeller.json` (konkrete Flaschen)

Solange Entscheidung 1 offen ist, kein Push dieser Dateien.

---

## Offene Entscheidungen (vor 1 / 1b)

1. **Merge-Modus für persönliche Dateien**
   - **A** öffentlich: URLs → Platzhalter, Weinkeller als `gems/examples/wine-cellar.sample.json`
   - **B** 1:1 inkl. URLs und Keller, im README als persönliche Knowledge-Files markiert
2. **Wann:** jetzt auf `main` oder gebündelt mit Phase 1 auf `refactor/v0.1`
3. **`gemini-Gem` danach:** nur README-Verweis, oder zusätzlich GitHub-Archive

Default, wenn „mach“ ohne Feintuning kommt: **A + Branch `refactor/v0.1` + gemini-Gem bleibt live mit Verweis.**

---

## Phase 2 — Inhalt härten

- Few-Shot-Platzhalter in `golden-prompts.md` durch echte Beispiele ersetzen (mindestens Coding, DevOps, SRE, Meta).
- `prompt-refinement` fertigmachen oder nur im Archiv lassen.
- Frontmatter je Prompt: Zweck, Modell, Input, Output, Status (`stable` / `draft` / `archived`).
- Ein durchgängiges Forge-Beispiel unter `forge/examples/`.
- `docs/usage.md`: AI Studio / Gemini Gem, System Instructions + Knowledge-Upload.

---

## Phase 3 — Außenwirkung

- `CONTRIBUTING.md` (Namenskonvention, wie ein Gem landet).
- Issue-Templates: `new-gem`, `improve-archetype`.
- Release `v0.1.0` mit Notes.
- Zweisprachige README erst, wenn der deutsche Einstieg sitzt.
- `dev`-Branch erst bei PRs oder riskanten Umbauten.

---

## Bewusst nicht

- GitHub Pages / Marketing-Site
- Prompt-Compiler als App
- Massenhaft neue Archetypen vor der Struktur
- Repo-Rename vor fester Positionierung
- CI, Tests, Docker (kein Anwendungscode)

---

## Reihenfolge der nächsten Arbeit

1. Entscheidungen 1–3 (oben) treffen.
2. Phase 1 auf `refactor/v0.1` (Moves + archive).
3. Phase 1b (Copy aus `gemini-Gem`, README dort).
4. Root-README und `gems/README.md` auf die neuen Pfade ziehen.
5. Tag `v0.1.0`.
6. Phase 2 nur an kanonischen Dateien, nicht an Archivkopien.
