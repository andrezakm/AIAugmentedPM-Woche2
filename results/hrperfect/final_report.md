# Abschlussbericht: HR Harness — Plattform-Pivot für HRPerfect
**Unternehmen:** HRPerfect
**Analysedatum:** 2026-09-01
**Run-ID:** run_hrperfect_20260901

---

## Executive Summary

HRPerfect (70 MA, ca. 14 Mio. € Umsatz, DACH-HR-SaaS) steht unter Druck: Der Sales-Funnel liegt bei ca. 50 % des Normalniveaus, kostendeckend, aber nicht nachhaltig. Das aktuelle Horizon-2-Produkt (ROI-Analytics) ist technisch fertig, erzeugt aber keinen Kunden-Pull. Analysiert wurde die strategische Alternative **HR Harness**: eine Self-Service-Plattform, auf der DACH-HR-Abteilungen eigene KI-Agenten bauen, deployen und managen — ohne Code, mit vorintegrierter deutscher Compliance (DSGVO Art. 22, EU AI Act Anhang III, BetrVG, BDSG § 26) als eingebauter, durchsetzender statt nur informierender Schicht. Der Zugang erfolgt primär über die bestehenden 600 Job-Shop-Kundenbeziehungen, nicht über kaltes DACH-Outbound.

Die fünfstufige Analyse (Marktrecherche → Status-Quo-Analyse → Lösungs-/Technologie-/Geschäftsmodell-Hypothesen → Fünf-Perspektiven-Debatte) kommt zu einem konsistenten Bild: Die Grundrichtung ist tragfähig und wird von allen fünf Debattenperspektiven (Optimist, Kritiker, Techniker, Marktexperte, Stratege) unabhängig getragen — hier herrscht Konsens, keine Kontroverse. Der eigentliche Streitpunkt liegt woanders: **wie groß der erste Zug sein darf**, bevor er auf einer soliden Zahlenbasis steht. Der aktuell spezifizierte MVP (hypothesis_solution.md: drei kuratierte Playbooks, kompletter Builder, Compliance-Klassifikator, Freigabe-Gate, Daten-Andock-Assistent, Sandbox-Modus — alles gleichzeitig) ist bereits eine bewusste Verengung gegenüber der ursprünglichen, breiten Plattform-Ambition des Case. Drei der fünf Debattenperspektiven (Kritiker, Techniker, Stratege) halten diese Verengung unabhängig voneinander für **nicht weit genug** und fordern einen noch schmaleren, validierungs-first ersten Schritt.

**Empfehlung: CONDITIONAL GO**

Die drei wichtigsten Gründe:

1. **Zwei echte, nicht kopierbare Vermögenswerte tragen die Grundthese.** Schatten-KI-Nutzung (66–98 % der Mitarbeitenden nutzen bereits unautorisierte KI-Tools, PagerDuty-Studie 2026) ist die robusteste Nachfrage-Evidenz im gesamten Case und von allen fünf Debattenperspektiven als Konsens bestätigt. Die 600 bestehenden Kundenbeziehungen umgehen nachweislich das dokumentierte Procurement-Vertrauens-Gate, das kleine/unbekannte Anbieter unabhängig von Produktqualität aussortiert. Kein Wettbewerber kann sich beides kurzfristig kaufen.
2. **Der aktuelle MVP-Zuschnitt und die komplette kommerzielle Zahlenbasis sind unvalidiert bis teils intern widersprüchlich.** Preise (490 €–8.000+ €/Monat), TAM/SAM/SOM (670 Mio. € / 120 Mio. € / 1,0–2,5 Mio. € ARR) und die Pilot-zu-Abo-Konversionsquote sind ohne externen Beleg konstruiert; der Marktexperte der Debatte korrigiert SAM/SOM eigenständig nach unten und zeigt, dass der Starter-Preis bereits über dem einzigen verfügbaren Vergleichsanker liegt — ausgerechnet im Segment, für das der Case einen validen Kleineinstieg als harten Constraint verlangt.
3. **Fünf konkrete, aber messbare Unbekannte entscheiden über Preis, Architektur und Tempo** — und keine davon ist aktuell gemessen: Unit Economics (Token-/Rechenkosten pro Agenten-Fall), n8n-Grenzen und Embedding-/Lizenzfähigkeit, ICP-Deckungsgrad im Bestand (wie viele der 600 Kund:innen das Zielraster tatsächlich erfüllen), BetrVG-Konsultationsdauer in der Praxis, und die Pilot→Abo-Konversionsrate. Alle fünf sind laut Debatte durch definierte Mess-Schritte (Spikes, CRM-Abfrage, Primärbefragung, Pilot-Tracking) schließbar — keine davon erfordert eine weitere Argumentationsrunde.

