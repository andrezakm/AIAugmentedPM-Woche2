# Status Quo Analysis

> Input basis: research_market.md, research_technology.md, research_problems.md
> Company: Voltaris | Date: 2026-09-01

## 1. Relevant Market Opportunities

### Segmente und Trends mit direkter Relevanz für Voltaris

**Der Gesamtmarkt wächst, aber nicht zwingend in Voltaris' Zielsegment.** Der deutsche Batteriespeichermarkt wächst 2026 zweistellig (BVES: 17,1 Mrd. € Umsatz, +12 %), doch dieses Wachstum wird überproportional von Großspeichern getragen: Großspeicher (>1 MWh) legten im Q1 2026 um ~270 % zu und haben Heimspeicher beim Zubau-Volumen erstmals überholt, während die Heimspeicher-Stückzahlen 2025 um rund 8 % zurückgingen (research_market.md). Voltaris steigt damit in ein Teilsegment ein, dessen Branchen-Momentum und Kapitalfokus sich 2026 spürbar wegverschieben — ein Punkt, der in `input.yaml` nicht auftaucht.

**Das PV-Bestandssegment (Nachrüstung) ist der ökonomisch stärkste Anknüpfungspunkt.** PV-Anlagen der letzten 10–15 Jahre ohne Speicher werden zunehmend nachgerüstet, besonders wirtschaftlich, sobald die EEG-Einspeisevergütung nach 20 Jahren ausläuft; der Eigenverbrauchsanteil steigt dadurch von ~25–30 % auf bis zu 80 % (research_market.md). Das deckt sich unmittelbar mit dem in `input.yaml` skizzierten Zielsegment "PV-Besitzer" und mit Voltaris' bestehender Kundenbasis.

**Regulatorischer Rückenwind ist real, aber zweischneidig.** Seit 1.1.2025 müssen laut §41a EnWG alle Stromlieferanten dynamische Tarife anbieten — das vergrößert den grundsätzlich adressierbaren Markt, erhöht aber auch den Wettbewerbsdruck, weil praktisch jeder Anbieter denselben Einstieg hat (research_market.md). §14a EnWG (steuerbare Lasten) und die seit April 2026 lastvariablen Netzentgelte verstärken den ökonomischen Anreiz für automatisierte Steuerung zusätzlich zum reinen Preis-Spread (research_market.md) — das stützt die Grundidee der Solution Direction.

**Kritischer Flaschenhals: Smart-Meter-Rollout.** Nur 5,5 % aller Zählpunkte (23,3 % der Pflichtfälle) hatten Ende 2025 ein intelligentes Messsystem (research_market.md, research_technology.md). Das von Voltaris selbst benannte Risiko wird durch die Recherche nicht nur bestätigt, sondern präzise quantifiziert — und begrenzt das kurzfristig realistisch adressierbare Segment erheblich, unabhängig vom Geschäftsmodell.

### Opportunities im Einklang mit Strategie und Constraints

- **Bestandskundenbasis als Einstiegskeil** (`target_market`) ist strategisch sinnvoll: kein Kaltakquise-Aufwand, bestehende Vertrauensbeziehung — aber tragfähig nur für den Teil der Basis, der auch PV besitzt (siehe unten und Abschnitt 3).
- **Leasing-/Abo-Modelle** passen zum Kapital-Constraint ("Speicher auf die eigene Bilanz zu kaufen ist riskant"): Der Markt bietet bereits funktionierende Blaupausen (Bnewable, EWE, Yello, historisch Younicos; Mietpreise 69–114 €/Monat) — kein technologisches oder geschäftsmodellisches Neuland (research_technology.md).
- **DACH-/Deutschland-Fokus** wird durch nichts in der Recherche infrage gestellt — alle drei Research-Dateien sind konsequent auf den deutschen Markt fokussiert und liefern keinen Hinweis auf ungenutztes internationales Potenzial.
- **VPP/§14a als Zusatzerlös statt Kernwette** passt besser zur Kapitalrestriktion als eigener Hardware-Ausbau: Die Kiwigrid×Tibber-Kooperation zeigt, dass Flexibilitätserlöse auch ohne eigene Hardware-Herstellung/-Installation erschließbar sind (research_market.md).

