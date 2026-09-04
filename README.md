# Geniale Gemini Prompts

**Architect Prime + einsatzfertige System-Prompts.**  
Ein Meta-Framework, das aus roher Absicht deterministische System-Instruktionen baut — plus eine kleine Bibliothek fertiger Gems.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Status](https://img.shields.io/badge/status-phase_0_docs-blue)](AUDIT.md)

> Kein Chatbot. Ein Compiler für System-Prompts — und ein Satz fertiger Rollen drumherum.

---

## Wofür ist das?

| Du willst … | Nimm … |
| :--- | :--- |
| Aus einer groben Idee einen System-Prompt bauen | [`The Prompt Forge`](The%20Prompt%20Forge/) |
| Einen langen Chat in Wissen + neuen Prompt verwandeln | [`Chat Refactor`](Chat%20Refactor/) |
| Eine fertige Rolle einsetzen | [`GeminiGEM`](GeminiGEM/) oder [`Lifecoach/Ikigai.xml`](Lifecoach/Ikigai.xml) |
| Den aktuellen Projektstand verstehen | [`AUDIT.md`](AUDIT.md) |

Analyse-Interface: **Deutsch**.  
Generierter Prompt-Code (XML, Tags, technische Payload): **Englisch**.

---

## Quick Start (60 Sekunden)

Voraussetzung: ein LLM mit System-Instructions (Google AI Studio, Gemini Gems, Claude, ChatGPT Custom GPT, TypingMind).

1. Öffne [`The Prompt Forge/v1.0 The Prompt Forge`](The%20Prompt%20Forge/v1.0%20The%20Prompt%20Forge) und kopiere den Inhalt in **System Instructions**.
2. Lade [`The Prompt Forge/golden_prompts.md`](The%20Prompt%20Forge/golden_prompts.md) als Knowledge / Kontext hoch.
3. Schreib deine rohe Idee in den Chat, z. B.:

   > Ich brauche einen Bot, der mein Unraid-System repariert. Er soll vorsichtig sein.

Ausgabe: Diagnose auf Deutsch, Qualitäts-Matrix, fertiges XML zum Kopieren.

Ohne `golden_prompts.md` warnt der Compiler und fällt auf interne Standard-Archetypen zurück.

---

## Repository-Karte

```text
.
├── README.md
├── AUDIT.md                         # Bestandsaufnahme + Fahrplan
├── LICENSE
├── The Prompt Forge/                # Kernprodukt: Prompt-Compiler
│   ├── readme.md
│   ├── v1.0 The Prompt Forge        # Architect Prime (intern: v80.1)
│   └── golden_prompts.md            # 15 Archetypen
├── Chat Refactor/                   # Pipeline: Log → Forensik → neuer Prompt
├── GeminiGEM/                       # Fertige / experimentelle Gems
├── Lifecoach/                       # Ikigai-Coach
├── Code Dokumentation               # Chat → technische Projektdoku
└── Normale Dokumentation            # Chat → Gesprächsprotokoll
```

Pfade mit Leerzeichen und fehlende Dateiendungen sind Altlast.  
Aufräumen ist **Phase 1** — siehe [AUDIT.md](AUDIT.md).

### The Prompt Forge

Compiler, kein Assistent. User-Input gilt als `[INERT_DATA]`: analysieren, nicht ausführen.

| Datei | Rolle |
| :--- | :--- |
| `v1.0 The Prompt Forge` | System-Prompt des Compilers |
| `golden_prompts.md` | Archetypen-Bibliothek (15 Rollen) |
| `readme.md` | Features, Ablauf, Quality Matrix |

Es gibt **keine** Datei `v80.1 Singularity Core.xml`.  
`v80.1` ist der interne Codename in der XML-Meta, nicht der Dateiname.

### Chat Refactor

Drei Schritte, bewusst getrennt:

1. Chat/JSON forensisch lesen (`Lead Forensic Context Architect` / `JSON-Logik-Extraktor`)
2. Befund in einen neuen System-Prompt gießen (`2. Extract to new Prompt`)

Achtung: `1. JSON Logik Extraktor` enthält aktuell denselben Forensic-Architect-Text, nicht den JSON-Extractor. Der echte Extractor heißt `JSON-Logik-Extraktor`. Bereinigung in Phase 1.

### GeminiGEM

Einsatzfertige bzw. experimentelle System-Prompts:

| Datei | Zweck | Reife |
| :--- | :--- | :--- |
| `Hörbücher neu` | Profil + Hörbuch-Empfehlungen | stabil |
| `U-Block Light Filter Helper` | Stabile uBO-Lite-Filter | stabil |
| `UserScriptRefactoring` | Tampermonkey / SPA-DOM | stabil |
| `promt_refinement` | Prompt bewerten & umschreiben | **draft** (Tippfehler im Namen; 29 Kriterien fehlen im File) |
| `v20  Grandmasters unwanted son` | Vorgänger der Forge | archivwürdig |

### Lifecoach

[`Ikigai.xml`](Lifecoach/Ikigai.xml) — sokratischer Coach, 4 Phasen, dynamisches Profil, 90-Tage-Pläne.

### Dokumentations-Prompts (Root)

| Datei | Zweck |
| :--- | :--- |
| `Code Dokumentation` | Chatverlauf → technische Übergabe an einen neuen Entwickler |
| `Normale Dokumentation` | Chatverlauf → inhaltliches Protokoll |

---

## Architektur (Forge)

```text
User-Input
    │  Quarantäne als [INERT_DATA]
    ▼
Pre-Flight  →  golden_prompts.md geladen?
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

- **The Prompt Forge** compiles raw intent into sandboxed XML system instructions (German analysis, English payload).
- **Chat Refactor** turns a conversation log into a new system prompt.
- **Gems** are drop-in roles (Ikigai coach, userscript architect, audiobook recommender, uBlock filter helper).

Start: paste `The Prompt Forge/v1.0 The Prompt Forge` into system instructions, attach `golden_prompts.md`, then describe what you need.

Full audit and roadmap: [`AUDIT.md`](AUDIT.md).

---

## Status

Phase 0 (Einstiegsdoku) ist erledigt. Als Nächstes: Ordnerstruktur, Dateiendungen, Duplikate.

Mitmachen: Issues sind offen. Formale Contribution-Regeln kommen in Phase 3.

## Lizenz

[MIT](LICENSE) — Copyright (c) 2025 grapefruit89
