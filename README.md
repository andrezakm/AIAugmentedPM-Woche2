# AI-Augmented PM — Woche 2: Business Case Analysis mit Agenten-Debatten

Willkommen. Dieses Repository enthält alle Materialien für Woche 2 des Kurses **AI-Augmented Product Management**.

Du lernst in dieser Woche, wie du mit Claude aus einem Business Case einen vollständigen Analyse-Report baust — mit parallelen Research-Agenten, strukturierten Lösungshypothesen und einer echten Agenten-Debatte, die in eine finale Empfehlung mündet.

Das System heißt **Eval**. Es läuft vollständig in Claude Code, ist zu 100 % beobachtbar und produziert in einem einzigen Run bis zu 10 Markdown-Dokumente — inklusive Final Report mit Go/No-Go-Empfehlung.

---

## Voraussetzungen

Du brauchst Claude — auf demselben Weg wie in Woche 1. **Beide Wege funktionieren für diesen Kurs gleich gut.** Nimm den, der bei dir schon läuft.

### Weg A — Claude in der Desktop-App

Wenn Claude bei dir schon installiert ist — in vielen Firmen wird die Desktop-App zentral ausgerollt — brauchst du **nichts weiter**: keine Installation, kein Terminal. Du arbeitest direkt in der App.

### Weg B — Claude Code im Terminal (in Cursor oder in der Terminal-App)

