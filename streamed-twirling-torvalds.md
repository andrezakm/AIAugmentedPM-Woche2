# Plan: Eval — Business Case Research & Analysis System

> **Historische Notiz:** Dieser Plan ist das Original vom Bau des Systems (März 2026) — so, wie es im Video „Das Monster bauen" entsteht. Seitdem wurde die Struktur umgebaut: Der Ordner `eval/` ist jetzt das Wurzelverzeichnis, `prompts/` heißt `scripts/`, `input.yaml` liegt in `input/`, `company.md` und `strategy.md` in `context/`, und fertige Beispiel-Läufe liegen in `results/`. Die Logik ist unverändert.

## Context

Der Nutzer möchte ein mehrstufiges, agentenbasiertes Analyse-System für Business Cases aufbauen. Es soll:
- Tief und aus mehreren Winkeln recherchieren
- Einen klar strukturierten Lösungsraum aufbauen
- Verschiedene Agenten-Perspektiven debattieren lassen
- Alles in Markdown-Zwischendateien dokumentieren
- **Vollständig in Claude Code laufen und beobachtbar sein**

Die letzte Anforderung ist entscheidend für die Architektur: Das System wird **nicht** als isoliertes Python-Skript gebaut, sondern als **Claude Code-nativer Workflow** — Claude Code selbst ist der Orchestrator und nutzt den Agent-Tool-Mechanismus für Parallelität und Sub-Agenten.

---

## Architektur-Entscheidung: Claude Code-nativer Workflow

### Warum nicht ein standalone Python-Skript?
- Der Nutzer möchte Beobachtbarkeit direkt im Claude Code Interface
- Alle Tools (WebSearch, WebFetch, Write) stehen Agenten direkt zur Verfügung
- Kein API-Key-Management, kein Setup von Tavily/Serper o.ä.
- Parallelisierung via parallele Agent-Tool-Aufrufe in einer Nachricht

### Kernkomponenten

```
input.yaml                   → Strukturierter Input (Firma, Strategie, Business Case)
prompts/                     → Prompt-Templates für jeden Agenten-Typ
  research_market.md
  research_technology.md
  research_problems.md
  status_quo_analysis.md
  hypothesis_*.md
  debate_persona_*.md
  synthesis.md
output/                      → Alle Zwischendateien
  research_market.md
  research_technology.md
  research_problems.md
  status_quo_analysis.md
  hypothesis_solution.md
  hypothesis_technology.md
  hypothesis_business_model.md
  debate_round_1.md
  debate_round_2.md          (optional)
  final_report.md
FLOW.md                      → Mermaid-Diagramm des gesamten Flows
run.md                       → Anleitung: Wie startet man einen Run?
```

---

## Phasen-Design

### Phase 0 — Input laden
- Nutzer stellt `input.yaml` bereit (Schema: `company`, `strategy`, `business_case`, `solution_direction`)
- Claude Code liest und validiert den Input
- Output-Ordner für diesen Run wird angelegt (z.B. `output/run_YYYYMMDD_HHMMSS/`)

### Phase 1 — Research (3 parallele Agenten)
**Alle drei gleichzeitig gestartet (Agent tool, 3 Calls in einer Nachricht):**

| Agent | Aufgabe | Output |
|---|---|---|
| `research-market` | Marktgröße, Segmente, Wettbewerb, Trends | `research_market.md` |
| `research-technology` | Tech-Landschaft, Reifegrad, Make/Buy | `research_technology.md` |
| `research-problems` | Öffentlich geäußerte Pain Points, Priorisierung | `research_problems.md` |

Jeder Agent:
- Erhält den vollen Input-Kontext
- Führt 4–6 Web-Suchanfragen durch (WebSearch + WebFetch)
- Gliedert seine Suche in Unteraufgaben (z.B. Markt → TAM/Segmente/Wettbewerber/Trends als separate Suchen)
- Schreibt sein Ergebnis in die Output-Datei

**Qualitätssicherung Research-Tiefe:**
- Jeder Research-Agent hat eine Mindest-Anforderung: mind. 4 Quellen pro Unteraufgabe
- Wenn Quellen dünn sind, führt der Agent eine zweite Suchschicht durch

### Phase 2 — Ist-Analyse (sequenziell, 1 Agent)
- Liest alle 3 Research-Outputs
- Kontextualisiert gegen den spezifischen Input (Firma + Strategie + Lösungsrichtung)
- Identifiziert: relevante Chancen, passende Technologien, adressierte Probleme, Lücken & Risiken
- Output: `status_quo_analysis.md`

### Phase 3 — Lösungshypothesen (3 parallele Agenten)
**Alle drei gleichzeitig gestartet:**

| Agent | Aufgabe | Output |
|---|---|---|
| `hypothesis-solution` | Konkrete Lösung: Features, User Journey, Value Prop | `hypothesis_solution.md` |
| `hypothesis-technology` | Tech-Architektur, Build-Blöcke, Top-Risiken | `hypothesis_technology.md` |
| `hypothesis-business` | ICP, TAM/SAM/SOM, Preismodell, GTM | `hypothesis_business_model.md` |

Jeder Agent liest: Research-Outputs + Ist-Analyse

### Phase 4 — Agenten-Debatte (1–2 Runden)

**Runde 1:** 5 Agenten schreiben ihre Positionen **parallel**:

| Persona | Blickwinkel |
|---|---|
| Optimist | Chancen, Stärken, Upside, Best-Case |
| Kritiker | Schwächen, Annahmen hinterfragen, Worst-Case |
| Techniker | Machbarkeit, technische Risiken, Komplexität |
| Marktexperte | Vermarktbarkeit, Wettbewerb, Customer Fit |
| Stratege | Strategischer Fit, Timing, Ressourcen |

