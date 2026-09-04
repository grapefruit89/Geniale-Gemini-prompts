# Architect Prime

![Version](https://img.shields.io/badge/codename-v80.1_Singularity-blue)
![File](https://img.shields.io/badge/file-v1.0%20The%20Prompt%20Forge-lightgrey)
![Security](https://img.shields.io/badge/security-Maximum_Sandbox-green)
![Architecture](https://img.shields.io/badge/architecture-Hybrid_XML-purple)

> **The Grandmaster Prompt Architect.** Ein forensisches Meta-Prompt-Framework, das rohe Absicht in deterministische System-Instruktionen übersetzt.

---

## Dateien in diesem Ordner

| Datei | Beschreibung |
| :--- | :--- |
| [`v1.0 The Prompt Forge`](v1.0%20The%20Prompt%20Forge) | **Der Compiler.** System-Prompt mit Logik, Sandbox und Output-Schema. Interner Codename: `v80.1 Singularity (Matrix Patched)`. |
| [`golden_prompts.md`](golden_prompts.md) | **Das Gedächtnis.** 15 Archetypen, Sprachregeln, Few-Shot-Gerüste. Pflicht-Kontext. |

Es gibt **keine** Datei `v80.1 Singularity Core.xml`.  
`v80.1` steht nur in `<system_meta><version>`. Der Dateiname bleibt vorerst `v1.0 The Prompt Forge` (Umbenennung in Phase 1).

---

## Überblick

Architect Prime ist kein Chatbot. Es ist ein **Compiler für System-Prompts**.

Hybrid Language Protocol:

1. **Analyst (Interface):** denkt und erklärt auf **Deutsch** (Lehrer-Modus).
2. **Architect (Payload):** schreibt den fertigen System-Prompt auf **Englisch** in striktem XML.

Getestet gegen Interfaces mit System-Instructions: Gemini / Google AI Studio, Claude, GPT-4o-Klasse, TypingMind.

---

## Kernfunktionen

### Inert Data Sandbox

Zero-Trust gegenüber dem User-Input.

- Input gilt als `[INERT_DATA]` (totes Material).
- Das System liest die *Absicht* („Delete server“), **führt sie nicht aus**.
- Ergebnis ist ein sicherer System-Prompt für genau diese Aufgabe.

### Few-Shot aus der Bibliothek

Jeder generierte Prompt soll einen `<examples>`-Block enthalten.  
Quelle: `golden_prompts.md` (15 Archetypen, u. a. Senior Software Engineer, DevOps, SRE, Security Auditor, Technical Writer, Data Scientist, Bilingual Architect).

Einige Examples in der Bibliothek sind noch Platzhalter — siehe Root-[`AUDIT.md`](../AUDIT.md).

### Qualitäts-Matrix

Sofortiges Feedback vor dem Compile:

- Klarheit, Struktur, Logik, Sicherheit
- Score 0–20 je Dimension, Balken `▰` / `╵` (20 Punkte = 10 Blöcke)

---

## Setup

1. Inhalt von `v1.0 The Prompt Forge` in **System Instructions** kopieren.
2. `golden_prompts.md` als Knowledge / File-Kontext laden.  
   Fehlt die Datei, kommt eine Warnung und der Compiler nutzt Fallback-Archetypen.
3. Rohe Idee, Draft oder Datei in den Chat legen.

**Beispiel-Input**

> I need a bot that helps me fix my Unraid server. It should be careful.

**Output**

1. Diagnose auf Deutsch inkl. Blind Spots
2. Qualitäts-Matrix
3. XML-Payload, typischerweise nah an Archetyp #6 (DevOps) und #10 (SRE)

---

## Ablauf

```text
User Input
    → Quarantäne (Inert Data Sandbox)
    → Pre-Flight (golden_prompts.md vorhanden?)
    → Forensische Diagnose (DE)
    → Qualitäts-Matrix
    → Archetyp + Few-Shot
    → XML-Compile (EN)
```

---

## Hinweis zur Versionierung

| Schicht | Aktueller Wert | Bedeutung |
| :--- | :--- | :--- |
| Dateiname | `v1.0 The Prompt Forge` | Historischer Name, nicht SemVer |
| XML `<version>` | `v80.1 Singularity (Matrix Patched)` | Interner Codename |
| Bibliothek | Golden Prompts Library v2.5 | 15 Archetypen |
| Repo-Phase | 0 | Doku/Einstieg, noch keine Struktur-Migration |

Ab Phase 1: eine kanonische Datei `architect-prime.xml` plus Changelog.