Der Weg nach vorn ist nicht "mehr debattieren", sondern **enger bauen, schneller messen**. Details und Bedingungen unter "Overall Recommendation".

---

## Assessment Scorecard

| Dimension | Rating (1–5) | Key Finding |
|---|---|---|
| Marktchance | 3/5 | Reale, gut belegte Nachfrage (Schatten-KI) trifft auf eine Zielkategorie ohne eigene Marktgrößen-Zahl und ein zunehmend umkämpftes Feld (Workday Build bereits live). |
| Lösungsqualität | 3/5 | MVP zielt gezielt auf die stärkste Nachfrage-Evidenz, löst aber das Kernrisiko "zu strategisch, nicht akut" nicht vollständig — selbst die eigenen Analyseautoren sind über den richtigen Zuschnitt uneins. |
| Technische Machbarkeit | 2/5 | Einzelkomponenten produktionsreif, aber die empfohlene Architektur wurde vor der Validierung ihrer eigenen Grundannahmen (n8n-Eignung, Embedding-Lizenz) bereits als "empfohlen" ausgesprochen; Java-Team-Skill-Gap viermal benannt, nie in Timeline/Hiring übersetzt. |
| Kommerzielle Tragfähigkeit | 2/5 | 600-Kundenbasis ist ein echter Vorteil; Preise, TAM/SAM/SOM, CAC und Konversionsquote sind jedoch durchgehend unvalidiert — vom debatteninternen Marktexperten teils als intern widersprüchlich korrigiert. |
| Strategischer Fit | 3/5 | Konsequente Fortsetzung der Unternehmensstrategie, aber der Bauaufwand konzentriert sich auf die eine Komponente (Builder), die die eigene Recherche als nicht dauerhaft verteidigungsfähig einstuft. |
| **Gesamt** | **2,6/5** | Richtung tragfähig und mehrheitsfähig, aktueller Zuschnitt und Zahlenbasis noch nicht — Conditional Go mit engerer Erstsequenz und fünf definierten Messschritten. |

---

## Market Assessment

**Marktchance — Größe, Wachstum, Timing.** Der DACH-HR-Software-Markt wächst laut Recherche-Synthese mit ca. 12 % p. a., 72 % der Neukund:innen im DACH-Mittelstand wählen 2026 bereits Cloud-Lösungen (research_market.md §1). Der globale No-Code-AI-Plattform-Markt wird von 8,6 Mrd. USD (2026) auf über 75 Mrd. USD (2034) prognostiziert (research_market.md §1) — nicht HR-spezifisch, aber ein Beleg für strukturelles Wachstum der zugrunde liegenden Technologiekategorie. Für die eigentliche Zielkategorie — "No-Code-Agent-Builder speziell für HR, DACH" — existiert dagegen **keine einzige Marktgrößen-Zahl** in irgendeiner gesichteten Quelle; diese Schnittmenge wird in keinem Marktreport als eigene Kategorie geführt (research_market.md §1–2). Bereits die übergeordnete DACH-HR-Software-Marktgröße selbst ist widersprüchlich beziffert (1,8 Mrd. € vs. 3,2 Mrd. €, research_market.md §1, ungeklärt).

Die stärkste Nachfrage-Evidenz im gesamten Case ist indirekt, aber robust: Laut PagerDuty-Studie 2026 nutzen 66 % der Mitarbeitenden bereits unautorisierte KI-Tools trotz Kenntnis des Regelverstoßes, 88 % teilen Arbeitsinhalte mit öffentlichen KI-Tools, 98 % der Organisationen haben Mitarbeitende mit unsanktionierter KI-Nutzung (research_problems.md §2.1). Das belegt einen bereits stattfindenden, ungesteuerten Bedarf — kein hypothetisches Zukunftsszenario. Das Procurement-Vertrauens-Gate gegen kleine/unbekannte Anbieter ist ebenfalls extern bestätigt: "procurement departments often won't approve smaller firms" (research_problems.md §1.3) — ein Gate, das die 600 Bestandskundenbeziehungen bereits umgehen.

**Wichtigste Marktrisiken.** Erstens: Das Whitespace-Signal ("kein Wettbewerber vereint No-Code-Baukasten + deutsche HR-Compliance") beruht auf Abwesenheit von Gegenbeweisen in einer Quick-Recherche, nicht auf einer erschöpften Konkurrenzanalyse (research_market.md §5, explizit markiert). Zweitens, und gewichtiger: Ein ungelöster Widerspruch zwischen den eigenen Rechercheergebnissen zeigt, dass das Feld enger ist als die optimistischere Lesart nahelegt — research_technology.md §4 findet, dass Workday im Juni 2026 bereits "Workday Build" veröffentlicht hat (Developer Agent, Agent-Ready Tools, Agent Passport), strukturell dieselbe Grundidee wie HR Harness, bereits live bei einem der zwei größten globalen HR-Suite-Anbieter. Der einzig belegte Unterschied ist die fehlende deutsche Compliance-Tiefe bei Workday Build — aber keine Quelle beziffert, wie lange dieses Fenster offen bleibt. Drittens: Das regulatorische Zeitfenster (EU AI Act), das im Case implizit als Dringlichkeitstreiber mitschwingt, ist in der Recherche selbst uneinheitlich (materielle Pflichten teils ab August 2026, volle Bußgeld-Durchsetzung laut einer Quelle erst August 2027, eine dritte, nicht gegengeprüfte Quelle nennt Dezember 2027) — vor jeder kundengerichteten Dringlichkeits-Kommunikation zu verifizieren (research_market.md §4, research_technology.md §6).

