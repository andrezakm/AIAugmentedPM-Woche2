# Lösungshypothese

> Basis: research_market.md, research_problems.md, analysis_status_quo.md
> Unternehmen: HRPerfect | Datum: 2026-09-01

## 1. Konkrete Lösungsbeschreibung

**Produkttyp:** Vertikale No-Code-SaaS-Plattform mit einer rechtlich durchsetzenden (nicht nur informierenden) Compliance-Schicht, ergänzt um ein kuratiertes Marketplace-Ökosystem und einen bezahlten Consulting-Einstiegspfad. HR Harness ist explizit kein Marktplatz vorgefertigter Agenten — das Modell, das SAP Joule, Workday Build und Oracle AI Agent Studio bereits fahren (research_market.md §3b, research_technology.md §4) — und kein generischer, branchenneutraler Agent-Builder (n8n, Copilot Studio, Relevance AI u. a., research_market.md §3a). Es ist ein Baukasten mit Werksvorgaben: HR-Teams bauen ihre eigenen Agenten, starten dabei aber nicht vor einer leeren Fläche, sondern mit editierbaren Playbooks für die am besten belegten HR-Painkiller.

**Für wen:** Primär HR-Verantwortliche (Ein-Personen-HR-Generalist:in bis HR-Leitung) in DACH-Unternehmen von 50 bis 5.000+ Mitarbeitenden. Erste Welle: die bestehenden 600 Job-Shop-Kundenbeziehungen — nicht der kalte DACH-Markt. Sekundär und ausdrücklich nicht Teil des MVP: HR-Software-Vendoren und Implementierungspartner als spätere White-Label-Lizenznehmer (Case-Vorgabe, target_market).

**In welchem Kontext:** Zwei Rechercheergebnisse diktieren die Einstiegserzählung, statt die im Case skizzierte "baue deine eigenen Agenten"-Botschaft direkt als Werbeversprechen zu verwenden. Erstens erwähnen nur 4,8 % der HR-Tech-Käufer:innen 2026 "KI" proaktiv in Evaluierungsgesprächen, während "Automatisierung" mit über 50 % Top-Priorität ist (research_problems.md §3.3) — Käufer:innen suchen Ergebnisse, keine Technologie-Kategorie. Zweitens ist Schatten-KI die am robustesten belegte Nachfrage-Evidenz im gesamten Case (66–98 % ungesteuerte KI-Nutzung je nach Messung, PagerDuty-Studie 2026, research_problems.md §2.1). HR Harness tritt deshalb nicht mit der abstrakten Baukasten-Erzählung an, sondern mit einem konkreten ersten Angebot: die KI-Nutzung, die in den Kundenunternehmen ohnehin schon informell stattfindet, in einen governierten, dokumentierten, deutschem Recht entsprechenden Kanal zu überführen. Die "baue selbst"-Fähigkeit ist von Tag 1 an technisch vorhanden — sie ist nur nicht die Eingangstür.

### Kernfähigkeiten (Core Capabilities)

**1. HR Competency Layer als durchsetzende Middleware, nicht als Nachschlagewerk.** Jeder im Builder konfigurierte Agent läuft automatisch durch eine Klassifizierungsschicht, die prüft, ob er DSGVO Art. 22, EU-AI-Act-Anhang-III oder BetrVG §87-Kriterien berührt (z. B. Verarbeitung personenbezogener Bewerber- oder Mitarbeiterdaten, überwachungsgeeignete Funktionen). Trifft das zu, erzwingt das System automatisch die passenden Bausteine — Human-in-the-loop-Schritt, Protokollierung, Freigabe-Gate (Punkt 3) — statt sie nur als Empfehlung anzuzeigen. Das setzt den in der Technologierecherche beschriebenen Trend zu Gateway-/Kontext-Ebene-Enforcement um (research_technology.md §1g, §4) und macht aus HRPerfects bereits vorhandenem Compliance-Wissen (laut Case größtenteils vorhanden, muss API-fähig werden) den strukturellen Kern des Produkts statt eine Zusatzdokumentation.

**2. Geführter No-Code-Builder mit editierbarer Playbook-Bibliothek (auf n8n-Basis).** Kein leeres Canvas als Startpunkt. HR-Anwender:innen wählen ein Playbook (siehe Feature-Set), beschreiben in natürlicher Sprache Abweichungen von ihrem Fall ("bei uns gilt zusätzlich Regel X"), und der Builder passt Workflow und Konfiguration live an — das Claude-Code-Erlebnis für HR-Fachbereiche, wie im Case beschrieben, aber mit einem Sicherheitsnetz gegen die leere Seite.

