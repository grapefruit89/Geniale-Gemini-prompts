# Audit — Geniale-Gemini-prompts

**Stand:** 2026-09-05  
**Repo:** https://github.com/grapefruit89/Geniale-Gemini-prompts  
**Branch:** `main` @ `f2bb619` (vor Phase 0)  
**Lizenz:** MIT  
**Sichtbarkeit:** public, 0 Stars, 0 Forks, 1 Branch, keine Releases  

Dieses Dokument ist die Bestandsaufnahme vor der Professionalisierung.  
Phase 0 (Doku/Einstieg) ist umgesetzt. Ordner-Umbau folgt in Phase 1.

---

## 1. Ist-Zustand

### Metadaten

| Feld | Wert |
| :--- | :--- |
| Beschreibung (About) | leer |
| Topics | keine |
| Default-Branch | `main` |
| Weitere Branches | keine |
| Root-README (vorher) | faktisch leer (`..`) |
| Letzter Commit vor Audit | 2026-01-28, uBlock-Lite-Filter |

### Dateibaum (vor Phase 0)

```text
.
├── README.md                          # leer
├── LICENSE                            # MIT, © 2025 grapefruit89
├── Code Dokumentation                 # Prompt, keine Endung
├── Normale Dokumentation              # Prompt, keine Endung
├── Chat Refactor/
│   ├── readme.md                      # Müll: "ff"
│   ├── 1. JSON Logik Extraktor        # Inhalt = Forensic Architect (falscher Name)
│   ├── 1. Lead Forensic Context Architect
│   ├── 2. Extract to new Prompt
│   └── JSON-Logik-Extraktor           # anderer Prompt, ähnlicher Name
├── GeminiGEM/
│   ├── Hörbücher neu
│   ├── U-Block Light Filter Helper
│   ├── UserScriptRefactoring
│   ├── promt_refinement               # Tippfehler; 29 Kriterien fehlen
│   └── v20  Grandmasters unwanted son # Vorgänger der Forge
├── Lifecoach/
│   └── Ikigai.xml                     # vollständig, lesbar
└── The Prompt Forge/
    ├── readme.md                      # gut, aber kaputte Dateiverweise
    ├── golden_prompts.md              # 15 Archetypen (README behauptete 11)
    └── v1.0 The Prompt Forge          # Kern-Compiler, intern "v80.1"
```

Es gibt **kein** File `v80.1 Singularity Core.xml`. Der Compiler liegt unter  
`The Prompt Forge/v1.0 The Prompt Forge` (ohne Endung).

---

## 2. Bewertung

### Substanz: 7/10

Keine Prompt-Sammlung zum Kopieren, sondern ein Meta-System:

- **Architect Prime** behandelt User-Input als `[INERT_DATA]`, analysiert auf Deutsch, kompiliert System-Prompts als englisches XML.
- **Golden Prompts v2.5** liefert 15 Rollen als Few-Shot-Gedächtnis.
- **Chat Refactor** ist eine Pipeline: Log → Forensik → neuer System-Prompt.
- Einzelne Gems sind einsatzfähig (Ikigai, Userscript-Architect, Hörbuch-Ingestor, uBlock-Helper).
- Sicherheitsmodell (Sandbox, nicht ausführen) und Sprachtrennung sind bewusst gebaut.

### Präsentation: 2/10

- Leere Root-README, kein About, keine Topics.
- Dateien ohne Endung, Leerzeichen und Umlaute in Pfaden.
- Doku verweist auf Dateien, die so nicht heißen.
- Versionsnummern sind Marketing (`v80.1`, `v30.0`, `v20`), kein Schema.
- Duplikate und falsche Dateinamen in `Chat Refactor`.

### Wiederverwendbarkeit für Dritte: 3/10

Ein Außenstehender versteht in 60 Sekunden nicht, was das Repo ist, welche Datei der Einstieg ist und welche Artefakte stabil vs. Entwurf sind.

---

## 3. Befunde im Detail

### 3.1 Broken references

`The Prompt Forge/readme.md` nannte `v80.1 Singularity Core.xml` als Hauptdatei.  
Tatsächlicher Pfad: `The Prompt Forge/v1.0 The Prompt Forge`.  
Dieselbe README zählte 11 Archetypen; `golden_prompts.md` enthält 15.

### 3.2 Duplikate und Namenskollisionen

| Datei | Problem |
| :--- | :--- |
| `Chat Refactor/1. JSON Logik Extraktor` | Enthält Lead Forensic Context Architect |
| `Chat Refactor/1. Lead Forensic Context Architect` | Nahezu gleiche Rolle, andere Schärfe |
| `Chat Refactor/JSON-Logik-Extraktor` | Echter JSON-Log-Extractor, anderer Inhalt |
| `GeminiGEM/v20  Grandmasters unwanted son` | Ältere Forge-Variante |
| `GeminiGEM/promt_refinement` | Tippfehler; Stub (29 Kriterien nicht enthalten) |

### 3.3 Qualitätsgefälle

| Artefakt | Status |
| :--- | :--- |
| Forge-Compiler | ausgearbeitet, einsatzbereit |
| Ikigai.xml | ausgearbeitet |
| Userscript / uBlock / Hörbücher | konkret, domänenspezifisch |
| golden_prompts.md | Struktur gut, Few-Shot oft Platzhalter |
| prompt_refinement | unvollständig |
| Root- und Chat-Refactor-READMEs | vorher unbrauchbar |

### 3.4 Git-Hygiene

- Nur `main`, keine Tags, kein Changelog.
- Kein `CONTRIBUTING`.
- Commit-Historie zeigt iterative Prompt-Arbeit — inhaltlich nachvollziehbar, strukturell nicht geplant.

---

## 4. Zielbild (Phase 1+, noch nicht umgesetzt)

```text
.
├── README.md
├── AUDIT.md
├── LICENSE
├── CHANGELOG.md
├── docs/
├── forge/
│   ├── architect-prime.xml
│   ├── golden-prompts.md
│   └── examples/
├── pipelines/chat-refactor/
├── gems/
└── archive/
```

Prinzip: ein Produkt vorne (Forge), fertige Gems daneben, Historie hinten.  
ASCII-kebab-case, Pflicht-Endungen `.xml` / `.md`.

---

## 5. ROI-Fahrplan

| Phase | Inhalt | Status |
| :---: | :--- | :--- |
| 0 | Root-README, About-Text, Müll-READMEs, Broken Refs, Tippfehler | **erledigt (dieser Commit)** |
| 1 | Ordner umbenennen, Endungen, Duplikate nach `archive/`, SemVer | offen |
| 2 | Few-Shots füllen, Frontmatter, Nutzungsbeispiel, usage.md | offen |
| 3 | CONTRIBUTING, Issue-Templates, optionales Release | offen |
| — | Website, App, 20 neue Archetypen, CI | bewusst nicht |

---

## 6. Offene Produktfrage

Positionierung bestimmt README-Ton und späteren Repo-Namen:

- **A** Framework-Repo (Architect Prime)
- **B** Toolbox: Forge + fertige Gems  ← Empfehlung
- **C** Private Werkstatt, nur aufräumen

Phase 0 dokumentiert **B**, ohne das Repo umzubenennen.

---

## 7. Was Phase 0 nicht ändert

Keine Dateiverschiebungen, keine Löschung von Prompt-Inhalt, keine Versions-Tags.  
`GeminiGEM/promt_refinement` bleibt als Dateiname erhalten, bis Phase 1 verschiebt; der Tippfehler ist in den READMEs dokumentiert.
