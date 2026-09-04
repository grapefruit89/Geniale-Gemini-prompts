# Chat Refactor

Pipeline: aus einem Gesprächsverlauf wird erst ein Befund, dann ein neuer System-Prompt.

Keine der Dateien hier hat bisher eine Endung. Namen mit Nummerierung sind Arbeitsstände. Bereinigung folgt in Phase 1 ([AUDIT.md](../AUDIT.md)).

---

## Reihenfolge

```text
Chat-Log / JSON
    → 1. Forensik (was ist wirklich passiert?)
    → 2. Compile (neuer XML-System-Prompt)
```

Optional davor: `JSON-Logik-Extraktor`, wenn die Quelle ein LLM-JSON-Log ist und du Verhalten (nicht Inhalt) abstrahieren willst.

---

## Dateien

| Datei | Aufgabe | Hinweis |
| :--- | :--- | :--- |
| [`1. Lead Forensic Context Architect`](1.%20Lead%20Forensic%20Context%20Architect) | Forensisches Gutachten: Fakten vs. Inferenz, ACH-Hypothesen | bevorzugte Forensik-Variante |
| [`1. JSON Logik Extraktor`](1.%20JSON%20Logik%20Extraktor) | **Gleicher Prompt-Typ wie Forensic Architect** | Dateiname irreführend — nicht der JSON-Extractor |
| [`JSON-Logik-Extraktor`](JSON-Logik-Extraktor) | Reconstructs Verhaltensregeln aus einem JSON-Chat-Log | der eigentliche Extractor |
| [`2. Extract to new Prompt`](2.%20Extract%20to%20new%20Prompt) | Report → deploybarer XML-System-Prompt | braucht den Befund aus Schritt 1 |

---

## Kurz nutzen

1. System-Prompt aus Schritt 1 laden, Log/Transkript einfügen, Befund speichern.
2. System-Prompt aus Schritt 2 laden, Befund einfügen, XML kopieren.
3. Neuen Prompt in einem frischen Chat als System Instruction verwenden.

Teil 1 der Compiler-Ausgaben ist Deutsch, Teil 2 (XML) Englisch.