**3. Freigabe-Gate mit automatisch generierter Mitbestimmungs-Dokumentation.** Bevor ein als mitbestimmungs- oder hochrisikorelevant klassifizierter Agent live geschaltet werden kann, generiert das System automatisch einen Betriebsvereinbarungs-Entwurf, eine DPIA-Kurzdokumentation und ein EU-AI-Act-Anhang-IV-Dokumentationsgerüst, inklusive Sign-off-Tracking. Das verwandelt die in der Statusanalyse als Geschwindigkeits-Risiko identifizierte BetrVG-Mitbestimmungspflicht (analysis_status_quo.md, Spannungsfeld 2) von Vertriebs-Reibung in ein sichtbares Produkt-Feature — laut Recherche bei keinem geprüften Wettbewerber gefunden, auch nicht bei Workday Build oder Oracle AI Agent Studio (research_technology.md §6).

**4. Daten-Andock-Assistent statt Integrationsprojekt.** E-Mail-Postfach-Monitoring, CSV-/Excel-Import und generische Webhooks als Standard-Andockwege — die Kanäle, die HR-Teams laut Case bereits als Workaround nutzen. Ergänzt um kuratierte (nicht garantierte) Konnektoren zu den größten DACH-HRIS über den bereits reifen iPaaS-Drittanbietermarkt (Workato, Boomi, Kombo, Apideck, Truto — research_technology.md §2, §5), passend zum Case-Constraint "keine Integrationsgarantien".

**5. Marketplace/Ökosystem auf MCP-Basis — architektonisch von Anfang an angelegt, funktional ab V2.** MCP ist kein hypothetisches Vorbild, sondern ein real existierender, schnell wachsender Standard (97 Mio. monatliche SDK-Downloads bis März 2026, research_technology.md §1d, §4). Jeder Marketplace-Agent läuft durch dieselbe Competency Layer wie ein selbst gebauter — Kuratierung/Validierung ist HRPerfects Aufgabe, nicht der Bau jeder Integration.

### User-Journey-Skizze

**Minuten 1–10 — die "Show, don't tell"-Situation (Sandbox, kein Produktivsystem):**
1. HR-Verantwortliche:r sitzt mit einer HRPerfect-Person (bezahlter Consulting-Einstieg, kein Self-Serve-Erstkontakt) vor einer Sandbox mit synthetischen Testdaten.
2. Wählt aus der Playbook-Bibliothek das Szenario, das dem eigenen akuten Problem am nächsten kommt — meist der Mitarbeiter-Self-Service-Assistent oder der Schatten-KI-Auffangkanal (siehe Feature-Set).
3. Nennt eine eigene Abweichung ("bei uns gilt zusätzlich…"); der Builder passt den Workflow live an. Die Competency Layer markiert in Echtzeit sichtbar, welche Compliance-Bausteine greifen würden.
4. Stellt dem Agenten live eine eigene Testfrage, sieht Antwort plus Herleitung/Quelle.
5. Sieht am Ende der Demo den automatisch erzeugten Entwurf: Betriebsvereinbarungs-Kapitel plus Kurz-DPIA für genau diesen Agenten — der konkrete Übergabepunkt in einen echten Beschaffungsprozess, nicht nur ein Wow-Moment.

**Woche 1–4 — bezahltes Onboarding (Consulting als Akquise-Funnel, kein Selbstzweck):**
6. Vertragsabschluss auf dem passenden Einstiegsplan; HRPerfect-Consultant begleitet die Daten-Andockung über den vorhandenen Kanal des Kunden (CSV-Export oder E-Mail-Postfach) — kein Migrationsprojekt.
7. Der im Demo konfigurierte Agent läuft 1–2 Wochen im Beobachtungsmodus auf echten, aber noch nicht live wirksamen Daten.
8. Parallel dazu, nicht danach: Das Freigabe-Gate liefert die Betriebsvereinbarungs-Unterlagen für die Betriebsratsabstimmung, wo ein Betriebsrat existiert.
9. Live-Schaltung des ersten Agenten; Audit-Log läuft ab Tag 1 mit.
10. Ab Monat 2: Das HR-Team konfiguriert selbständig einen zweiten, eigenen Anwendungsfall im Builder — der Moment, in dem aus "HRPerfect hat uns einen Agenten gebaut" tatsächlich "wir bauen selbst" wird.