### Opportunities, die explizit ausgeschlossen werden sollten

- **"Ohne PV" als primäres Zielsegment.** Mehrere unabhängige Quellen kommen übereinstimmend zum Schluss, dass reine Preis-Arbitrage ohne PV wirtschaftlich dünn bis "komplett witzlos" ist (research_market.md: nur für Haushalte mit hohem Verbrauch ab 3.500–4.000 kWh/Jahr überhaupt tragfähig; research_problems.md: Neon-Studie ~50 €/Jahr Nettoersparnis, reduco.ai-Rechner ~17 €/Jahr im pessimistischen Szenario). Die in `input.yaml` explizit gestellte Frage, ob "ohne PV" ein sinnvolles Zielsegment ist, lässt sich mit den vorliegenden Daten mit einem klaren "eher nein, jedenfalls nicht als Kernsegment" beantworten.
- **Volle vertikale Hardware-Integration nach Enpal-Vorbild als einzig geprüfte Option.** Der Vergleich Enpal (1,1 Mrd. € Umsatz 2025, erstmals positiver Free Cashflow) vs. Zolar (strukturell ähnliches Modell, Insolvenz im selben Jahr) zeigt, dass dieser Weg funktionieren kann, aber keineswegs zuverlässig funktioniert (research_market.md) — ohne Abwägung leichterer Alternativen (Tibber-Pulse-Modell, Kiwigrid-Partnerschaft) wäre das ein vermeidbares Klumpenrisiko.
- **VPP-/Netzdienst-Erlöse als tragende Umsatzsäule.** Die einzige belastbare Zahl (sonnenVPP: bis 100 €/Jahr Gewinnbeteiligung) deutet auf einen Nebenerlös hin; die Frequency/Severity-Map stuft dieses Thema explizit als "Niedrig" in der öffentlichen Diskussion ein (research_problems.md). Die in `strategy.direction` genannte VPP-Perspektive sollte nicht als primärer Business Case gerechnet werden.

## 2. Technology Fit Assessment

### Passung zum bestehenden Stack und Team

Voltaris' heutiger Stack (Smartphone-App, Python-Cloud-Backend, Day-Ahead-Marktanbindung, SMGW-Anbindung, Verbrauchsanalytics) trifft auf einen Technologiemarkt, der in fast allen benötigten Bausteinen bereits reif und zukaufbar ist:

- **Speicher-Hardware und Wechselrichter sind ein reifer, kommoditisierter Kaufmarkt** (LFP als dominante Zellchemie, >95 % Marktanteil bei Neugeräten; BYD, Tesla, Huawei, Sungrow, sonnen, E3/DC u. a. als etablierte Anbieter) — kein technologischer Grund für Eigenentwicklung (research_technology.md).
- **Die Steuerungssoftware/HEMS-Ebene ist der einzige Baustein mit echter Build-or-Buy-Wahl.** Der Markt bietet sowohl herstellerunabhängige Integrationsschichten (gridX, Solar Manager, Fenecon FEMS) als auch eine Open-Source-Referenz (evcc) — Letztere wird für ein kommerzielles B2C-Geschäft mit Support-/Haftungsanforderungen als eher ungeeignet eingeordnet (research_technology.md, dort explizit als eigene, nicht extern belegte Einschätzung gekennzeichnet). Genau hier dockt Voltaris' bestehende Kernkompetenz an: Die Recherche ordnet "Verbrauchs-/Nutzenanzeige, App, Nudging" explizit als Build-Feld und bestehende Voltaris-Stärke ein (research_technology.md) — die eigentliche Aufgabe ist, neue Hardware-Telemetrie in die bestehende App-Architektur einzuspeisen, nicht Steuerungstechnik neu zu erfinden.
- **SMGW/Steuerbox ist regulatorisch fixiert (BSI-Zertifizierung)** und bietet keinen Spielraum für Eigenentwicklung oder Beschleunigung durch Kapital — die Verfügbarkeit hängt vom zuständigen lokalen Messstellenbetreiber ab, nicht von Voltaris (research_technology.md).