**Rating: 3/5.** Der zugrunde liegende Bedarf ist real und ungewöhnlich gut belegt (Schatten-KI), das breitere Marktumfeld wächst strukturell — aber die spezifische Zielkategorie hat keine eigene Marktgrößen-Zahl, das Whitespace ist bei näherer Betrachtung ein "umkämpftes, aber noch nicht besetztes Feld" statt eines sauberen weißen Flecks (analysis_status_quo.md §5), und die regulatorische Dringlichkeitserzählung steht auf unsicherem Datum.

---

## Solution Assessment

**Passung zu den identifizierten Problemen.** Der MVP trifft die am robustesten belegten Probleme direkt: Der "Schatten-KI-Auffangkanal" (eines von drei MVP-Playbooks) übersetzt ein bereits stattfindendes, ungesteuertes Verhalten in einen governierten Kanal (hypothesis_solution.md, Feature-Set); das Freigabe-Gate mit automatisch generierter Betriebsvereinbarungs-/DPIA-Dokumentation zielt direkt auf die 3–6-monatige, mehrere Abteilungen bindende Compliance-Nachweispflicht bei KI-Beschaffung (research_problems.md §1.4); die durchgängige Preisskalierung adressiert das "Customer-Size-Mismatch"-Muster, den häufigsten Einzelgrund für Anbieterwechsel im Mid-Market (research_problems.md §1.5, §3.4).

**Kernstärken.** Die Lösungshypothese benennt selbstkritisch, dass der Builder kein Moat ist ("Ausdrücklich nicht der Builder selbst", hypothesis_solution.md §2) und verlagert die Differenzierung korrekt auf die durchsetzende Compliance-Schicht plus die 600-Kunden-Distribution — beides laut Recherche bei keinem geprüften Wettbewerber gefunden (research_technology.md §6). Die bewusste Auslassung des Zeugnis-/Dokumenten-Playbooks aus dem MVP, weil die Eignung generischer Dokumentenparser für deutsche Formate technisch ungeprüft ist (hypothesis_solution.md §3), wird vom Techniker der Debatte explizit als vorbildlicher Umgang mit einer Recherchelücke gewürdigt.

**Kritischste Risiken und Lücken.** Erstens, und laut Status-Quo-Analyse der wichtigste ungelöste Befund der gesamten Analyse: "Zu strategisch, nicht akut" ist kein Randrisiko, sondern eine mögliche Wiederholung des Musters, an dem HRPerfects eigenes ROI-Analytics-Produkt bereits scheitert — auf einer Abstraktionsebene höher (analysis_status_quo.md §3–4; research_problems.md §1.2: "Buying software without a clear question leads to dashboards nobody looks at", bei gleichzeitig guter Produktbewertung). Die drei kuratierten Playbooks mildern dies, lösen es aber nach eigenem Eingeständnis der Lösungshypothese nicht vollständig ("die Grundspannung bleibt", hypothesis_solution.md, "Offene Spannungsfelder"). Zweitens: Das am häufigsten dokumentierte Scheitern-Muster bei HR-Tech-Einführungen überhaupt — Adoptions-/Change-Management-Versagen ("nearly 1 in 4 organizations", research_problems.md §1.1) — wird durch das Self-Service-Modell nicht adressiert und laut Status-Quo-Analyse potenziell verschärft, da Konfigurationsverantwortung zusätzlich auf die Kund:innen verlagert wird (analysis_status_quo.md §3). Drittens: Die ursprüngliche GTM-Prämisse des Case ("15-Minuten-Demo überzeugt") widerspricht der Kaufreue-Evidenz (90 % der reuigen HR-Software-Käufer:innen verließen sich ausschließlich auf Herstellerangaben, research_problems.md §3.1) und wurde in der Hypothesenphase stillschweigend durch ein Consulting-Sprint-Modell ersetzt — laut Stratege ein "strategischer Konstruktionsfehler in der Ausgangsthese", der offen benannt statt klammheimlich repariert gehört. Viertens: Der Kern-Dissens dieser Analyse (siehe Overall Recommendation) — ob selbst der bereits verengte MVP noch zu breit ist.