## 2. Wertversprechen

**Kernwert (ein Satz):** HR Harness überführt KI-Nutzung, die in DACH-HR-Abteilungen ohnehin schon unkontrolliert stattfindet, in selbst gebaute Agenten, die von der ersten Sekunde an deutschem Arbeits- und Datenschutzrecht entsprechen — ohne dass das HR-Team dafür auf Legal, IT oder einen externen Dienstleister warten muss.

**Differenzierung:** Ausdrücklich nicht der Builder selbst — dieser ist laut Technologierecherche eine "Commodity"-Fähigkeit, die sich per Vibe-Coding nachbauen lässt (Präzedenzfall im Case selbst: die Wiener Voice-AI-Plattform, in einer Woche kopiert; research_technology.md §4). Die Differenzierung liegt in der Kombination zweier Elemente, die beide einzeln schwer von außen zu kopieren sind: (a) eine Compliance-Tiefe, die als durchsetzende Architektur — nicht als Nachschlagewerk — in jeden Agenten eingebaut ist, insbesondere das BetrVG-Freigabe-Gate, das laut Recherche bei keinem geprüften Wettbewerber gefunden wurde, einschließlich Workday Build und Oracle AI Agent Studio (research_technology.md §6, analysis_status_quo.md Abschnitt 5); und (b) die 600 bestehenden Kundenbeziehungen als Umgehung des dokumentierten Procurement-Vertrauens-Gates, das kleine/unbekannte Anbieter unabhängig von Produktqualität aussortiert (research_problems.md §1.3). Kein geprüfter Wettbewerber — weder generische Builder noch HR-Suiten noch HR-AI-Startups — vereint beides.

**Bindungshebel (Retention Hook):** Mit jedem live geschalteten Agenten wächst ein Audit- und Dokumentations-Trail (Freigaben, Betriebsvereinbarungen, Ausführungsprotokolle), der exakt die Nachweispflicht erfüllt, die externe Vendor-Assessments laut Recherche 3–6 Monate kosten (research_problems.md §1.4). Ein Unternehmen, das diesen Prozess einmal mit HR Harness durchlaufen hat, verliert bei einem Anbieterwechsel nicht nur den Agenten, sondern die gesamte Compliance-Historie dahinter — ein Wechsel bedeutet, den Betriebsrats-Prozess neu zu starten.

## 3. Feature-Set

### MVP

Der MVP muss den Kernwert mit dem geringstmöglichen Umfang liefern und gleichzeitig die BetrVG-/DSGVO-Anforderungen von Anfang an erfüllen — nicht nachträglich anflicken, weil genau dieses nachträgliche Anflicken laut Recherche der Unterschied zwischen HRPerfect und US-Wettbewerbern sein soll (research_technology.md §6).

- **HR Competency Layer v1 (durchsetzend, nicht informierend):** Automatische Klassifizierung jeder Agent-Konfiguration gegen DSGVO Art. 22 / EU-AI-Act-Anhang-III / BetrVG §87; erzwingt bei Treffer automatisch Human-in-the-loop-Schritt und Protokollierung. Baut auf HRPerfects vorhandenem Compliance-Wissen auf (API-Exponierung, nicht Neubau) — der Aufwand dafür ist in keiner der drei Recherchedateien beziffert und muss vor Terminplanung geschätzt werden.
- **Drei editierbare Playbooks, bewusst nicht acht:**
  1. *Mitarbeiter-Self-Service-Assistent* — RAG-basierter Chat über hochgeladene HR-Dokumente (Urlaubsregeln, Reisekosten, Weiterbildung, Policies), direktes Analogon zum recherchierten DACH-Praxisbeispiel mit ca. 40 % Ticket-Entlastung (research_problems.md §2.3).
  2. *Schatten-KI-Auffangkanal* — ein sanktionierter, protokollierter Kanal für Aufgaben, die Mitarbeitende laut PagerDuty-Studie schon heute in öffentliche KI-Tools eingeben (Stellenanzeigen-Entwürfe, Formulierungshilfen, interne Kommunikationsentwürfe), mit Audit-Log statt Verbot.
  3. *Bewerbungs-Vorsichtungs-Assistent* — Ranking und Klartext-Begründung pro Kandidat:in, Entscheidung bleibt beim Menschen (Art.-22-konform, durch die Competency Layer erzwungen).
  Bewusst nicht im MVP: ein Zeugnis-/Vertragsentwurf-Playbook, obwohl im Case explizit als Competency-Layer-Scope genannt — die Technologierecherche bestätigt VLM-Dokumentenparser nur generisch als produktionsreif, nicht spezifisch geprüft für deutsche Zeugnis-Formulierungscodes (research_technology.md §1e). Vor Aufnahme wäre ein technischer Prüf-Spike nötig.