### Realistische Build/Buy-Aufteilung für ein Unternehmen dieses Profils

| Baustein | Empfehlung | Begründung aus der Recherche |
|---|---|---|
| Batteriespeicher, Wechselrichter | Buy | Reifer, kommoditisierter Markt, kein technologischer Vorteil durch Eigenentwicklung (research_technology.md) |
| HEMS/Steuerungslogik | Buy/dünne eigene Integrationsschicht | Fertige Integrationsschichten am Markt; volle Eigenentwicklung wäre bei 55 Mitarbeitenden ohne Hardware-Erfahrung ein Ressourcen-Fehleinsatz (research_technology.md) |
| App/Nutzenanzeige/Nudging | Build | Explizit als Voltaris-Kernkompetenz eingeordnet (research_technology.md) |
| SMGW/Steuerbox | Buy (reguliert, alternativlos) | BSI-zertifiziert, kein Entwicklungsfeld (research_technology.md) |
| Installation/Service | Partner | Deckt sich mit `strategy.constraints`; Recherche zeigt aber, dass Partnerkapazität selbst knapp ist (siehe unten) |
| Finanzierung/Leasing | Partner/Buy | Bewährte Marktmuster vorhanden, kein Neuland (research_technology.md) |

Diese Aufteilung passt grundsätzlich zum Team-Profil (Software/UX/Energiemarkt-Schwerpunkt, keine Hardware-/Installationskompetenz laut `input.yaml`). Das Risiko liegt nicht im Technologie-Zukauf selbst, sondern in der **Integrationsarbeit** und der **Betriebsorganisation** rund um Installation und Service, die tatsächlich neu aufgebaut werden müsste.

### Technologierisiken, die spezifisch für Voltaris' Situation sind

