# Marktprobleme-Recherche: HRPerfect — HR Harness

## Kontext

**Unternehmen:** HRPerfect (fiktiver Beispiel-Case) — etabliertes HR/SaaS-Unternehmen, 70 Mitarbeitende, ca. 14 Mio. € Jahresumsatz, DACH-fokussiert. Kernprodukt (Horizon 1) ist Job Shop (Stellenanzeigen-Management), das aktuelle Horizon-2-Produkt (ROI-Analytics) ist technisch fertig, erzeugt aber noch keinen Kunden-Pull.

**Business-Case-Thema:** Das bestehende HR/SaaS-Geschäftsmodell steht unter Druck (Sales-Funnel bei ca. 50 % des Normalniveaus, kostendeckend aber nicht nachhaltig). Die strategische Frage: Kann das Unternehmen seine Produktphilosophie umkehren — von selbst spezifizierten HR-Agenten-Use-Cases hin zu einer Plattform, die es HR-Abteilungen erlaubt, eigene Agenten zu bauen — und daraus ein tragfähiges, skalierbares Geschäft machen, bevor das aktuelle Modell weiter erodiert? Marktkontext-Hypothese des Case: HR-Software-Käufer:innen tätigen weniger große SaaS-Anschaffungen und kaufen stattdessen kleine, spezifische Painkiller bei Agenturen ein — mit inkonsistenter Qualität, hohen Einarbeitungskosten und ohne Compliance-Basis.

**Lösungsrichtung:** HR Harness — eine Self-Service-Plattform, auf der HR-Teams eigene KI-Agenten bauen, deployen und managen, ohne Code, mit vorintegrierter deutscher Compliance (DSGVO Art. 22, EU AI Act Anhang III, BetrVG, BDSG § 26). Drei Schichten: HR Competency Layer (Compliance-/Domänenwissen als Moat), Agent Builder (No-Code-Konfiguration, Claude-Code-Analogie), Marketplace/Ecosystem (Skills & Plugins, kuratiert statt garantiert).

**Zielmarkt:** DACH-HR-Abteilungen aller Größenordnungen — vom 50-Personen-Mittelständler bis zum 5.000+-Personen-Konzern, horizontale statt enger ICP-Reichweite. Sekundär: HR-Softwareanbieter und Implementierungspartner als White-Label-Kunden. Einstiegshebel: die bestehende Job-Shop-Kundenbasis (600 Kundenbeziehungen, SME bis Enterprise).

**Recherchetiefe:** quick (mindestens 3 Suchen). **Sprache:** Deutsch.

**Methodischer Hinweis:** HRPerfect selbst ist ein fiktiver Case — es existieren keine öffentlichen Aussagen über "HRPerfect" als Unternehmen. Diese Recherche belegt daher nicht das Unternehmen, sondern die zugrunde liegende Marktdynamik (HR-Software-Kaufverhalten, KI-Agenten-Adoption, Procurement-/Compliance-Hürden), auf der die Prämisse des Case aufbaut. Alle Befunde sind Marktevidenz aus öffentlichen Quellen, keine HRPerfect-spezifischen Daten.

---

## 1. Geäußerte Pain Points

### 1.1 Adoptions- und Change-Management-Scheitern ist der am häufigsten belegte Schmerzpunkt
Laut SHRM liegt die Hauptursache für scheiternde HR-Tech-Einführungen nicht in der Technik, sondern im menschlichen Verhalten: "Nearly 1 in 4 organizations report that their new HR tech implementations fail to meet adoption expectations." Genannte Treiber: fehlendes Change Management, mangelnde Schulung, ein schlechter erster Eindruck bei Rollout. [Quelle: SHRM, shrm.org/enterprise-solutions/insights/biggest-reason-why-new-hr-technology-implementations-fail]

Fuseworkforce spitzt dies zu: HR-Software scheitert typischerweise, weil Unternehmen "Features statt Partnerschaften" kaufen — Tools werden nach Feature-Liste statt nach tatsächlichem Business-Pain ausgewählt, oft ohne klare strategische Verbindung zu den Unternehmenszielen. [Quelle: fuseworkforce.com/blog/most-hr-software-fails-because-companies-buy-features-instead-of-partnerships]