- **Geführter Builder (n8n-Basis):** Formularbasierte Konfiguration je Playbook, editierbar per natürlichsprachlicher Anweisung. Kein leeres Canvas als Einstieg.
- **Freigabe-Gate v1:** Automatisch generierter Betriebsvereinbarungs-Entwurf, DPIA-Kurzdokumentation und AI-Act-Anhang-IV-Grundgerüst bei Hochrisiko-/Mitbestimmungs-Klassifizierung; Sign-off-Tracking.
- **Daten-Andock-Assistent v1:** E-Mail-Postfach-Monitoring, CSV-/Excel-Import, generischer Webhook. Keine tiefen nativen HRIS-Konnektoren im MVP.
- **Audit-Log je Agent:** Jede Ausführung, jede automatische Klassifizierungsentscheidung, jede Freigabe protokolliert und exportierbar — für Betriebsrats- oder Aufsichtsanfragen.
- **Sandbox-/Demo-Modus:** Synthetische Testdaten, getrennt vom Produktivmodus — der technische Unterbau für die "Show, don't tell"-Vertriebssituation, ohne echte Mitarbeiterdaten in der Verkaufsphase zu riskieren.

Explizit außerhalb des MVP-Scopes: Marketplace/Ecosystem (Kuratierung braucht zuerst Volumen), White-Label für Partner, EU-souveräne Modellschicht als Alternative zu Claude, tiefe native HRIS-Konnektoren, People-Analytics-Dashboards. Letzteres ist eine bewusste Auslassung: genau diese Kategorie ist das Muster, an dem HRPerfects eigenes ROI-Analytics-Produkt laut Statusanalyse bereits scheitert (analysis_status_quo.md Abschnitt 3).

### V2 (Verteidigungsebene)

- **Marketplace/Ecosystem live, MCP-basiert:** Kuratierte Skills/Plugins Dritter; jeder Marketplace-Agent durchläuft dieselbe Competency Layer wie ein selbst gebauter. HRPerfect kuratiert und validiert, garantiert keine Einzelintegration (Case-Constraint).
- **"Sovereign Mode":** Wählbare EU-gehostete Modellschicht (z. B. Mistral AI oder Aleph Alpha/PhariaAI — beide production-ready mit voller EU-Datenresidenz, research_technology.md §1f) als Alternative/Ergänzung zu Claude API, für Kund:innen/Segmente mit besonderer CLOUD-Act-Sensitivität (öffentlicher Sektor, stark regulierte Branchen, Großkund:innen mit eigenen Datenhoheits-Vorgaben). Löst den in der Statusanalyse benannten Zielkonflikt zwischen US-LLM-Layer und "DACH-nativ"-Versprechen architektonisch statt nur kommunikativ (analysis_status_quo.md Abschnitt 2, Spannungsfeld 5).
- **Quartalsweiser Bias-/Fairness-Report je Agent:** Setzt den Trend zu Gateway-/Kontext-Ebene-Guardrails um (research_technology.md §1g) und liefert einen zusätzlichen Vertrauensanker gegen die dokumentierte Skepsis von HR-Tech-Käufer:innen (research_problems.md §3.1).
- **Erweiterte, offiziell gepflegte HRIS-Konnektoren** (Personio, SAP SuccessFactors, Workday; DATEV-Anbindung als offene Frage, siehe Lücken) als Marketplace-Einträge, Community-/Partner-getrieben statt HRPerfect-Eigenbau.
- **Nutzungsdaten-Feedback-Loop:** Aggregierte, anonymisierte Muster, welche Playbook-Varianten in der Praxis am robustesten laufen, fließen in bessere Standardvorlagen zurück — der Anfang eines Datennetzwerkeffekts, der in der Technologierecherche als eines der wenigen vibe-coding-resistenten Moat-Elemente genannt wird (research_technology.md §4).
- **White-Label-Lizenzmodell** für HR-Software-Vendoren und Implementierungspartner (Case-Zielgruppe, sekundär).

### Langfristige Vision

