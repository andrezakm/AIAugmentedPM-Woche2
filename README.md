# AI-Augmented PM — Woche 2: Business Case Analysis mit Agenten-Debatten

Willkommen. Dieses Repository enthält alle Materialien für Woche 2 des Kurses **AI-Augmented Product Management**.

Du lernst in dieser Woche, wie du mit Claude Code aus einem Business Case einen vollständigen Analyse-Report baust — mit parallelen Research-Agenten, strukturierten Lösungshypothesen und einer echten Agenten-Debatte, die in eine finale Empfehlung mündet.

Das System heißt **Eval**. Es läuft vollständig in Claude Code, ist zu 100 % beobachtbar und produziert in einem einzigen Run bis zu 10 Markdown-Dokumente — inklusive Final Report mit Go/No-Go-Empfehlung.

---

## Voraussetzungen

Du brauchst nur zwei Dinge:

### 1. Claude Code installieren

Claude Code ist die App, mit der du diesen Kurs durchläufst.

→ Installationsanleitung: [claude.ai/code](https://claude.ai/code)

Folge den Anweisungen auf der Seite für dein Betriebssystem.

### 2. Ein Terminal

- **Mac:** Das Programm heißt **Terminal** — bereits vorinstalliert (Programme → Dienstprogramme → Terminal, oder `Cmd + Leertaste` → "Terminal")
- **Windows:** Suche nach **PowerShell** in der Windows-Suche und öffne es

---

## Installation

### Schritt 1 — Kursordner herunterladen

Gehe auf die Kursseite (den Link hast du per E-Mail erhalten) und klicke auf den grünen **Code**-Button → **Download ZIP**.

Entpacke die ZIP-Datei in einen Ordner deiner Wahl — zum Beispiel auf dem Schreibtisch oder in deinen Dokumente-Ordner.

### Schritt 2 — Claude Code im Kursordner starten

Öffne dein Terminal und navigiere in den entpackten Ordner:

**Mac:**
```bash
cd ~/Desktop/AIAugmentedPM-Woche2
claude
```

**Windows (PowerShell):**
```powershell
cd "$env:USERPROFILE\Desktop\AIAugmentedPM-Woche2"
claude
```

Falls du den Ordner woanders gespeichert hast, passe den Pfad entsprechend an.

### Schritt 3 — WebSearch-Berechtigung setzen

Das Eval-System sucht im Internet nach Marktdaten, Wettbewerbern und Technologien. Damit das in Unter-Agenten funktioniert, muss WebSearch in deinen Claude-Einstellungen erlaubt sein.

Tippe in Claude Code:

```
Füge WebSearch und WebFetch zu meinen erlaubten Tools hinzu.
```

Claude erledigt das automatisch. Du musst das nur einmal machen — die Einstellung bleibt erhalten.

---

## Kurs starten

Sobald Claude Code läuft, tippe einfach:

```
Starte den Kurs
```

Claude liest den Kurs ein und beginnt sofort mit der Begrüßung. Du kannst während des Kurses jederzeit:
- **`weiter`** tippen, um zum nächsten Schritt zu gehen
- **`überspringen`** tippen, um einen Schritt zu überspringen
- **`stop`** tippen, um den Kurs zu unterbrechen

Du kannst an einem beliebigen Schritt einsteigen:

```
Starte den Kurs ab Schritt 4
```

---

## Dateistruktur

```
AIAugmentedPM-Woche2/
├── README.md                    ← Diese Datei — lies sie zuerst
├── Woche2.md                    ← Der vollständige Kursinhalt
├── eval/
│   ├── input.yaml               ← Dein Business Case — hier startet alles
│   ├── company.md               ← Beispiel-Firmenprofil (NeoEmployee)
│   ├── strategy.md              ← Beispiel-Strategie (NeoEmployee)
│   ├── FLOW.md                  ← Flussdiagramm des gesamten Systems
│   ├── run.md                   ← Orchestrierungsanleitung für Claude Code
│   └── prompts/                 ← Prompt-Templates für alle Agenten (13 Dateien)
│       ├── p1_research_market.md
│       ├── p1_research_technology.md
│       ├── p1_research_problems.md
│       ├── p2_analysis.md
│       ├── p3_hypothesis_solution.md
│       ├── p3_hypothesis_technology.md
│       ├── p3_hypothesis_business.md
│       ├── p4_debate_optimist.md
│       ├── p4_debate_critic.md
│       ├── p4_debate_technician.md
│       ├── p4_debate_market.md
│       ├── p4_debate_strategist.md
│       └── p5_synthesis.md
└── output/                      ← Leer — wird im Run befüllt
```

Ein vollständiger Run erzeugt in `eval/output/run_YYYYMMDD_HHMMSS/`:

```
research_market.md
research_technology.md
research_problems.md
analysis_status_quo.md
hypothesis_solution.md
hypothesis_technology.md
hypothesis_business_model.md
debate_round_1.md
debate_round_2.md          ← optional
final_report.md
```

---

## Welches Modell verwenden?

Für diesen Kurs reicht **Claude Sonnet 4.6** vollständig aus. So wählst du das Modell:

```bash
claude --model claude-sonnet-4-6
```

Oder nach dem Start mit `/model` in der Claude Code Oberfläche.

**Hinweis:** Das Eval-System startet bis zu 20 parallele Agenten in einem vollständigen Run mit zwei Debattenrunden. Das verbraucht mehr Tokens als ein normales Gespräch — plane dafür etwas Zeit und Token-Budget ein.

---

## Hinweis: Token-Limit

Bei einem vollständigen Run (alle 6 Phasen, 2 Debattenrunden) werden deutlich mehr Tokens verbraucht als in Woche 1. Das Token-Limit von Claude Code wird alle 5 Stunden zurückgesetzt.

**Empfehlung für den ersten Run:** Nutze den Step-Modus (`mode: "step"` in `input.yaml`). So pausiert das System nach jeder Phase — du kannst lesen, was produziert wurde, bevor es weitergeht.

---

## Probleme?

- **Agenten finden keine Suchergebnisse** → WebSearch-Berechtigung fehlt → Schritt 3 der Installation wiederholen
- **Claude findet die Dateien nicht** → stelle sicher, dass du Claude Code **im Kursordner** gestartet hast (nicht in einem Unterordner)
- **Run bricht ab** → der Step-Modus erlaubt es, an jedem Punkt fortzufahren; tippe "weiter mit Phase X"
- **Kurs startet nicht** → stelle sicher, dass `Woche2.md` im selben Ordner liegt wie `README.md`