### 1.2 "Zu strategisch, nicht akut" — Tools ohne unmittelbaren Pain werden zu Shelfware
Für People-Analytics-/HR-Dashboard-Tools zeigt sich ein Muster, das dem aktuellen Problem von HRPerfects eigenem ROI-Analytics-Produkt auffällig ähnelt: "Buying software without a clear question leads to dashboards nobody looks at." Ursachen: fehlende klare Business-Fragestellung beim Kauf, mangelndes Change Management nach Rollout, Datenqualitätsprobleme. Bemerkenswert: Die zugrunde liegenden Tools selbst werden auf G2 nicht schlecht bewertet (Kategorie-Durchschnitt 4,49/5, Weiterempfehlungsquote 8,99/10) — das Problem liegt hier eher im Nutzungskontext ("zu strategisch, nicht akut genug") als in der Produktqualität. [Quelle: G2 HR-Analytics-Kategorie, g2.com/categories/hr-analytics; ergänzend diverse Ratgeber-Artikel zu HR-Analytics-Tools]

### 1.3 Boutique-/Agentur-Anbieter werden von Procurement systematisch aussortiert — unabhängig von Qualität
Direkte externe Bestätigung der im Case beschriebenen Beobachtung ("kleine Agenturen sind schwer durch Procurement- und Vertrauens-Gates zu bekommen"): "Implementation boutiques ship faster and cost 2-5x less than Big 4 firms for the same work... [but] procurement departments often won't approve smaller firms, which is cited as the most common real reason to pick Big 4 vendors." Als Abhilfe werden konkrete Nachweise genannt: SOC 2 als "Procurement-Abkürzung" sowie belastbare Referenzen ("Show me 3 production AI features you've shipped in the last 6 months"). [Quelle: justinmckelvey.com/blog/ai-consultant-companies; agenticaipricing.com/the-procurement-checklist-ai-vendors-should-prepare-for]

### 1.4 Compliance-Nachweispflicht für KI in HR ist real und zeitintensiv
Für HR-KI-Tools, die Kandidat:innen filtern, bewerten oder ranken, gilt unter dem EU AI Act eine High-Risk-Einstufung (Anhang III); rein prozedurale Tools fallen meist nicht darunter. Käufer:innen verlangen zunehmend konkrete Nachweise: "the Article 22 challenge and human-review workflow shown in practice, a concrete DPA with a full subprocessor map, and transfer documentation" — häufig bereitgestellt über einen "procurement data room under NDA". Externe Vendor-Assessments dauern typischerweise 3 bis 6 Monate; beteiligt sind oft Legal, Compliance, Risk, IT, Security, Procurement, HR und Product gemeinsam. [Quelle: sprad.io/blog/ai-recruiting-compliance-2026-what-hr-teams-need-to-know-about-gdpr-and-the-eu-ai-act-before-buying-ai-recruiting-tools; gdprregister.eu/articles/eu-ai-act-compliance-checklist-dpos]

### 1.5 Starre Verträge und "Customer-Size-Mismatch" treiben Anbieterwechsel
Über G2, Capterra und Trustpilot hinweg wiederholen sich sechs Beschwerdemuster: Support-Frust, Implementierungskomplexität, eingeschränktes Reporting, Payroll-Zuverlässigkeit, starre Verträge/Mindestlaufzeiten sowie "Customer-Size-Mismatch", wenn Käufer:innen aus einem Tool herauswachsen. Zitierte Formulierungen: Interface wirkt "very corporate and rigid"; die häufigste einzelne Wechselursache im Mid-Market ist, dass Käufer:innen ein Produkt verlassen, das ursprünglich für einen Durchschnittskunden mit ca. 7 Mitarbeitenden konzipiert wurde. [Quelle: Capterra-Reviews diverser Produkte, capterra.com; worknice.com/blog/why-companies-replace-employment-hero-and-what-they-choose-instead]