Setzt sich HR Harness durch, verschiebt sich HRPerfects Rolle vom Anbieter einzelner HR-Produkte zum Compliance- und Ausführungs-Betriebssystem, auf dem DACH-HR-Abteilungen selbst entscheiden, was sie automatisieren. Die Competency Layer wird perspektivisch zu einem eigenständig lizenzierbaren Produkt — API-Zugriff auf deutsches HR-Compliance-Wissen für Dritte, unabhängig vom Builder selbst. Job Shop wird entweder zu einem Playbook unter vielen innerhalb der Harness (Kannibalisierung ist laut Case-Constraint ausdrücklich erlaubt) oder bleibt als eigenständiger Zulieferer strukturierter Stellendaten für Recruiting-Agenten bestehen. Die 600-Kunden-Basis wird zur Referenz- und Nutzungsdatenbasis, aus der sich ein DACH-weiter Benchmark für funktionierende HR-Automatisierung entwickelt — genau die Art von akkumulierter Distribution und Nutzungsdaten, die laut Technologierecherche zu den einzigen Moat-Elementen zählt, die Vibe-Coding nicht kopieren kann (research_technology.md §4).

## 4. Fit mit dem HRPerfect-Profil

| Genutzte Stärke | Zu schließende Lücke |
|---|---|
| 600 bestehende Kundenbeziehungen (SME bis Enterprise) — direkter Vertriebskanal, umgeht das dokumentierte Procurement-Vertrauens-Gate gegen kleine/unbekannte Anbieter (research_problems.md §1.3) | Kein produktisierter Einstiegspfad vorhanden — heutiges Geschäft ist auf Enterprise-Sales-Zyklus ausgelegt; Sandbox-Demo → kleiner Plan muss komplett neu gebaut werden |
| HR Compliance Layer bereits als HRPerfect-eigene Infrastruktur/Wissen vorhanden (Case-Angabe) | Muss von internem Wissen zu einer API-fähigen, durchsetzenden Schicht umgebaut werden; der Aufwand dafür ist in keiner der drei Recherchedateien beziffert |
| n8n bereits im Stack gesetzt als Orchestrierungsschicht | Ungeklärt, ob n8n für mehrstufige HR-Agentenlogik ausreicht oder eine zweite Schicht (z. B. LangGraph-Muster) nötig wird (research_technology.md §1b, §2) |
| Claude API/Agent SDK production-ready für Einbettung in Dritt-SaaS, bereits im Stack gesetzt | US-CLOUD-Act-Exposition steht im Spannungsverhältnis zum "DACH-nativ"-Versprechen, bis der Sovereign Mode (V2) verfügbar ist (research_technology.md §1f, §6) |
| MCP als Marketplace-Standard existiert bereits real und wächst schnell — passt zur Case-Prämisse "der Markt liefert Integrationen" (research_technology.md §1d, §4) | Team-Kompetenz für Python-/MCP-Entwicklung ist laut Tech-Stack neu (bisher primär Java) — das Skill-Gap-Risiko wird von keiner der drei Recherchedateien geprüft; interne Kompetenzprüfung nötig |
| Sales-Funnel bei 50 % erzeugt echten Handlungsdruck; Bereitschaft, Job Shop zu kannibalisieren, erleichtert Ressourcenumschichtung (Case-Constraint) | Keine belegte Fähigkeit zu Self-Service-/PLG-Vertrieb; "Show, don't tell" als alleiniger Konversionsmechanismus ist zudem durch Kaufreue-Evidenz nicht unangefochten (90 % der reuigen HR-Software-Käufer:innen verließen sich ausschließlich auf Herstellerangaben, research_problems.md §3.1) |
| Bestehende Java-Plattform (Job Shop, ROI-Analytics, Compliance-Layer-APIs) liefert operative Stabilität und Cashflow während des Aufbaus | Kein Kostenmodell für Claude-API-Verbrauch pro Agenten-Case vorhanden — die Nutzungsgebühr-Prämisse ist unkalkuliert (research_technology.md §3) |

## 5. Zentrale zu validierende Annahmen