- **Claude Code installieren**, falls noch nicht vorhanden → [claude.ai/code](https://claude.ai/code). Folge den Anweisungen auf der Seite für dein Betriebssystem.
- **Ein Terminal:**
  - **Cursor (oder VS Code):** das eingebaute Terminal — Menü *Terminal → New Terminal*
  - **Mac:** das Programm **Terminal** — bereits vorinstalliert (Programme → Dienstprogramme → Terminal, oder `Cmd + Leertaste` → "Terminal")
  - **Windows:** **PowerShell** — in der Windows-Suche suchen und öffnen

---

## Installation

### Schritt 1 — Kursordner herunterladen

Klicke auf dieser GitHub-Seite auf den grünen **Code**-Button → **Download ZIP**.

Entpacke die ZIP-Datei:

- **Windows:** Rechtsklick auf die Datei → **„Alle extrahieren"** → **„Extrahieren"**. (Nicht nur doppelklicken — dann stecken die Dateien noch im Archiv.)
- **Mac:** Doppelklick genügt.

Der entpackte Ordner heißt `AIAugmentedPM-Woche2-main`. Leg ihn ab, wo du magst — zum Beispiel auf dem Schreibtisch.

### Schritt 2 — Claude im Kursordner öffnen

Claude muss in **genau diesem Ordner** arbeiten — dem, in dem direkt die `CLAUDE.md` liegt, nicht eine Ebene darüber. Nimm den Weg, den du oben gewählt hast:

**Weg A — Desktop-App**

Öffne Claude, starte eine **neue Session** und lenke sie in den entpackten Kursordner.

**Weg B — Terminal**

In **Cursor**: *File → Open Folder* → den Ordner `AIAugmentedPM-Woche2-main` wählen, dann das Terminal öffnen und `claude` tippen.

In der **Terminal-App** navigierst du selbst in den Ordner:

**Mac:**
```bash
cd ~/Desktop/AIAugmentedPM-Woche2-main
claude
```

**Windows (PowerShell):**
```powershell
cd "$env:USERPROFILE\Desktop\AIAugmentedPM-Woche2-main"
claude
```

Falls du den Ordner woanders gespeichert hast, passe den Pfad entsprechend an.

### Schritt 3 — Websuche erlauben

Das Eval-System recherchiert im Internet (Markt, Wettbewerber, Technologie). Damit das auch in den Unter-Agenten funktioniert, müssen WebSearch und WebFetch in deinen Claude-Einstellungen erlaubt sein.

Tippe in Claude:

```
Füge WebSearch und WebFetch zu meinen erlaubten Tools hinzu.
```

Claude erledigt das selbst. Das musst du nur einmal machen — die Einstellung bleibt erhalten.

---

## Kurs starten

Sobald Claude im Kursordner läuft, tippe einfach:

```
Starte den Kurs
```

Claude liest den Kurs ein und beginnt sofort mit der Begrüßung. Du kannst während des Kurses jederzeit:
- **`weiter`** tippen, um zum nächsten Schritt zu gehen
- **`überspringen`** tippen, um einen Schritt zu überspringen
- **`stop`** tippen, um den Kurs zu unterbrechen

Außerhalb des Kurses kannst du Claude normal verwenden — er startet den Kurs nur, wenn du ihn ausdrücklich dazu aufforderst.

Du kannst jederzeit an einem beliebigen Schritt einsteigen:

```
Starte den Kurs ab Schritt 4
```

---

## Dateistruktur

```
AIAugmentedPM-Woche2-main/
├── README.md                    ← Diese Datei — lies sie zuerst
├── CLAUDE.md                    ← Wird automatisch von Claude geladen
├── Kurs_Woche2.md               ← Der vollständige Kursinhalt
├── run.md                       ← Orchestrierung: wie ein Eval-Run abläuft
├── FLOW.md                      ← Flussdiagramm des gesamten Systems
├── Eval.md                      ← Prinzipien & Systemdesign (Referenz)
├── EXTENSIONS.md                ← Ideen, wie man das System weiterbaut
├── Eval - Flow Übersicht.html   ← Der Flow als Seite im Browser
├── streamed-twirling-torvalds.md ← Der ursprüngliche Bauplan (Lektion „Das Monster bauen")
├── context/
│   ├── company.md               ← Wer sind wir? (statischer Kontext)
│   └── strategy.md              ← Was ist die Strategie? (statischer Kontext)
├── input/
│   └── input.yaml               ← Dein Business Case — hier startet alles
├── scripts/                     ← Prompt-Templates für alle Agenten (14 Dateien)
│   ├── p1_research_market.md
│   ├── … (Research, Analyse, Hypothesen, Debatte, Synthese)
│   └── p5_synthesis.md
├── output/                      ← Leer — deine eigenen Runs landen hier
└── results/                     ← Fertige Beispiel-Läufe zum Anschauen
    ├── neoemployee/
    ├── voltaris/
    └── hrperfect/
```

Ein vollständiger Run erzeugt in `output/run_YYYYMMDD_HHMMSS/`:

```
research_market.md · research_technology.md · research_problems.md
status_quo_analysis.md
hypothesis_solution.md · hypothesis_technology.md · hypothesis_business_model.md
debate_round_1.md · debate_round_2.md (optional)
final_report.md
```

**`results/`** enthält fertige Beispiel-Läufe — schau sie an, ohne selbst einen (token-intensiven) Run starten zu müssen. Für **eigene, saubere** Runs bleibt `output/` leer; die Beispiele in `results/` sind nur zum Lesen.

---

## Welches Modell verwenden?

Für den Kurs reicht **Sonnet** — wie in Woche 1. Der Eval-Run orchestriert viele Agenten über fünf Phasen; wenn du später einen ernsthaften eigenen Case mit `deep` laufen lässt, ist **Opus** die bessere Wahl: Es hält die lange, mehrstufige Orchestrierung besser zusammen und glättet die Debatte weniger zu Konsens.

So wählst du es:

- **Desktop-App:** im Modell-Auswahlfeld wählen.
- **Terminal:** `/model` tippen, Enter, dann aus der Liste wählen.

---

## Hinweis: Token-Limit

Ein vollständiger Run (alle 5 Phasen, 2 Debattenrunden) startet bis zu 20 Agenten und verbraucht deutlich mehr Tokens als Woche 1. Bei intensiver Nutzung kann Claude dich bitten, kurz zu warten — das Token-Limit wird alle 5 Stunden zurückgesetzt. Das ist normal.

**Empfehlung für den ersten Run:** Step-Modus (`mode: "step"`) und `research_depth: "quick"` — beides ist in `input/input.yaml` so voreingestellt. Das System pausiert dann nach jeder Phase, und du siehst, was produziert wurde, bevor es weitergeht.

---

## Probleme?

- **Research-Agenten finden nichts** → WebSearch/WebFetch nicht erlaubt → Schritt 3 der Installation wiederholen.
- **Claude findet die Dateien nicht** → stelle sicher, dass Claude **im Kursordner** arbeitet (dem, in dem direkt `CLAUDE.md` liegt — nicht eine Ebene darüber, nicht in einem Unterordner).
- **Run bricht ab** → im Step-Modus kannst du fortfahren: „weiter mit Phase X".
- **Ergebnis wirkt unsauber / mischt sich mit den Beispielen** → für einen sauberen Lauf `output/` leeren und keine alten Läufe oder `results/` als Eingabe verwenden. (Guter Moment zu verstehen, wie stark Kontext das Ergebnis prägt.)
- **Kurs startet nicht** → stelle sicher, dass du das Repository vollständig heruntergeladen hast (nicht nur einzelne Dateien) und Claude neu startest.
- Bei allem anderen: Nachricht an Markus — oder im nächsten Call fragen.