**Rating: 3/5.** Die Lösungshypothese zeigt ungewöhnlich ehrliche Selbstreflexion und trifft die stärkste Nachfrage-Evidenz gezielt — aber das zentrale strukturelle Risiko der gesamten Analyse bleibt unaufgelöst, und die eigene Debatte zeigt, dass drei von fünf unabhängigen Perspektiven den aktuellen Bau-Zuschnitt für nicht eng genug halten.

---

## Technical Assessment

**Machbarkeits-Zusammenfassung.** Die einzelnen Bausteine sind gut belegt produktionsreif: Claude API/Agent SDK für die Einbettung in Dritt-SaaS (research_technology.md §1c), n8n für Automatisierung (§1b), MCP als wachsender Standard für die Marketplace-Schicht (§1d), Dokumentenparser als generische Kategorie (§1e). Der Techniker der Debatte bewertet den MVP-Scope selbst als "Feasible with caveats" — aber die volle "Option C"-Architektur (Compliance-Klassifikator, gegateter High-Risk-Pfad, Governed Pipeline) als spezifiziert als **"High risk"**, weil sie auf mindestens zwei unvalidierten Annahmen aufbaut, während bereits konkrete Geschäftsmodell-Zahlen darauf aufsetzen.

**Kritischste technische Risiken.** (1) **Sequenzierungsfehler an der Wurzel:** Die empfohlene Architektur wird ausgesprochen, bevor die Kernfrage geklärt ist, ob n8n überhaupt für mehrstufige, zustandsbehaftete HR-Agentenlogik ausreicht — eine explizit offene Recherchelücke (research_technology.md §1b), die im selben Dokument mit "Mittel/Hoch" bewertet, aber erst nach der Architekturempfehlung als "Spike 1" eingeplant wird (hypothesis_technology.md §2, §5). (2) **n8n-Embedding/White-Label-Fähigkeit** — ob n8n überhaupt als eingebettete, gebrandete Oberfläche lizenzrechtlich nutzbar ist — steht als letzter von fünf Meilensteinen, obwohl ein Scheitern hier die gesamte "n8n-Basis"-Prämisse ungültig macht (hypothesis_technology.md §5, Proof Point 5). (3) **Compliance-Layer-Extraktion aus dem Java-Legacy-System** wird in allen vier Hypothesendokumenten als "Aufwand unbeziffert" geführt, aber nur mit "Mittel–Hoch" bewertet; der Techniker stuft dies auf "Hoch" herauf und benennt es als wahrscheinlichen kritischen Pfad des gesamten Projekts — verteiltes Regelwissen in gewachsenen Systemen lässt sich erfahrungsgemäß nicht einfach als sauberer Service extrahieren. (4) **Der Compliance-Klassifikator hat kein sicheres Kalibrierungs-Optimum**: "Fail-closed" verhindert zwar Compliance-Verstöße, drückt aber unbekannt viele eigentlich unkritische Fälle in die langsame Governed Pipeline und untergräbt damit das Selbstbedienungs-Versprechen — kein Dokument modelliert den erwarteten Anteil betroffener Fälle. (5) **Auto-generierte Rechtsdokumente (Betriebsvereinbarung, DPIA) ohne beschriebenen juristischen Prüfworkflow** — ausgerechnet das Feature, das den Moat tragen soll, trägt ein Halluzinationsrisiko ohne dokumentierte Gegenprüfung vor Kundenauslieferung. (6) **Mandantentrennung in der n8n-Ausführungsschicht fehlt in allen vier Dokumenten vollständig**, obwohl die Pilotphase bereits mit echten Mitarbeiterdaten arbeitet. (7) **Team-Skill-Gap** (Java-Legacy-Team → n8n/Python/MCP/ML-Klassifikation) wird in vier verschiedenen Dokumenten unabhängig als "nicht durch Recherche prüfbar" benannt, aber nie in Timeline, Hiring-Entscheidung oder Spike-Priorität übersetzt.

**Rating: 2/5.** Die Grundbausteine sind solide, aber die empfohlene Architektur enthält mehrere fundament-invalidierende Unbekannte (n8n-Eignung, Embedding-Lizenz), die aktuell nach statt vor dem Architektur-Commitment geprüft werden, plus einen wahrscheinlich unterschätzten kritischen Pfad (Compliance-Layer-Extraktion) und einen wiederholt benannten, nie aufgelösten Skill-Gap. Das ist kein Beleg für Unmachbarkeit, sondern für eine falsch sortierte Validierungsreihenfolge — behebbar, aber im aktuellen Zuschnitt nicht geschehen.

---

## Commercial Assessment