---

## 2. Jobs To Be Done & Workarounds

### 2.1 Schatten-KI ist bereits dominante Realität — nicht die Ausnahme
Die stärkste indirekte Evidenz für die Kern-Prämisse des Case: Mitarbeitende bauen sich KI-gestützte Workarounds schon heute selbst, weit außerhalb jeder Governance. Laut PagerDuty Shadow-AI-Survey 2026 (1.250 Bürofachkräfte in Unternehmen ab 500 Mio. USD Umsatz, Australien/Japan/UK/USA):
- **66 %** haben nicht autorisierte KI-Tools genutzt, obwohl sie wussten, dass dies gegen Unternehmensrichtlinien verstößt
- **88 %** haben arbeitsbezogene Informationen mit öffentlichen KI-Tools (ChatGPT, Claude, Gemini) geteilt
- **98 %** der Organisationen haben Mitarbeitende, die nicht sanktionierte KI-Tools nutzen
- **34 %** haben Kundendaten eingegeben, **31 %** Finanz-/vertrauliche Dokumente

Zitat des PagerDuty-CTO: "When over 30% of employees are putting confidential company data into public models, 'Shadow AI' becomes a massive enterprise liability." Ergänzend bestätigt eine Gartner-Befragung unter 302 Cybersecurity-Verantwortlichen: 69 % vermuten oder haben Beweise für verbotene GenAI-Nutzung in ihrer Organisation. [Quelle: PagerDuty Newsroom, pagerduty.com/newsroom/shadow-ai-workplace-survey-2026; Gartner-Zahl zitiert via secondtalent.com/resources/shadow-ai-stats]

Job-to-be-Done-Übersetzung: Der Bedarf, KI-gestützt zu arbeiten, ist längst da und wird bereits erfüllt — nur ungesteuert, ohne Compliance-Schicht. Genau diese Lücke beansprucht die HR Competency Layer im Case zu schließen.

### 2.2 Self-Service-Agentenbau ist bereits ein wachsender, adressierter Markt
Laut Deloitte werden 25 % der Organisationen, die generative KI einsetzen, 2026 Agentic-AI-Pilotprojekte oder Proofs-of-Concept starten. Anbieter wie Microsoft Copilot Studio (Low-Code-Plattform für HR-Agenten zu Benefits-Fragen, Policy-Discovery, Onboarding, Urlaubsanträgen) und Moveworks (Employee-Self-Service) positionieren sich explizit auf HR-Selbstbedienung. Eine Quelle beschreibt die Verschiebung so: "Non-technical users who once depended on engineering queues can now prototype conversational agents alongside technical teams" — strukturell dieselbe Verschiebung, die der Case für HR-Fachbereiche postuliert. [Quelle: sanalabs.com/agents-blog/hr-ai-agents-work-assistants; rasa.com/blog/best-low-code-ai-agents-platforms-for-2026]

### 2.3 DACH-Praxisbeispiel: HR-Self-Service-Agent bereits im Einsatz
Aus der deutschsprachigen Recherche: Ein Industrieunternehmen hat einen HR-Self-Service-Agenten in Teams gebaut, der Fragen zu Urlaubstagen, Reisekostenregeln und Weiterbildung beantwortet und komplexere Anfragen weiterleitet — mit einer berichteten Entlastung von rund 40 % der Routine-Tickets. Genannte Bauzeiten: 2–4 Wochen für klar definierte Prozesse, 4–8 Wochen bis zum ersten produktiven Kern-Agenten, 6–12 Wochen für komplexere Multi-System-Integrationen. n8n, Microsoft Copilot Studio und Make werden explizit als Low-Code-Wege genannt. [Quelle: lise.de/insights/artikel/ki-agenten-erstellen-fuer-unternehmen; abiconsulting.io/leistungen/ki-agenten; akademie-ki.com/ki-agenten-erstellen]