Danach: **Moderator-Agent** (sequenziell) liest alle 5 Positionen, identifiziert:
- Konsens-Punkte
- Widersprüche
- Kritischste offene Fragen

Output: `debate_round_1.md`

**Runde 2 (optional):** Wenn Moderator signifikante Widersprüche identifiziert → zweite Runde mit fokussierter Debatte auf die Konfliktpunkte. Output: `debate_round_2.md`

### Phase 5 — Synthese & Final Report (1 Agent)
Liest alle bisherigen Outputs und erstellt:
- Executive Summary (1 Seite)
- Stärken & Schwächen der Lösungsrichtung
- Empfehlung: Go / No-Go / Pivot-Optionen mit Begründung
- Offene Fragen & empfohlene nächste Schritte

Output: `final_report.md`

### Phase 6 — Flow-Dokumentation
- Mermaid-Diagramm wird generiert (verfeinert basierend auf tatsächlichem Run)
- Gespeichert in `FLOW.md`

---

## Dateisystem-Struktur

```
/eval/
  input.yaml              ← Input-Template
  run.md                  ← Anleitung für einen Run
  FLOW.md                 ← Mermaid-Diagramm
  prompts/
    p1_research_market.md
    p1_research_technology.md
    p1_research_problems.md
    p2_analysis.md
    p3_hypothesis_solution.md
    p3_hypothesis_technology.md
    p3_hypothesis_business.md
    p4_debate_optimist.md
    p4_debate_critic.md
    p4_debate_technician.md
    p4_debate_market.md
    p4_debate_strategist.md
    p4_moderator.md
    p5_synthesis.md
  output/
    run_YYYYMMDD_HHMMSS/
      research_market.md
      research_technology.md
      research_problems.md
      status_quo_analysis.md
      hypothesis_solution.md
      hypothesis_technology.md
      hypothesis_business_model.md
      debate_round_1.md
      debate_round_2.md
      final_report.md
```

---

## Wie wird ein Run gestartet?

1. Nutzer füllt `input.yaml` aus
2. Nutzer sagt Claude Code: "Starte einen Eval-Run mit input.yaml"
3. Claude Code liest die Prompts aus `/eval/prompts/`, befüllt sie mit Input-Kontext
4. Orchestrierung läuft Phase für Phase, mit sichtbaren parallelen Agenten
5. Nach jedem Phase-Ende: kurze Status-Ausgabe an den Nutzer
6. Final Report wird am Ende zusammengefasst

---

## Input-Schema (input.yaml)

```yaml
company:
  name: ""
  description: ""        # Wer seid ihr? Kernkompetenzen, Team, Ressourcen
  tech_stack: []         # Relevante Technologien die ihr bereits nutzt/habt

strategy:
  direction: ""          # Wohin wollt ihr? Positionierung, Ziel
  constraints: []        # Was ist ausgeschlossen / nicht verhandelbar?

business_case:
  topic: ""              # Das zu untersuchende Thema (1-2 Sätze)
  solution_direction: "" # Grobe Lösungsrichtung (die Hypothese, die analysiert wird)
  target_market: ""      # Wer soll adressiert werden (grob)

run_options:
  debate_rounds: 1       # 1 oder 2
  research_depth: "deep" # "quick" | "deep" — steuert Anzahl Web-Suchen
  language: "de"         # Ausgabesprache der Reports
  mode: "step"           # "step" = Pause nach jeder Phase (zum Testen) | "auto" = vollautomatisch
```

---

## Zu bauende Dateien (in dieser Reihenfolge)

1. `eval/input.yaml` — Input-Template mit Kommentaren
2. `eval/prompts/p1_research_market.md` — Prompt-Template Markt-Research
3. `eval/prompts/p1_research_technology.md` — Prompt-Template Tech-Research
4. `eval/prompts/p1_research_problems.md` — Prompt-Template Problem-Research
5. `eval/prompts/p2_analysis.md` — Prompt-Template Ist-Analyse
6. `eval/prompts/p3_hypothesis_solution.md`
7. `eval/prompts/p3_hypothesis_technology.md`
8. `eval/prompts/p3_hypothesis_business.md`
9. `eval/prompts/p4_debate_*.md` (5 Persona-Prompts)
10. `eval/prompts/p4_moderator.md`
11. `eval/prompts/p5_synthesis.md`
12. `eval/run.md` — Anleitung / Orchestrierungs-Guide für Claude Code
13. `eval/FLOW.md` — Mermaid-Diagramm

---

## Offene Entscheidungen (mit Empfehlung)

| Frage | Empfehlung |
|---|---|
| Sollte es ein Python-Helper-Script für den Output-Ordner geben? | Ja — kleines `setup_run.py` das den Output-Ordner anlegt |
| Wie tief soll Research gehen (Anzahl Suchen)? | "deep": 6 Suchen pro Agent, "quick": 3 Suchen |
| Soll der Nutzer zwischen Phasen bestätigen? | Optional via `run_options.interactive: true` |
| Prompt-Sprache (Templates in DE oder EN)? | **Templates auf EN** (besseres Reasoning), Output-Sprache via `language` steuerbar |
| Flow-Modus während Tests? | **`mode: "step"`** — Pause nach jeder Phase, user bestätigt. Später `mode: "auto"` für vollautomatischen Durchlauf. |

---

## Verifikation / Test

1. Einen Test-Run mit einem einfachen, bekannten Business Case starten
2. Prüfen ob alle Output-Dateien korrekt geschrieben werden
3. Prüfen ob Research-Tiefe ausreicht (mind. 4 Quellen pro Unteraufgabe)
4. Prüfen ob Debatte echte Widersprüche generiert (nicht nur Agreement)
5. Final Report auf Kohärenz mit Input prüfen