**ICP-Qualität und Erreichbarkeit.** Das gewählte ICP (250–1.500 MA, HR-Team 5–20 VZK, etablierter Betriebsrat, aktive Job-Shop-Kundenbeziehung, hypothesis_business_model.md §1) ist formal scharf und sofort gegen ein CRM operationalisierbar. Der Marktexperte der Debatte weist jedoch nach, dass es **nachfrageseitig nicht belegt** ist: Die robusteste Nachfrage-Evidenz (PagerDuty-Schatten-KI-Studie) stammt aus Unternehmen ab 500 Mio. USD Umsatz außerhalb DACH — nicht aus dem gewählten ICP-Band; das klarste Whitespace-Signal (SMB-Unterversorgung im Agent-Builder-Markt) zeigt auf ein anderes, kleineres Segment als das gewählte. Die vier Begründungen für das ICP (Procurement-Gate umgangen, Selbstbedienungskapazität, Mitbestimmungserfahrung, Referenzierbarkeit) sind alle Risiko-/Geschwindigkeits-Aussagen, keine Nachfrage-Aussagen. Entscheidend und bislang ungeklärt: **Welcher Anteil der 600 Bestandskund:innen erfüllt überhaupt das Filterraster (Größe UND aktiver Betriebsrat)?** Das ist eine offene CRM-Abfrage, keine Rechercheaufgabe — und ohne diese Zahl steht jede SOM-Berechnung auf Sand (Marktexperten-Sektion, debate_round_1.md).

**Geschäftsmodell-Stärke.** Die Empfehlung (Plattformgebühr + Nutzungsgebühr nach Agentenzahl/Fallvolumen, nicht token-basiert, ergänzt um Consulting-as-Acquisition) ist strategisch konsistent mit dem harten Case-Constraint der durchgängigen Preisskalierung. Aber: Es existiert **kein einziger Token-/Rechenkosten-Benchmark pro HR-Agenten-Fall** in irgendeiner der vier Recherchedateien (research_technology.md §3) — die zentrale Prämisse des Geschäftsmodells ("Nutzungsgebühr statt Token-Preis lässt sich profitabel kalibrieren") ist damit weder bestätigt noch widerlegt, sondern schlicht ungemessen. Die eigene n8n-Kostenkurve springt zudem statt linear zu verlaufen (24 $ → 60 $ → 800 $ → 2.000–3.000+ $/Monat) — ein möglicher Widerspruch zur versprochenen glatten Kundenpreisskalierung. Der Marktexperte rechnet die Preistabelle gegen die einzigen verfügbaren Anker durch: Der Starter-Tier (490 €/Monat) liegt umgerechnet bei ca. 9,80 € PEPM (bei 50 MA) — bereits über dem recherchierten Anker für Einstiegs-Punktlösungen (2–8 USD PEPM, research_problems.md §3.2), ausgerechnet im Segment, für das der Case einen validen Kleineinstieg als nicht verhandelbaren Constraint verlangt. Kein einziger öffentlicher Preispunkt für ein vergleichbares Produkt wurde in der gesamten Recherche gefunden (research_market.md §5) — die komplette Preistabelle ist unvalidierte Hypothese.

**Go-to-Market-Viabilität.** Der einzige kommerzielle Vorteil, der auf einem bereits vorhandenen statt zu beweisenden Vermögenswert beruht, sind die 600 Bestandskundenbeziehungen (research_problems.md §1.3, in der Debatte durchgehend als einziger extern belastbarer Vorteil bestätigt). Alles Weitere ist unmodelliert oder unbelegt: CAC des Consulting-Sprints ist an keiner Stelle beziffert; die Pilot→Abo-Konversionsquote wird von der Business-Modell-Hypothese selbst als "reine Case-Konstruktion, in keiner Recherchedatei evidenziert" eingeordnet (hypothesis_business_model.md §6); drei gleichzeitige GTM-Bewegungen (bestehender Enterprise-Zyklus + neuer Consulting-Sprint-Vertrieb + perspektivisches Self-Serve) werden ohne Kapazitätsprüfung für ein 70-Personen-Unternehmen bei 50 % Funnel-Auslastung verlangt; und die BetrVG-Mitbestimmungsreibung ist laut Marktexperte strukturell wiederkehrend statt einmalig — sie bremst damit nicht nur die Erstkonversion, sondern auch die Konto-Expansionslogik, auf der das SOM-Wachstum direkt aufbaut.

**Rating: 2/5.** Der 600-Kunden-Vorteil ist real und einzigartig — aber praktisch jede quantitative Aussage im Geschäftsmodell (Preise, TAM/SAM/SOM, CAC, Konversionsquote) ist entweder unvalidierte Konstruktion oder wird vom debatteninternen Marktexperten mit konkreten Gegenrechnungen als zu optimistisch korrigiert. Das ist die am schwächsten belegte Dimension der gesamten Analyse.

---

## Strategic Assessment