Einschränkung: Diese Quellen bestätigen die technische Machbarkeit (Agentenbau ist heute ohne Data-Science-Team möglich), belegen aber nicht eindeutig, dass HR-Fachbereiche selbst (statt IT-Abteilung oder externer Dienstleister) die Agenten bauen. Diese Differenzierung — zentral für die "Claude Code für HR"-Analogie des Case — bleibt eine offene Frage für vertiefte Recherche.

### 2.4 Ein-Personen-HR-Abteilungen als struktureller Workaround-Treiber
In kleinen und mittleren Unternehmen trägt häufig eine einzelne HR-Generalist:in "alle Hüte gleichzeitig" — Recruiting, Onboarding, Compliance, Benefits. Bei Wachstum, Saisonspitzen oder Fluktuation kollabiert dieses Ein-Personen-Setup unter Verwaltungsaufwand, der nie für Skalierung gedacht war. Automatisierung wird durchgängig als Entlastungshebel genannt, ist aber an Budget und Priorisierung gebunden. [Quelle: futureforcepersonnel.com/2026/06/03/staffing-automation-for-hr-teams; diverse HR-Burnout-Ratgeber (Raconteur, AIHR, Workday)]

### 2.5 Lücke: Direkte Excel-/CSV-Workaround-Zitate nicht auffindbar
Konkrete, zitierfähige Beispiele für HR-spezifische Tabellen-Workarounds ("wir machen das in Excel, weil nichts anderes funktioniert") ließen sich in dieser Recherche-Runde nicht direkt belegen — die gezielte Suche nach Forenbeiträgen lieferte keine einschlägigen, indexierten Treffer (siehe Recherche-Log). Das Muster wird indirekt durch den Case selbst gestützt ("companies know their own workarounds (CSV exports, email workflows, etc.)") sowie durch die generelle Literatur zu Datenqualität als Adoptionsbremse (Abschnitt 1.2), ist aber **nicht mit einer öffentlichen Primärquelle belegt**.

---

## 3. Gescheiterte Lösungen

### 3.1 HR-Software als dritthäufigste Quelle von Kaufreue
Laut Capterra Tech Trends Report ist HR-Software die dritthäufigste Quelle für Kaufreue unter den untersuchten B2B-Softwarekategorien; 28 % der befragten reuigen Käufer:innen nannten HR-Software als Ursache. Kernzahlen:
- **90 %** der reuigen Käufer:innen verließen sich ausschließlich auf Herstellerangaben
- **62 %** beschreiben die finanzielle Auswirkung als "significant or monumental"
- **64 %** der reuigen Käufer:innen waren Alleinentscheider:innen (gegenüber 52 % bei erfolgreichen Käufen)
- **37 %** nennen höhere Gesamtkosten als erwartet als Top-Grund (gleichauf mit "Technologie zu komplex")

Zitat: "Relying solely on what vendors tell you about their product is a bad idea." Erfolgreiche Käufer:innen ziehen 56 % häufiger Expertenmeinungen und 52 % häufiger Bewertungsportale hinzu als reuige Käufer:innen. [Quelle: Capterra, capterra.com/resources/tech-trends-hr-software-purchase-regret]

**Relevanz für den Case:** Das Muster "Alleinentscheider:in verlässt sich auf Herstellerangaben → Kaufreue" ist genau die Lücke, die ein vertrauensbasierter Ansatz über eine bereits bekannte Marke (600 bestehende Kundenbeziehungen) strukturell adressieren könnte. Gleichzeitig relativiert es die Annahme, eine 15-minütige Live-Demo allein reiche zur Konversion — die Daten legen nahe, dass Käufer:innen typischerweise mehrere unabhängige Quellen brauchen, um Kaufreue zu vermeiden.

### 3.2 Punktlösungen sparen kurzfristig, kosten langfristig durch Integrationsaufwand
Modulare Anbieter (Beispiel Rippling) erlauben zunehmend den Einkauf einzelner Komponenten statt kompletter Suiten. Kehrseite: "Point solutions may cost less in the short term, but pile on integration and admin overhead as you grow." Preisspannen: Entry-Level-Punktlösungen bei 2–8 USD PEPM, vollständige Enterprise-Suiten mit Analytics/globaler Payroll bei 30–100+ USD PEPM — eine Bandbreite, die der im Case geforderten Skalierung von "kleiner Plan" bis "Enterprise-Plan auf derselben Plattform" strukturell entspricht. [Quelle: selecthub.com/hr-management/hr-software-pricing; selectsoftwarereviews.com/blog/hr-software-pricing]

