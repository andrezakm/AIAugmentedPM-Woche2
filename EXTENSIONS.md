# Eval System — Geplante Erweiterungen

Erweiterungen die im Betrieb identifiziert wurden, aber noch nicht implementiert sind.

---

## 1. Zwischenanmerkungen (Mid-Run Annotations)

**Problem:** Während eines Runs hat der Nutzer wichtigen Kontext der in den Input-Dokumenten fehlt. Derzeit gibt es keinen strukturierten Weg das einzuspeisen — der Nutzer muss warten und dann manuell korrigieren.

**Erweiterung:** Nach jeder Phase pausiert das System (bereits im Step-Modus vorhanden) und fragt explizit:
> "Gibt es Korrekturen oder zusätzlichen Kontext bevor Phase X startet?"

Der eingegebene Kontext wird als `annotation_phase_X.md` gespeichert und allen folgenden Agenten übergeben. Bereits laufende Phasen werden nicht unterbrochen.

**Gelernt aus:** HR Harness Run — "n8n-Stack", "Compliance Layer existiert bereits", "600 Kunden" wurden erst nach Phase 1 eingegeben und mussten manuell in den Kontext gebracht werden.

---

## 2. Klärungsfragen vor dem Start (Pre-Run Clarification)

**Problem:** Das Input-YAML hat strukturelle Lücken — nicht weil der Nutzer nichts weiß, sondern weil die richtigen Fragen nicht gestellt werden. Beispiel HR Harness: "Compliance Layer exists as HRPerfect infrastructure" klingt nach internem Tool, nicht nach "wir sind der trusted compliance partner der HR-Abteilungen inkl. Betriebsräte."

**Erweiterung:** Nach dem Lesen des YAML, aber vor Phase 1, startet ein Clarification-Agent der 3-5 gezielte Fragen stellt:
- Welche bestehenden Kundenbeziehungen sind tiefgehend genug um die GTM-These zu tragen?
- Gibt es bestehende Vertrauensbeziehungen mit regulatorischen Stakeholdern (Betriebsräte, Behörden)?
- Was hat das Unternehmen schon versucht, das gescheitert ist? (Anti-Joy-Pattern)
- Was ist das schlimmste Szenario das der Nutzer für diesen Business Case kennt?

Die Antworten werden als `clarification.md` gespeichert und in alle Prompts eingespeist.

**Schema-Erweiterung für input.yaml:**
```yaml
existing_trust_relationships: ""  # Tiefe Beziehungen die GTM-Annahmen tragen
compliance_track_record: ""       # Bestehende Compliance-Autorität beim Kunden
known_failure_modes: ""           # Was wurde schon versucht und hat nicht funktioniert
```

---

## 3. Konservative und Extreme Cases (Scenario Expansion)

**Problem:** Das System produziert derzeit einen einzelnen Base-Case. Für strategische Entscheidungen unter Unsicherheit ist das zu eng — besonders wenn der Base-Case auf unvalidierten Annahmen beruht (z.B. Consulting-Conversion-Rate 40-60% ohne Marktbelege).

**Erweiterung:** Phase 3 Business Model Hypothesis erzeugt drei parallele Szenarien:

| Szenario | Beschreibung | Beispiel HR Harness |
|---|---|---|
| **Konservativ** | Alle unvalidierten Annahmen auf unteres Ende; Wettbewerb tritt früh ein | Conversion 15%, SOM €350K Y1, SAP Mittelstand in 12 Monaten |
| **Base Case** | Aktuelle Hypothese wie bisher | Conversion 35%, SOM €600K Y1 |
| **Optimistisch** | Hypothese hält, Urgency-Window funktioniert, Kunden-Retention hoch | Conversion 55%, SOM €950K Y1, 3 Enterprise-Deals |

Die Debatte-Agenten in Phase 4 erhalten alle drei Szenarien und debattieren:
- In welchem Szenario ist die Entscheidung eindeutig (Go oder No-Go)?
- Welches Szenario ist am wahrscheinlichsten und warum?
- Was müsste eintreten damit das konservative Szenario zum Base Case wird?

**Vorteil:** Öffnet das Verfahren — statt "ist die Annahme korrekt?" wird gefragt "unter welchen Bedingungen ist es trotzdem gut/schlecht?"

---

## 4. What Must Be True — Validation Sequencing (bereits implementiert)

**Status:** In HR Harness Run als Pflicht-Sektion im Moderator-Prompt eingebaut. Sollte in den Standard-Moderator-Prompt aufgenommen werden.

**Format:**
```
| # | Assumption | Kill probability | Cheapest test | Time to test | Decision gated |
```

**Prinzip:** Höchstes Risiko × günstiger Test geht zuerst. Nicht in Annahme #3 investieren bevor Annahme #1 validiert ist.

---

## 5. Ownership Change Scenarios (bereits implementiert als Ad-hoc)

**Status:** Im HR Harness Run auf Nutzeranfrage in Round-2-Strategist eingebaut. Sollte als optionale Sektion in den Standard-Strategist-Prompt aufgenommen werden — aktiviert wenn `ownership_structure` im input.yaml angegeben ist.

**Trigger:** Wenn input.yaml `ownership_structure: "private_investor"` oder ähnliches enthält, aktiviert der Strategist automatisch die Ownership-Change-Analyse.

---

## 6. Schärferes Input-Feedback

**Problem:** Gelernt aus HR Harness: Der Nutzer kann wichtigen Kontext nicht einbringen wenn das Schema keine Felder dafür hat.

**Erweiterung:** Nach Phase 2 (Ist-Analyse) prüft ein Feedback-Agent ob die Analyse Annahmen macht die dem Nutzer offensichtlich falsch erscheinen könnten, und fragt direkt:
> "Die Analyse geht davon aus, dass [X]. Stimmt das? Gibt es wichtige Hintergrundinformationen die diese Einschätzung verändern würden?"

---

*Dokumentiert nach NeoEmployee- und HR-Harness-Runs, März 2026.*