**Strategischer Fit.** Auf Anspruchsebene ist die Passung nahezu tautologisch: HR Harness ist wörtlich Horizon 2 aus der Unternehmensstrategie, Kannibalisierung von Job Shop ist explizit sanktioniert, Job Shop finanziert den Aufbau aus einer kostendeckenden Position heraus. Der Stratege der Debatte weist jedoch zurecht darauf hin, dass diese Übereinstimmung nichts darüber aussagt, ob der *Zuschnitt* der Lösung strategisch klug ist (Stratege-Sektion, debate_round_1.md).

**Verteidigungsfähigkeit und Moat-Potenzial.** Die Moat-Analyse der Debatte zeigt ein klares, unbequemes Muster: Von sechs geprüften Moat-Kandidaten tragen nur zwei — Distribution (600 Kundenbeziehungen, bereits vorhanden) und regulatorisches Domänenwissen (Compliance-Tiefe, bei keinem geprüften Wettbewerber gefunden, aber realistisch 12–24 Monate haltbar, bevor ein ressourcenstarker Wettbewerber nachzieht). Technologie/Builder, Netzwerkeffekte und Marketplace tragen laut eigener Recherche **nicht** — der Builder ist "vibe-codebar" (eigener Case-Präzedenzfall: Wiener Voice-AI-Plattform, in einer Woche kopiert), und die MCP-Marketplace-Schicht baut auf einem offenen Standard auf, den auch Wettbewerber nutzen können. Der schärfste, bislang nirgends explizit benannte Befund der Debatte: Für Workday ist das Zukaufen deutscher Rechts-/Compliance-Expertise eine kleinere, schnellere Investition als für HRPerfect der Aufbau einer kompletten neuen Plattform-Engineering-Fähigkeit (Python, n8n-Agentenlogik, MCP) auf einem Java-Legacy-Team — eine **asymmetrische Wettrenn-Dynamik zulasten von HRPerfect**, die der Stratege auf 12–24 Monate schätzt (nicht recherchebelegt, explizit als eigene Einschätzung markiert).

**Langfristige Positionierungsqualität.** Der Stratege der Debatte skizziert zwei klar unterschiedene Drei-bis-Fünf-Jahres-Bilder: **Bild A** (volle Plattform wie spezifiziert) macht HRPerfect zu einer strukturell unterlegenen "kleineren Workday", die dauerhaft gegen Konkurrenz mit 10- bis 100-fachem F&E-Budget in exakt der Schicht antreten muss, die laut eigener Recherche nicht dauerhaft verteidigungsfähig ist. **Bild B** (schmalerer, compliance-layer-geführter Zug: lizenzierbare Compliance-Intelligenz plus fokussiertes Portfolio governed Point-Solution-Agenten) baut vollständig auf dem einzigen bestätigten, unbestrittenen Moat auf und vermeidet die direkte Konfrontation mit Oracle/SAP/Workday auf deren Terrain. Der Stratege bewertet Bild B als die tragfähigere Position für ein Unternehmen dieses Profils — schließt Bild A damit nicht aus, sondern sieht Bild B als plausiblen Weg dorthin, finanziert aus einer Position der Stärke statt aus der aktuellen Dringlichkeitslage.

**Rating: 3/5.** Die Grundrichtung ist die konsequente, richtige nächste Bewegung aus der eigenen Strategie heraus. Aber der aktuelle Bau-Zuschnitt konzentriert den Entwicklungsaufwand eines 70-köpfigen Java-Hauses primär auf die eine Komponente (Builder-Infrastruktur), die die eigene Recherche als nicht dauerhaft verteidigungsfähig einstuft, während der einzige nachweislich einzigartige Vorteil noch nicht als eigenständiger, schneller monetarisierbarer erster Zug sequenziert ist — ein struktureller Zielkonflikt zwischen Moat-Lage und Bau-Priorität, der in der Debatte einstimmig erkannt, aber im aktuellen Zuschnitt nicht aufgelöst wird.

---

## Overall Recommendation

**Empfehlung: CONDITIONAL GO**

### Warum nicht GO, PIVOT oder NO-GO

Kein NO-GO: Alle fünf unabhängigen Debattenperspektiven bestätigen dieselbe Grundthese — ein bereits stattfindender, gut belegter Bedarf (Schatten-KI) trifft auf einen nicht kopierbaren Distributionsvorteil (600 Kundenbeziehungen). Kein Dokument und keine Debattenperspektive liefert einen fatalen, stoppwürdigen Befund; der Kritiker selbst stuft "Annahme-Stapel-Kollaps" und "Ressourcen-Mismatch" nur als "nah dran" an fatal ein, nicht als bereits fatal (Kritiker-Sektion, debate_round_1.md).