### 3.3 Wichtige Gegenevidenz: "KI" ist (noch) kein Kaufauslöser, den Käufer:innen selbst nennen
Zentrale Spannung für die Positionierung des Case: Laut Outsail wurde "AI" in offenen Antworten von HR-Tech-Käufer:innen nur in **0 % (2024) → 0,7 % (2025) → 4,8 % (2026)** der Evaluationsgespräche proaktiv erwähnt; unter 5 % der Käufer:innen bringen KI von sich aus zur Sprache, manche lehnen starke KI-Beteiligung explizit ab. Gleichzeitig ist "Automatisierung" mit über 50 % Nennung die Top-Priorität der Käufer:innen. Automatisierung wird also stark nachgefragt — aber nicht unbedingt unter dem Label "KI" oder "Agent". Ergänzend: 16 % der 2026 evaluierten Kund:innen haben noch gar kein bestehendes HCM/HRIS-System (gegenüber ca. 9 % in Vorjahren) — ein wachsender "Greenfield"-Markt ohne Ablösungsdruck, aber auch ohne bestehende Kaufgewohnheit. [Quelle: Outsail, outsail.co/post/observing-hr-tech-buying-behavior-in-2026]

Das stützt indirekt die "Show-don't-tell"-GTM-Hypothese des Case: Wenn Käufer:innen nicht aktiv nach "KI-Agenten-Plattformen" suchen, sondern nach Automatisierungs-/Entlastungsergebnissen, dann müsste Positionierung/Marketing eher auf konkrete Ergebnisse zielen als auf die Technologie-Kategorie — eine Aussage, die im Case bisher nicht explizit gemacht wird und für Phase 2/3 relevant sein dürfte.

### 3.4 Konkrete Wechselgründe von bestehenden HR-Tools (aggregiert)
Wiederkehrende Muster aus Capterra-/G2-Auswertungen: Support-Qualität, Implementierungsaufwand, eingeschränktes Reporting/fehlende Audit-Trails, Payroll-Zuverlässigkeit, starre Vertragsbindung — und am häufigsten im Mid-Market: das Herauswachsen aus einem für kleinere Kund:innen gebauten Produkt. [Quelle: siehe Abschnitt 1.5]

---

## 4. Häufigkeits- & Schweregrad-Matrix

| Problem | Häufigkeit | Schweregrad | Anmerkung |
|---|---|---|---|
| Adoptions-/Change-Management-Scheitern bei HR-Tech-Einführung | Hoch | Hoch | ~1 von 4 Implementierungen verfehlt Adoptionserwartung (SHRM); 62 % der Kaufreue-Fälle mit "signifikanter/monumentaler" finanzieller Wirkung |
| Schatten-KI / ungesteuerte KI-Nutzung durch Mitarbeitende | Sehr hoch | Hoch | 66–98 % Nutzung je nach Messung; explizit als "massive enterprise liability" bezeichnet |
| Procurement lehnt kleine/Boutique-Anbieter unabhängig von Qualität ab | Hoch | Hoch | Als häufigster realer Grund für Big-4-Wahl genannt; wirkt als binäres Ausschlusskriterium, nicht graduell |
| EU-AI-Act-/DSGVO-Nachweispflicht bei KI-Beschaffung | Mittel–Hoch | Hoch | 3–6 Monate Assessment-Dauer; betrifft primär High-Risk-Use-Cases (Scoring/Filtering), nicht jede HR-KI-Anwendung |
| Strategische Tools ("zu strategisch, nicht akut") werden zu Shelfware | Mittel | Mittel–Hoch | Direktes Analogon zu HRPerfects eigenem ROI-Analytics-Problem; Produktqualität laut G2 nicht die Ursache |
| Customer-Size-Mismatch bei Wachstum (Tool wird herausgewachsen) | Mittel | Hoch | Erzwingt Re-Platforming/Migration; häufigster Einzelgrund im Mid-Market-Wechsel |
| Punktlösungs-Wildwuchs (Integrations-/Verwaltungsaufwand) | Mittel | Mittel | Kosten akkumulieren graduell, kein Einzelereignis |
| "KI" als explizit genanntes Kaufkriterium fehlt trotz Automatisierungsbedarf | Niedrig (als Suchbegriff), Bedarf selbst hoch | Mittel (Positionierungsrisiko) | Nur 4,8 % erwähnen "KI" proaktiv, während Automatisierung Top-Priorität ist — Hinweis auf Positionierungs-, nicht Nachfrageproblem |