| Annahme | Wie validieren |
|---|---|
| Ein kuratiertes Playbook konvertiert schneller UND reduziert das Adoptions-Scheitern-Risiko gegenüber einer offenen "baue was du willst"-Positionierung. | Pilot mit 5–10 Bestandskund:innen aus den 600 Job-Shop-Beziehungen, zwei Kohorten (kuratierter Playbook-Einstieg vs. offene Builder-Positionierung); messen: Time-to-first-live-agent, Nutzungsintensität nach 60/90 Tagen, Abbruchquote. |
| Das Freigabe-Gate verkürzt die reale Time-to-Live spürbar, statt die "15-Minuten-Demo"-Geschwindigkeit durch einen neuen Flaschenhals (Betriebsrats-Prozess) zu ersetzen. | Bei den ersten 5–10 Piloten Zeit von Demo bis Live-Schaltung messen, aufgeschlüsselt nach Kund:innen mit/ohne Betriebsrat; Vergleich mit dem recherchierten Referenzwert von 3–6 Monaten externer Vendor-Assessments (research_problems.md §1.4). |
| Compliance-Tiefe + 600-Kunden-Distribution sind tatsächlich kaufentscheidend — nicht der Builder oder die KI-Technologie selbst. | Strukturiertes Debrief nach jedem Pilot-Abschluss/jeder Absage: welches Argument gab den Ausschlag? Abgleich mit der Outsail-Beobachtung, dass "KI" in Evaluierungsgesprächen kaum aktiv genannt wird (research_problems.md §3.3). |
| Die Preisarchitektur (Plattformgebühr + Nutzungsgebühr nach Agentenzahl/Fallvolumen) lässt sich profitabel kalkulieren, obwohl aktuell kein Benchmark für Claude-API-Token-Verbrauch pro typischem HR-Agenten-Case existiert. | Tatsächlichen Token-Verbrauch der drei MVP-Playbooks in der Pilotphase messen (nicht schätzen), Grenzkosten pro Case berechnen — erst danach Preispunkte fixieren. |
| Der Claude-API-Layer (US, CLOUD-Act-Exposition) ist für die Mehrheit der Zielkund:innen in der MVP-Phase kein Blocker; die Spannung lässt sich bis zum V2-Sovereign-Mode kommunikativ/vertraglich (SCCs, DPA) statt architektonisch auflösen. | In den ersten Vertriebs-/Pilotgesprächen aktiv erfragen, ob CLOUD-Act-Exposition/Datenresidenz ein Blocker ist; Anteil der Kund:innen erfassen, die dies als Bedingung nennen; Schwelle festlegen, ab der Sovereign Mode von V2 auf MVP vorgezogen werden muss. |

## Offene Spannungsfelder, die diese Hypothese nicht auflöst

- **Der Builder ist kein Moat.** Er ist laut Technologierecherche vibe-codebar — der Case selbst berichtet den Präzedenzfall (Wiener Voice-AI-Plattform, in einer Woche nachgebaut, research_technology.md §4). Jede interne Priorisierung, die den Builder statt der Compliance-Tiefe und der 600-Kunden-Distribution als Kernverteidigung behandelt, baut auf Treibsand.
- **Die Playbook-Strategie mildert, löst aber nicht vollständig das "zu strategisch, nicht akut"-Risiko.** Drei konkrete Painkiller-Playbooks statt einer abstrakten Baukasten-Erzählung reduzieren die Ähnlichkeit zum ROI-Analytics-Scheitern, aber die Grundspannung bleibt: Eine Baukasten-*Fähigkeit* ist eine Abstraktionsebene über einem Punkt-Painkiller. Das muss in den ersten Piloten aktiv an Nutzungsdaten beobachtet werden, nicht nur an Abschlussraten.
- **Die CLOUD-Act-Frage ist im MVP nur vertraglich, nicht architektonisch gelöst.** Für Kund:innen, denen das nicht reicht, existiert bis V2 kein Angebot — das ist ein bewusster Kompromiss für Time-to-Market, kein gelöstes Problem.
- **Die Preisprämisse steht auf keiner kalkulierten Grundlage.** Es ist nicht auszuschließen, dass HRPerfects eigene Kostenbasis (n8n-Lizenzstufen, Claude-API-Verbrauch) dieselben Kostensprünge zeigt, die dem Kunden gegenüber vermieden werden sollen (research_technology.md §3) — bis zur Messung in der Pilotphase ist "Nutzungsgebühr statt Token-Preis" eine Wette, kein geprüftes Modell.
- **Der Wettbewerbsbefund zu Workday Build ist zwischen den beiden Recherchedateien uneinheitlich** (research_market.md §3b vs. research_technology.md §4, siehe analysis_status_quo.md Abschnitt 4, Punkt 1) — diese Hypothese geht von der vorsichtigeren, engeren Lesart aus (das Wettbewerbsfeld ist bereits enger, als eine der beiden Recherchen allein nahelegt), aber der Widerspruch selbst ist nicht aufgelöst.