Kein PIVOT: Die Richtung selbst wird von keiner der fünf Perspektiven infrage gestellt — der Dissens betrifft laut Moderator-Fazit "überwiegend das Ausmaß und die Reihenfolge des ersten Zugs, nicht die Grundrichtung" (debate_round_1.md, Moderator-Synthese). Ein Pivot wäre nur gerechtfertigt, wenn die Grundthese selbst widerlegt wäre — das ist nicht der Fall.

Kein einfaches GO: Der aktuelle MVP-Zuschnitt und praktisch die gesamte kommerzielle Zahlenbasis sind unvalidiert; ein uneingeschränktes GO würde Ressourcen in eine Architektur- und Preis-Reihenfolge binden, die selbst die eigenen Analyseautoren mehrheitlich für falsch sortiert halten.

### Der Kern-Dissens — und wie er aufzulösen ist

Die Debatte zeigt einen klaren Bruch zwischen zwei Lagern, der sich direkt in die Bedingungen unten übersetzt:

- **Position "aktueller Zuschnitt genügt"** (Optimist, Business-Modell-Hypothese): Der bereits verengte MVP (drei kuratierte Playbooks statt offener Baukasten-Erzählung) ist eine ausreichende Korrektur des "zu strategisch, nicht akut"-Risikos.
- **Position "noch enger"** (Kritiker, Techniker, Stratege — unabhängig voneinander zum selben Schluss gekommen): Der MVP bündelt weiterhin zwei unterschiedliche Wetten in einem Release — "beweisen, dass der Markt das will" und "die generische Plattform-Infrastruktur bauen" (Competency Layer, Klassifikator, Builder, Freigabe-Gate, Daten-Andock, Sandbox, gleichzeitig für drei Playbooks). Der Stratege schlägt konkret vor: **ein einzelner, vorkonfigurierter Schatten-KI-Auffangkanal-Agent plus automatischer Betriebsvereinbarungs-/DPIA-Dokumentationsgenerator — kein Builder, kein Klassifikator für freie Konfiguration, kein Sandbox-Modus —, verkauft in 15–20 der 600 Kundenbeziehungen.** Der Techniker fordert unabhängig davon einen einzigen integrierten vertikalen Durchstich statt fünf isolierter Spikes, mit umgekehrter Validierungsreihenfolge (n8n-Grenzen und Embedding-Lizenz zuerst, nicht zuletzt).

**Diese Synthese übernimmt die "noch enger"-Position als Bedingung für das GO.** Begründung: Sie ist von drei unabhängigen Perspektiven mit unterschiedlichem Mandat (Risiko, Technik, Strategie) getragen, sie konzentriert den ersten Bauaufwand auf die Komponente, die tatsächlich Moat trägt (Compliance-Dokumentation), statt auf die Komponente, die laut eigener Recherche ohnehin nicht verteidigungsfähig ist (Builder), und sie bleibt im Negativfall wertvoll — eine funktionierende Compliance-Dokumentationsgenerierung ist eigenständig verwertbar, ein unfertiges Builder-Engine-Investment ist es laut Stratege nicht.

### Bedingungen für GO

1. **Ersten Zug neu zuschneiden, bevor Ressourcen gebunden werden.** Statt des vollen MVP aus hypothesis_solution.md §3 zuerst: ein vorkonfigurierter Schatten-KI-Auffangkanal-Agent plus Freigabe-Gate-Dokumentationsgenerator, verkauft in 15–20 ICP-passende Bestandskund:innen. Builder, Klassifikator für freie Konfiguration und Sandbox-Modus folgen erst nach den Messungen aus Bedingung 2.
2. **Die fünf unmeasured Unbekannten vor jeder Preis-/Architektur-Fixierung messen** (siehe "Key Open Questions" unten) — keine davon erfordert weitere Debatte, alle sind durch definierte Schritte (Spike, CRM-Abfrage, Primärbefragung, Pilot-Tracking) innerhalb weniger Wochen bis Monate schließbar.
3. **Technische Validierungsreihenfolge umkehren.** n8n-Grenztest für mehrstufige Agentenlogik UND n8n-Embedding-/Lizenzfähigkeit zuerst klären (fundament-invalidierende Unbekannte) — nicht, wie aktuell, als letzter von fünf Meilensteinen. Bei Scheitern früh auf Alternative umsteuern, nicht erst nach Kundenauslieferung.
4. **Zwei konkrete Compliance-/Haftungslücken vor jeder Kundenauslieferung schließen:** einen juristischen Prüfworkflow für automatisch generierte Rechtsdokumente (Betriebsvereinbarung, DPIA) einführen — Auslieferung als "Entwurf zur Prüfung", nicht als fertiges Dokument — sowie eine explizite Mandantentrennungs-Architektur für die Ausführungsschicht festlegen, bevor der erste Pilot mit echten Mitarbeiterdaten läuft.
5. **Team-Skill-Gap in eine Entscheidung verwandeln, nicht in eine wiederholte Fußnote.** Internes Kompetenz-Audit (Python-Agentenorchestrierung, n8n, MCP, compliance-nahe Klassifikationslogik) vor Festlegung auf die volle Architektur, mit explizitem Hiring- oder Trainingsplan.