*Frequenz/Schweregrad sind qualitative Einschätzungen der Rechercheagentin auf Basis der zitierten Quellen, keine standardisierte Kennzahl.*

---

## 5. Wer beschwert sich

- **HR-Generalist:innen / Ein-Personen-HR in KMU (50–500 MA):** Nutzer:innen und zugleich (Mit-)Entscheider:innen. Vokal zu Arbeitsüberlastung, "alle Hüte gleichzeitig", fehlendem Budget für Entlastung. Vermutlich primäre Zielgruppe für kleine HR-Harness-Einstiegspläne.
- **People-Ops-/HRIS-Leads im Mid-Market:** Käufer:innen, die aus ursprünglich für Kleinkund:innen gebauten Tools herausgewachsen sind. Vokal auf G2/Capterra zu Rigidität, Reporting-Grenzen, Vertragsbindung.
- **IT-/Security-/Compliance-Verantwortliche (oft außerhalb HR):** Nicht HR selbst, aber faktische Gatekeeper der Procurement-Gates, die der Case explizit als Hürde für Boutique-Anbieter benennt. Vokal zu Schatten-KI-Risiko (Gartner-Befragung, PagerDuty-CTO-Zitat) und Vendor-Governance-Anforderungen (DPA, Subprocessor-Map, SOC 2).
- **Einzelentscheider:innen in kleineren Organisationen:** Laut Capterra überproportional in Kaufreue-Fällen vertreten (64 % vs. 52 % bei Erfolgsfällen) — verlassen sich mangels Ressourcen für unabhängige Recherche stärker auf Herstellerangaben. Direkte Zielgruppe für einen vertrauensbasierten Vertrieb über bestehende Kundenbeziehungen.
- **Mitarbeitende allgemein (nicht HR-spezifisch, aber HR-relevant als Nutzer:innen von Schatten-KI):** Nicht "beschwerdeführend" im klassischen Sinn, sondern durch Verhalten vokal — 66–88 % nutzen KI-Tools bereits ungesteuert. Verhaltens-, keine Aussage-Evidenz.

**Nutzer:innen vs. Käufer:innen:** Die Recherche deutet auf eine Trennung hin, die für den Case wichtig ist: Die Personen, die am lautesten über Arbeitsüberlastung klagen (HR-Generalist:innen), sind oft nicht dieselben, die über Procurement-Freigabe entscheiden (IT/Security/Compliance, teils Alleinentscheider:in in der Geschäftsführung bei KMU). Ein Produkt, das die HR-Generalist:in überzeugt, muss zusätzlich die Procurement-/Compliance-Gates adressieren, die eine andere Stakeholder-Gruppe kontrolliert — dies deckt sich mit der im Case genannten Trennung zwischen "Show-don't-tell"-Demo-Überzeugung und Compliance-Layer als separatem Vertrauensanker.

**Lücke:** Direkte, namentlich zitierbare Wortmeldungen von HR-Entscheider:innen speziell zu "ich will meine eigenen KI-Agenten bauen können" (im Sinne der Claude-Code-Analogie des Case) ließen sich in dieser Recherche-Runde nicht auffinden. Die Evidenz dafür bleibt indirekt (Wachstum von No-Code-Agent-Plattformen, DACH-Praxisbeispiel, Schatten-KI-Nutzung) statt direkt zitiert.