- **Die implizite Vision "eine App steuert einheitlich jede Speichermarke" ist technisch nicht trivial.** Kompatibilität zwischen Speicher/Wechselrichter ist auch bei offenen Standards (SunSpec, EEBus) nicht automatisch gegeben, hängt vom Einzelfall ab, und Nachrüstung gelingt nicht immer (research_technology.md). Geschlossene Ökosysteme sind Realität: sonnen bietet nur eine eingeschränkte Cloud-API mit begrenztem lokalem Zugriff, Tesla hat erst 2024 überhaupt eine offizielle Drittanbieter-API veröffentlicht. Für Voltaris bedeutet das: Beschränkung auf wenige, gut dokumentierte Partnerhersteller, oder Zukauf/Lizenzierung einer herstellerunabhängigen Integrationsschicht (research_technology.md nennt diese Muster explizit) — beides schränkt die im Case implizit unterstellte Flexibilität ein.
- **Kompatibilität des bestehenden Python-Backends mit den recherchierten Hersteller-APIs/HEMS-Plattformen ist offen** — die Recherche markiert dies explizit als unternehmensinterne Lücke, die öffentlich nicht recherchierbar ist (research_technology.md).
- **Kostensensitivität/Kalkulationsunsicherheit:** Systempreise streuen je nach Quelle um den Faktor 3–4 (270 bis 1.200 €/kWh; research_market.md, research_technology.md) — für ein kapitalbeschränktes Startup ist eine belastbare Margenkalkulation vor Markteintritt entscheidend, und diese Grundlage fehlt aktuell.
- **Regulatorische Unsicherheiten mit direktem Produktbezug:** DSGVO-Einordnung hochfrequenter Speicher-/Zählerdaten als personenbezogene Daten (zusätzliche Compliance-Last für Voltaris' Analytics-Kernkompetenz), unklare AI-Act-Einordnung der Lade-/Entlade-Optimierungslogik (research_technology.md nennt dies ausdrücklich als ungeklärt und rechtlich zu prüfen, nicht als recherchierte Tatsache).
- **VPP-Marktzugang für einen neuen Aggregator wurde nicht recherchiert** (research_technology.md, explizite Lücke) — falls VPP-Erlöse strategisch relevant bleiben sollen, ist unklar, ob Voltaris dafür eine eigene Lizenz bräuchte oder auf eine offene Plattform wie Kiwigrid setzen könnte.

## 3. Problem-Solution Fit Assessment

### Probleme, die die Solution Direction adressiert

Das zentrale, laut `research_problems.md` **extern bestätigte** Problem — mangelndes Verhaltens-Engagement selbst bei "interessierten" Kunden (Verivox: nur ~6,4 % Kostendifferenz zwischen aktiver Lastverschiebung und Nicht-Verschiebung über 6 Monate) — ist in der Frequency/Severity-Map als "Hoch/Hoch" eingestuft und damit das ranghöchste Problem im Datensatz. Die Speicher-Hypothese (Automatisierung statt Verhaltensänderung) zielt direkt und plausibel auf dieses Problem.

Auch die im Case genannte Kaufhürde "Anschaffungskosten" (Frequency/Severity: Mittel-Hoch/Mittel laut research_problems.md) wird durch die im Solution-Direction-Konzept mitgedachte Leasing-/Abo-Option potenziell adressiert — allerdings ist das laut `input.yaml` (offene Frage 5) noch nicht entschieden, sondern offen.

### Probleme, die die Solution Direction NICHT adressiert

- **Informations-/Vertrauensdefizit bei dynamischen Tarifen generell** (81 % fühlen sich schlecht informiert, 48 % schließen dynamische Tarife aus — vzbv/forsa, research_problems.md), Frequency/Severity "Hoch/Mittel-Hoch". Die Solution Direction setzt ausschließlich auf die *bestehende* Kundenbasis, die diesen Schritt bereits gegangen ist. Das begrenzt die Reichweite der Horizon-2-Vision ("Heim-Energie-Plattform" für ein breiteres Publikum) erheblich, solange dieses Defizit nicht separat adressiert wird.
- **Fehlende technische Voraussetzungen (Smart Meter)** — kann von der Lösung strukturell nicht behoben werden, da außerhalb von Voltaris' Kontrolle; ist aber bereits als bekanntes Risiko in `input.yaml` benannt, also kein blinder Fleck.
- **Speicher-Ökonomie ohne PV bleibt schwach — die Lösung schafft dieses Problem nicht, löst es aber auch nicht.** Für den Teil der Zielgruppe ohne PV bleibt die zugrundeliegende Wirtschaftlichkeit dünn (siehe Abschnitt 1), unabhängig davon, wie gut die Automatisierung funktioniert. Die Lösung behebt das Engagement-Problem (Verhalten), nicht das Ökonomie-Problem (Wirtschaftlichkeit) — für Nicht-PV-Haushalte bleibt selbst ein perfekt automatisierter Speicher ein Produkt mit dünnem Nutzenversprechen.

### Höchste Frequenz/Schwere oder Nische?

Der adressierte Kern (Engagement-Lücke) ist das ranghöchste Problem in der Severity-Map (research_problems.md). Allerdings zielt der gewählte *Lösungsmechanismus* (physischer Speicher) gleichzeitig in ein zweites, ebenfalls als "Hoch/Hoch" eingestuftes Problem hinein — die dünne Speicher-Ökonomie ohne PV — und zwar so, dass dieses zweite Problem die Wirksamkeit der Lösung für einen unbekannten, aber laut Recherche vermutlich erheblichen Teil der Zielgruppe unterläuft. Es handelt sich damit nicht per se um eine "Nischen"-Lösung, sondern um **eine hochrangige Lösung für ein hochrangiges Problem, deren Wirksamkeit an eine bislang unquantifizierte Vorbedingung (PV-Besitz) geknüpft ist** — ohne saubere Segmentierung entlang dieser Vorbedingung droht die Lösung, am Massenmarkt der Bestandskunden vorbeizuzielen.

## 4. Gaps, Risks & Blind Spots

### Was die Recherche aufdeckt, das im Case bisher nicht auftaucht

- **Strukturelle Verschiebung weg vom Heimspeicher-Segment.** Kapital und Wachstum der Speicherbranche verlagern sich 2026 spürbar zu Großspeichern; Heimspeicher-Stückzahlen sind 2025 rückläufig (research_market.md). Voltaris plant den Einstieg in ein Segment mit nachlassendem Branchen-Momentum — dieser Punkt fehlt in `input.yaml` vollständig und sollte in die Bewertung der "großen strategischen Wette" einfließen.
- **Garantiekontinuität/Herstellerinsolvenz-Risiko als ungelöstes Branchenproblem.** Varta (Zellhersteller) ging 2025 insolvent, Sonnen musste nach einem Gerichtsurteil seine Garantiebedingungen überarbeiten, Growatt steht wegen Garantieverweigerung in der Kritik (research_market.md). Kein Marktstandard für Garantiekontinuität bei Herstellerausfall ist erkennbar. Für einen Anbieter, dessen Kernversprechen "einrichten und vergessen" lautet, ist das ein direktes Risiko für genau dieses Versprechen — zugleich potenziell eine ungenutzte Differenzierungschance.
- **Partnerkapazität ist kein elastisches Angebot.** Der Fachkräftemangel im Elektrohandwerk (research_technology.md, research_problems.md: je nach Quelle 12.000 bis 65.301 offene Stellen, PV-Wartezeiten 6–8 Monate) bedeutet, dass das von Voltaris bevorzugte Partnermodell auf eine Ressource setzt, um die bereits alle Wettbewerber konkurrieren. Das Fenecon-Support-Beispiel (research_problems.md: Support-Strukturen wuchsen nicht im Tempo der Nachfrage mit) ist ein dokumentiertes Warnsignal für genau dieses Risiko.
- **Der Wettbewerbsvorteil "software-first Anbieter geht in Hardware" ist von beiden Seiten angreifbar.** Sowohl andere Software-first-Tarifanbieter (Tibber, Octopus, Ostrom) könnten denselben Schritt gehen, als auch Hardware-Anbieter (1KOMMA5° mit "Heartbeat") besetzen bereits die Tarif-/Software-Ebene von der anderen Seite aus (research_market.md). Die aktuell unbesetzte Positionierungslücke könnte sich von beiden Seiten schließen, bevor Voltaris skaliert hat.

### Wo Evidenz dünn oder widersprüchlich ist

- TAM-Schätzungen für den deutschen BESS-Markt bis 2030 schwanken um den Faktor ~2,8 zwischen Quellen (6,34 vs. 2,271 Mrd. USD) und sind nicht aufgelöst (research_market.md).
- Systempreise pro kWh streuen um den Faktor 3–4 zwischen Quellen (270–1.200 €/kWh) — für eine belastbare Margenkalkulation unzureichend (research_market.md, research_technology.md).
- 1KOMMA5°-Umsatzzahlen sind zwischen Quellen widersprüchlich (research_market.md).
- Fachkräftemangel-Zahlen im Elektrohandwerk schwanken stark in der Größenordnung, sind aber richtungskonsistent (research_technology.md).
- Amortisationsrechnungen für Speicher schwanken zwischen 2–3 und 15–20 Jahren je nach Systemgröße/Rechenmodell zwischen Quellen (research_problems.md, dort selbst als klärungsbedürftig markiert).
- **Keine Quelle beziffert die Gesamtzahl der Kunden auf dynamischen Tarifen in Deutschland** oder die Schnittmenge "Eigenheim + dynamischer Tarif + Speicher-Interesse" (research_market.md) — die für Voltaris' TAM/ICP-Berechnung entscheidende Zahl fehlt komplett.

### Unvalidierte Annahmen der Solution Direction

- **"Einrichten und vergessen" wird als überzeugend angenommen, aber nicht getestet.** Keine der drei Research-Dateien untersucht direkt, ob Kunden einer automatisierten Speicherlösung tatsächlich mehr vertrauen bzw. dafür eine höhere Preisstufe akzeptieren als der heutigen App-Lösung. **Research gap: Zahlungsbereitschaft/Vertrauen speziell gegenüber einem automatisierten Hardware-Upgrade wurde in keiner der drei Dateien recherchiert.**
- **Die implizite Annahme einer einheitlichen App-Steuerung über beliebige Speichermarken hinweg** widerspricht der recherchierten technischen Realität geschlossener/uneinheitlicher APIs (Abschnitt 2).
- **Dass das Partnermodell Qualität/Service "beherrschbar" hält** (`strategy.constraints`) wird durch das Fenecon-Beispiel eher infrage gestellt als bestätigt.
- **Dass Speicher-Integration den Nutzen für die gesamte Bestandskundenbasis "automatisch" erzeugt**, gilt laut Recherche belastbar nur für den PV-Anteil dieser Basis — für den Rest bleibt der ökonomische Nutzen strukturell dünn, unabhängig vom Automatisierungsgrad.
- **Research gap: Der PV-Anteil von Voltaris' eigener Bestandskundenbasis ist in keiner der drei Research-Dateien beziffert** (naturgemäß, da es sich um interne Kundendaten handelt, nicht um öffentlich recherchierbare Marktdaten) — ohne diese Zahl lässt sich die Kernannahme der Solution Direction nicht validieren.

## 5. Strategic Positioning Signal

Die Recherche zeigt keinen Wettbewerber mit exakt Voltaris' Ausgangslage — einer etablierten Software-/Tarifmarke mit engagierter, aber "unterengagierter" Bestandskundschaft, die von dort aus in Hardware expandiert (research_market.md). 1KOMMA5° kommt strukturell am nächsten, aber aus der umgekehrten Richtung (Hardware zuerst, Tarif später aufgesetzt). Das ist eine reale, aktuell unbesetzte Positionierung — aber:

- Sie liegt eingebettet in einen **insgesamt hoch kompetitiven, konsolidierenden Markt** (fragmentiertes Herstellerfeld, deutsche Hersteller verlieren durchgängig Marktanteile an chinesische und neue Anbieter; research_market.md).
- Der übergeordnete Weg "volle Hardware-Integration" hat einen **belegt zweigeteilten Track Record im selben Jahr** (Enpal: Erfolg; Zolar: Insolvenz, strukturell ähnliches Modell) — die Positionierungslücke zu besetzen ist keine Erfolgsgarantie, sondern ein unbewiesener Weg mit realem Scheiternsrisiko.
- Es existieren **funktionierende Alternativwege**, die denselben strategischen Zweck (Engagement/Monetarisierung erhöhen) mit deutlich geringerem Kapital- und Betriebsrisiko verfolgen: Tibbers leichtgewichtiger Hardware-Fußabdruck (Pulse, ~100 €), Octopus' Plattform-Lizenzierung (Kraken) statt eigener Hardware, Kiwigrid×Tibber als hardwarefreier VPP-Zugang (research_market.md).

**Einordnung:** Das ist eher eine **enge, aktuell unbesetzte Nische innerhalb eines übergreifend umkämpften und im Ausgang zweigeteilten Feldes** als ein echter Whitespace — unbesetzt heißt hier nicht risikoarm, sondern schlicht: noch niemand hat es genau so versucht.

**Der aus der Recherche am besten gestützte, verteidigungsfähige Winkel** für Voltaris' spezifisches Profil (begrenztes Kapital, keine Hardware-/Installationskompetenz, schlanke Software-Marke, bestehende Kundenbasis) wäre eine **enger gefasste Einstiegsstrategie** als in der aktuellen Solution Direction beschrieben: Fokus zunächst explizit auf den PV-Besitz-Anteil der Bestandskundenbasis (insbesondere das Nachrüstsegment mit auslaufender EEG-Vergütung), bilanzschonend über Leasing/Abo statt Eigenkauf, mit einem bewusst geprüften leichteren Alternativpfad (Partnerschaft/Plattform statt volle eigene Installations- und Service-Organisation) als Vergleichsoption zur vollen vertikalen Integration — statt Letztere von vornherein als einzige Lösung zu setzen.

## Key Tensions & Open Questions

1. **PV-Anteil der Bestandskundenbasis ist unbekannt und entscheidend.** Die gesamte "Bestandskunden als Einstiegskeil"-Strategie steht und fällt mit dem Anteil der Kunden mit eigener PV-Anlage — ohne PV ist die Speicher-Ökonomie laut Recherche wirtschaftlich dünn bis "witzlos" (research_market.md, research_problems.md). Diese Zahl liegt vermutlich in Voltaris' eigenen Kundendaten vor, aber in keiner der drei Research-Dateien. Ohne sie ist keine belastbare ICP-Größe berechenbar — Phase 3 muss dies als zentrale, zu prüfende Annahme behandeln.

2. **Volle Hardware-Integration vs. leichtgewichtige Alternative.** Ist "liefern, installieren, warten" in voller Eigenverantwortung (Enpal-/1KOMMA5°-Modell) tatsächlich nötig, um das Engagement-Problem zu lösen — oder erreicht ein leichterer Fußabdruck (Tibber-Pulse-Ansatz, Kiwigrid-artige VPP-Partnerschaft ohne eigene Hardware-Logistik) einen relevanten Teil des Nutzens bei deutlich geringerem Kapital- und Markenrisiko? Die Recherche liefert funktionierende Präzedenzfälle für beide Wege; die aktuelle Solution Direction wägt diese Alternative nicht explizit gegen die eigenen Constraints ab.

3. **Installationskapazität ist ein Angebotsengpass, kein Ausführungsdetail.** Das bevorzugte Partnermodell setzt auf externe Installationskapazität, die strukturell knapp ist (Fachkräftemangel, dokumentierte Support-Skalierungsprobleme bei Fenecon als Präzedenzfall). Wie sichert sich Voltaris verlässlichen, qualitätskonstanten Partnerzugang in einem Markt, in dem etablierte, kapitalstärkere Player um dieselbe knappe Ressource konkurrieren?

4. **Welche Kapitalstruktur (Kauf/Leasing/Abo) passt zu Voltaris' Bilanzprofil — und wird sie kundenseitig akzeptiert?** Die Wahl entscheidet über Bilanzrisiko (Enpal-Erfolg vs. Zolar-Insolvenz als Gegenbeispiele im selben Jahr) und über die Kaufhürde für Kunden. In `input.yaml` explizit als offene Frage benannt, durch keine der drei Research-Dateien mit einer klaren Empfehlung beantwortet — nur Marktbenchmarks (69–114 €/Monat) ohne Passungsanalyse zu Voltaris.

5. **Ist "einrichten und vergessen" tatsächlich das, was Kunden überzeugt — und honorieren sie es preislich?** Die Engagement-Lücke selbst ist gut belegt (Verivox, YouGov, vzbv, research_problems.md), aber keine der drei Research-Dateien testet direkt Zahlungsbereitschaft oder Vertrauen gegenüber einer automatisierten Hardware-Lösung im Vergleich zur heutigen App. Explizite Research-Lücke — sollte vor einer Investitionsentscheidung eigens (z. B. über eigene Kundenbefragung) geschlossen werden.