### Die drei wichtigsten nächsten Schritte (unabhängig von der Empfehlung)

1. **CRM-Abfrage: ICP-Deckung im Bestand.** Wie viele der 600 Kund:innen erfüllen das Filterraster (250–1.500 MA UND aktiver Betriebsrat)? Interne Datenfrage, keine Recherchelücke — sollte in Tagen, nicht Wochen beantwortbar sein und geht jeder GTM-Priorisierung voraus.
2. **Integrierter vertikaler Durchstich statt fünf isolierter Spikes.** Playbook "Schatten-KI-Auffangkanal" end-to-end durch den tatsächlichen Produktionspfad bauen (Datenandockung, n8n-Ausführung, echter Compliance-Layer-API-Endpunkt, Audit-Log) und dabei realen Claude-API-Tokenverbrauch messen — beantwortet Unit Economics, n8n-Eignung und Compliance-Layer-Extraktionsaufwand in einem Durchgang (Techniker-Empfehlung).
3. **Erste 5–10 Piloten mit hartem Tracking starten**, nicht mit finalen Listenpreisen: Time-to-first-live-agent, tatsächliche BetrVG-Konsultationsdauer, Pilot→Abo-Konversionsquote gegen eine vorab festgelegte Zielgröße (z. B. ≥ 50 %) messen — nicht schätzen.

---

## Key Open Questions

Die fünf wichtigsten offenen Fragen entsprechen den fünf in der Debatte identifizierten, gemeinsam ungemessenen Unbekannten. Alle fünf werden von allen fünf Debattenperspektiven als Konsens-Wissenslücke benannt (nicht als Streitpunkt) — der Dissens betrifft nur, wie eng gebaut werden darf, *bevor* sie beantwortet sind.

| Frage | Wie beantworten | Priorität |
|---|---|---|
| Wie hoch ist der tatsächliche Claude-API- und n8n-Ausführungskostenverbrauch pro typischem HR-Agenten-Fall (Unit Economics)? | Spike 2: realen Tokenverbrauch (inkl. Cache-/Batch-Rabatt) für 3–5 repräsentative Fälle messen, bevor Endpreise fixiert werden (hypothesis_technology.md §5) | Hoch |
| Trägt n8n mehrstufige, zustandsbehaftete HR-Agentenlogik, und ist n8n als eingebettete, gebrandete Oberfläche technisch/lizenzrechtlich nutzbar (n8n-Grenzen/Embedding)? | Spike 1 kombiniert mit Proof Point 5: einen nicht-trivialen Use-Case direkt in n8n nachbauen; Lizenzfrage für Embedding/White-Label vorab mit n8n klären | Hoch |
| Wie viele der 600 Bestandskund:innen erfüllen tatsächlich das ICP-Filterraster (250–1.500 MA UND aktiver Betriebsrat)? | Direkte CRM-Abfrage — keine externe Recherche nötig, sollte vor jeder GTM-Priorisierung vorliegen | Hoch |
| Wie lange dauert der BetrVG-Konsultationsprozess in der Praxis, beim Erstagenten und bei Folgeagenten? | Primärbefragung: 3–5 Bestandskund:innen mit aktivem Betriebsrat zu typischen Konsultationszeiten für neue Software befragen; anschließend an echten Piloten messen | Mittel-Hoch |
| Konvertieren bezahlte Consulting-Pilot-Sprints nach den ersten 5–10 Piloten mit einer belastbaren Quote in Plattform-Abos (Pilot→Abo-Konversion)? | Tracking der ersten 5–10 Piloten gegen eine vorab festgelegte Zielquote (z. B. ≥ 50 %); erst danach Umsatzplanung auf dieser Zahl aufbauen | Mittel |

---

## Document Index

- `research_market.md` — Marktrecherche (Phase 1)
- `research_technology.md` — Technologierecherche (Phase 1)
- `research_problems.md` — Marktproblem-Recherche (Phase 1)
- `analysis_status_quo.md` — Status-Quo-Analyse (Phase 2)
- `hypothesis_solution.md` — Lösungshypothese (Phase 3)
- `hypothesis_technology.md` — Technologiehypothese (Phase 3)
- `hypothesis_business_model.md` — Geschäftsmodell-Hypothese (Phase 3)
- `debate_round_1.md` — Fünf-Perspektiven-Debatte (Optimist, Kritiker, Techniker, Marktexperte, Stratege) inkl. Moderator-Synthese (Phase 4) — einzige, finale Runde