---

## Recherche-Log

**Suchanfragen (WebSearch), 13 insgesamt:**
1. "HR teams building their own AI agents no-code self-service demand 2026"
2. "why HR software point solutions fail adoption complaints"
3. "HR software procurement AI vendor trust compliance concerns GDPR EU AI Act"
4. "HR tech buyers 2026 fewer big suite purchases small point solutions budget"
5. "HR reddit spreadsheet workaround AI ChatGPT instead of software" — kein direkter Forums-Treffer, nur Add-on-Produktseiten
6. "people analytics HR dashboard not used shelfware complaints g2"
7. "shadow AI employees unauthorized ChatGPT workplace statistics survey 2026"
8. "boutique AI agency vendor procurement trust enterprise hard to vet small vendor"
9. "HR manager LinkedIn frustrated manual process 'wish I could build' automation" — überwiegend generischer Automatisierungs-Content, wenig direkte Beschwerde-Zitate
10. "HR Abteilung eigene KI-Agenten bauen Self-Service Mittelstand Deutschland"
11. "'switched from' HR software churn reasons capterra review complaints too rigid"
12. "site:reddit.com r/humanresources AI agent build own tool frustrated" — keine indexierten Reddit-Treffer
13. "HR generalist small company burnout too many hats need automation but no budget"

**Vertiefende Abrufe (WebFetch), 3 insgesamt:**
- capterra.com/resources/tech-trends-hr-software-purchase-regret (Kaufreue-Statistiken)
- outsail.co/post/observing-hr-tech-buying-behavior-in-2026 (Käuferverhalten 2026)
- pagerduty.com/newsroom/shadow-ai-workplace-survey-2026 (Schatten-KI-Statistiken)

**Gesamt: 16 Suchvorgänge** (13 WebSearch + 3 WebFetch), deutlich über dem Minimum von 3 für "quick".

**Gesichtete Quellen:** ca. 25 inhaltlich ausgewertete Artikel/Seiten (Synthesen der 13 Suchanfragen, deren Ergebnislisten je 6–10 Links umfassten, plus 3 vollständig abgerufene Volltexte). Herangezogen u. a. SHRM, Capterra, G2, Outsail, PagerDuty, Gartner (zitiert via Sekundärquelle), gdprregister.eu, sprad.io, selecthub.com sowie mehrere deutschsprachige Beratungs-/Agenturquellen (lise.de, abiconsulting.io, akademie-ki.com).

**Konfidenzniveau: Mittel.**
Begründung: Die Recherche liefert solide, zahlenbasierte Sekundärevidenz (Marktberichte, Vergleichsportale, Herstellerstudien wie PagerDuty/Outsail/Capterra) für die zentralen Fragen des Auftrags — Procurement-/Vertrauenshürden für kleine Anbieter, Compliance-Aufwand, Punktlösungs- vs. Suite-Kaufverhalten und Schatten-KI als Nachfragebeleg sind alle mit konkreten Zahlen belegt, teils mit direkten Zitaten. Zwei Lücken schwächen die Konfidenz:
1. Es fehlen direkte, wörtlich zitierbare Praktiker:innen-Stimmen aus Foren (Reddit, Hacker News, XING) — die gezielte Suche danach blieb ergebnislos, vermutlich weil diese Plattformen von der genutzten Websuche nicht tief indexiert werden.
2. Es fehlt DACH-spezifische Beschwerde-Evidenz (deutschsprachige Nutzer:innen-Zitate); die gefundenen deutschen Quellen sind überwiegend Anbieter-/Beratungscontent mit Praxisbeispielen, keine Nutzer:innen-Beschwerden.

Für eine belastbarere Grundlage empfiehlt sich in einer vertieften Recherche-Runde ("deep") eine gezielte Suche direkt auf reddit.com/r/humanresources, r/AskHR, XING-Gruppen und deutschen HR-Fachforen (z. B. Haufe-Community), sowie ein Zugriff auf einzelne G2/Capterra-Reviews statt Aggregat-Snippets.
