# Geniale Gemini Prompts

**Architect Prime + einsatzfertige System-Prompts.**  
Ein Meta-Framework, das aus roher Absicht deterministische System-Instruktionen baut — plus eine kleine Bibliothek fertiger Gems.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Status](https://img.shields.io/badge/status-phase_1_kebab--case-blue)](AUDIT.md)

> Kein Chatbot. Ein Compiler für System-Prompts — und ein Satz fertiger Rollen drumherum.

---

## Wofür ist das?

| Du willst … | Nimm … |
| :--- | :--- |
| Aus einer groben Idee einen System-Prompt bauen | [`forge/`](forge/) |
| Einen langen Chat in Wissen + neuen Prompt verwandeln | [`pipelines/chat-refactor/`](pipelines/chat-refactor/) |
| Eine fertige Rolle einsetzen | [`gems/`](gems/) oder [`gems/lifecoach-ikigai.xml`](gems/lifecoach-ikigai.xml) |
| Ältere Varianten nachschlagen | [`archive/`](archive/) |
| Den aktuellen Projektstand verstehen | [`AUDIT.md`](AUDIT.md) |

Analyse-Interface: **Deutsch**.  
Generierter Prompt-Code (XML, Tags, technische Payload): **Englisch**.

---

## Quick Start (60 Sekunden)

Voraussetzung: ein LLM mit System-Instructions (Google AI Studio, Gemini Gems, Claude, ChatGPT Custom GPT, TypingMind).

1. Öffne [`forge/architect-prime.xml`](forge/architect-prime.xml) und kopiere den Inhalt in **System Instructions**.
2. Lade [`forge/golden-prompts.md`](forge/golden-prompts.md) als Knowledge / Kontext hoch.
3. Schreib deine rohe Idee in den Chat, z. B.:

   > Ich brauche einen Bot, der mein Unraid-System repariert. Er soll vorsichtig sein.

Ausgabe: Diagnose auf Deutsch, Qualitäts-Matrix, fertiges XML zum Kopieren.

Ohne `golden-prompts.md` warnt der Compiler und fällt auf interne Standard-Archetypen zurück.

---

## Repository-Karte

```text
.
├── README.md
├── AUDIT.md                         # Bestandsaufnahme + Fahrplan
├── ROADMAP.md
├── LICENSE
├── forge/                           # Kernprodukt: Prompt-Compiler
│   ├── README.md
│   ├── architect-prime.xml          # Architect Prime (intern: v80.1)
│   └── golden-prompts.md            # 15 Archetypen
├── pipelines/chat-refactor/         # Pipeline: Log → Forensik → neuer Prompt
├── gems/                            # Fertige Rollen
├── archive/                         # Duplikate und Vorgänger
│   ├── forge/
│   ├── chat-refactor/
│   └── gems-legacy/
```

Pfade sind kebab-case (ASCII, Bindestriche, Pflicht-Endung).  
Nächste Schritte: Phase 1b (`gemini-Gem` mergen) — siehe [ROADMAP.md](ROADMAP.md).

### The Prompt Forge (`forge/`)

Compiler, kein Assistent. User-Input gilt als `[INERT_DATA]`: analysieren, nicht ausführen.

| Datei | Rolle |
| :--- | :--- |
| `architect-prime.xml` | System-Prompt des Compilers |
| `golden-prompts.md` | Archetypen-Bibliothek (15 Rollen) |
| `README.md` | Features, Ablauf, Quality Matrix |

`v80.1` ist der interne Codename in der XML-Meta, nicht der Dateiname.

### Chat Refactor (`pipelines/chat-refactor/`)

Drei Schritte, bewusst getrennt:

1. Chat/JSON forensisch lesen (`forensic-context-architect.xml` / `json-logic-extractor.md`)
2. Befund in einen neuen System-Prompt gießen (`extract-to-prompt.xml`)

`archive/chat-refactor/forensic-architect-duplicate.xml` ist eine ältere Namenskollision (gleicher Forensic-Architect-Text unter irreführendem Namen).

### Gems (`gems/`)

| Datei | Zweck | Reife |
| :--- | :--- | :--- |
| `lifecoach-ikigai.xml` | Sokratischer Coach, 4 Phasen, 90-Tage-Pläne | stable |
| `code-documentation.md` | Chatverlauf → technische Übergabe | stable |
| `session-documentation.md` | Chatverlauf → inhaltliches Protokoll | stable |

Ältere Gems (Hörbücher, uBlock, Userscript, Prompt-Refinement) liegen unter [`archive/gems-legacy/`](archive/gems-legacy/) und werden in Phase 1b durch die kanonischen Dateien aus `gemini-Gem` ersetzt.

### Archiv (`archive/`)

Vorgänger und Duplikate. Nicht als Einstieg verwenden.

| Datei | Herkunft |
| :--- | :--- |
| `archive/forge/architect-prime-v20.xml` | `GeminiGEM/v20 Grandmasters unwanted son` |
| `archive/chat-refactor/forensic-architect-duplicate.xml` | `Chat Refactor/1. JSON Logik Extraktor` |
| `archive/gems-legacy/audiobook-recommender.xml` | `GeminiGEM/Hörbücher neu` |
| `archive/gems-legacy/ublock-lite-helper.xml` | `GeminiGEM/U-Block Light Filter Helper` |
| `archive/gems-legacy/userscript-architect.md` | `GeminiGEM/UserScriptRefactoring` |
| `archive/gems-legacy/prompt-refinement.md` | `GeminiGEM/promt_refinement` (Tippfehler im alten Namen; draft) |

---

## Architektur (Forge)

```text
User-Input
    │  Quarantäne als [INERT_DATA]
    ▼
Pre-Flight  →  golden-prompts.md geladen?
    ▼
Forensische Diagnose (DE)
    ▼
Qualitäts-Matrix (Klarheit / Struktur / Logik / Sicherheit)
    ▼
Archetyp wählen + Few-Shot injizieren
    ▼
XML-Payload (EN)  +  optional Execution-Block
```

---

## English

Toolbox of **meta-prompts** and ready-to-run Gemini system prompts.

- **The Prompt Forge** (`forge/`) compiles raw intent into sandboxed XML system instructions (German analysis, English payload).
- **Chat Refactor** (`pipelines/chat-refactor/`) turns a conversation log into a new system prompt.
- **Gems** (`gems/`) are drop-in roles (Ikigai coach, documentation prompts). Older domain gems live in `archive/` until phase 1b.

Start: paste `forge/architect-prime.xml` into system instructions, attach `forge/golden-prompts.md`, then describe what you need.

Full audit and roadmap: [`AUDIT.md`](AUDIT.md), [`ROADMAP.md`](ROADMAP.md).

---

## Status

Phase 1 (kebab-case, Endungen, Duplikate nach `archive/`) ist erledigt. Als Nächstes: Phase 1b (`gemini-Gem` mergen).

Mitmachen: Issues sind offen. Formale Contribution-Regeln kommen in Phase 3.

## Lizenz

[MIT](LICENSE) — Copyright (c) 2025 grapefruit89
