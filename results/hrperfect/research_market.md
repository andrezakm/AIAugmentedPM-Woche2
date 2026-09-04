# Market Research

*Case: HRPerfect — Pivot von HR-/SaaS-Anbieter zu No-Code-Plattform für HR-eigene KI-Agenten (DACH, deutsche HR-Compliance-Schicht). Research Depth: quick.*

## 1. Market Size & Growth

- **DACH HR-Software-Markt 2026 — widersprüchliche Schätzungen:** Eine Quelle nennt 3,2 Mrd. € (einer IDC-Schätzung zugeschrieben), eine zweite, parallel in derselben Recherche aufgetauchte Zahl liegt bei 1,8 Mrd. €. Die automatisierte Such-Synthese erlaubt keine eindeutige Zuordnung, welche Zahl aus welcher Primärquelle stammt [Quelle: Websuche-Synthese über businessresearchinsights.com, de.statista.com]. **Diskrepanz wird hier bewusst offengelassen — vor Verwendung im Business Case verifizieren.**
- **Umsatz der Top-25 HR-Software-Anbieter in Deutschland:** 2,65 Mrd. € (Bezugsjahr 2024) [Quelle: haufe.de – HR-Software-Ranking].
- **Wachstumsrate DACH HR-Software:** ca. 12 % p.a. laut Such-Synthese [Quelle: hrworks.de / businessresearchinsights.com-Cluster].
- **Cloud-Adoption:** ca. 72 % der Neukunden im DACH-Mittelstand wählen 2026 Cloud-Lösungen statt On-Premise [Quelle: Websuche-Synthese, DACH-HR-Software-Marktüberblick].
- **Globaler No-Code-AI-Plattform-Markt** (die Kategorie, in die der Agent-Builder-Teil von HR Harness fällt, nicht HR-spezifisch): Prognose von 8,6 Mrd. USD (2026) auf über 75 Mrd. USD (2034) [Quelle: Websuche-Synthese über mindstudio.ai/pickaxe.co/dronahq.com-Vergleichsartikel-Cluster].
- **Marktcharakteristik DACH:** hohe Anforderungen an Datenschutz (DSGVO), Compliance, Mitbestimmung und Lokalisierung unterscheiden den Markt strukturell von anderen Regionen [Quelle: Websuche-Synthese].
- **Lücke:** Kein Marktgrößen-Wert für die eigentliche Zielkategorie von HR Harness — "No-Code-Agent-Builder speziell für HR, DACH" — gefunden. Diese Schnittmenge (HR-Software × Agent-Builder × DACH-Compliance) existiert in keiner der gesichteten Marktreports als eigene Kategorie. Insufficient public data found. Searches conducted: siehe Research Log. Recommend primary research (z. B. Custom-Anfrage bei Gartner/IDC/BearingPoint).

## 2. Market Segments

- Die HR-Software-Anbieterlandschaft ist klar dreigeteilt: **Enterprise-Suiten** (Workday, SAP SuccessFactors, Oracle), **Mittelstands-Allrounder** (Personio, HRworks, Kenjo) und **Spezialisten** für Recruiting/Learning [Quelle: activate-hr.de – HR-Cloud-Suiten-Vergleich].
- Positionierungsmuster zwischen den Segmenten: Personio gewinnt im Mittelstand über Einfachheit und Tempo; SAP SuccessFactors gewinnt im Konzern über Tiefe, Skalierung und globale Compliance [Quelle: activate-hr.de].
- Im generischen No-Code-Agent-Builder-Markt liegt der Zielgruppenfokus der recherchierten Anbieter fast durchgängig auf **Enterprise-Teams** (explizit genannt: Operations Leads, Support Manager, Finance Analysts) [Quelle: coworker.ai — "11 No-Code AI Agent Builders for Enterprise Teams"]. SMB wird in diesem Artikel-Cluster nicht explizit adressiert.
- Das deckt sich mit einer möglichen Unterversorgung kleinerer Unternehmen im generischen Agent-Builder-Markt — passend zur Kernthese des Case (50-Personen-HR-Team als valider Einstiegspunkt), aber nicht durch eine dedizierte Segmentierungsstudie belegt, sondern durch Abwesenheit von Gegenbeispielen in den gesichteten Vergleichsartikeln.
- **Lücke:** Keine belastbare Segmentierung nach Unternehmensgröße speziell für einen "HR-Agent-Builder-Markt" gefunden (z. B. Anteil 50-Personen- vs. 2.000-Personen-HR-Abteilungen, die aktiv eigene Agenten bauen). Insufficient public data found. Recommend primary research.

## 3. Competitive Landscape

Drei Wettbewerbstypen wie im Case-Briefing gefordert — generische Agent-Builder Richtung HR, HR-Vendoren mit Agent-Buildern, HR-AI-Startups:

**a) Generische Agent-Builder (bewegen sich Richtung HR, kein HR-natives Produkt)**
- Genannt: n8n, Microsoft Copilot Studio, Salesforce Agentforce, ServiceNow AI Agents, StackAI, Glean, Relevance AI, Dust, UiPath, SAP Build Apps (mit Joule), Coworker [Quelle: coworker.ai, Listicle "11 No-Code AI Agent Builders for Enterprise Teams 2026"].
- Weitere in Vergleichsartikeln genannte Anbieter: Lindy, MindStudio, Pickaxe, Agentshub.AI, EasyAgentForYou, DronaHQ, Airtable-eigener Vergleichsartikel [Quelle: diverse Vergleichsartikel, WebSearch-Cluster "No-Code AI Agent Builder 2026"].
- Von diesen erwähnt laut Volltext-Check nur **ServiceNow AI Agents** HR explizit als Anwendungsfall ("for IT, HR, and customer service work") [Quelle: coworker.ai]. Die übrigen sind horizontal/branchenagnostisch positioniert.
- Keiner der geprüften generischen Builder wird in den Quellen mit einer deutschen HR-Compliance-Schicht in Verbindung gebracht.
- **Pricing:** kaum transparente Angaben auffindbar. Salesforce Agentforce wird als "usage-based pricing can escalate costs" beschrieben, StackAI mit "higher enterprise pricing", Relevance AI mit "pricing scales with complexity" [Quelle: coworker.ai]. Konkrete Preispunkte (€/Monat, €/Agent, €/Case) wurden nicht gefunden.

**b) HR-Vendoren mit eigenem Agent-Builder / Agentic-AI-Layer**
- **SAP SuccessFactors:** Seit Release 1H/2026 agentische KI ("Joule") über die gesamte Suite verfügbar; vernetzte Agenten in Recruiting, Personalverwaltung, Gehaltsabrechnung, Weiterbildung, Talentförderung [Quelle: handelsblatt.com/adv (SAP-Advertorial), activate-hr.de].
- **Workday:** Acht spezifische KI-Agenten (u. a. "Recruiter", "Talent Mobility"), Anspruch bis zu 70 % administrativer Recruiting-Aufgaben zu automatisieren; positioniert ein "Agent System of Record" als Governance-Schicht [Quelle: ad-hoc-news.de, "KI-Agenten revolutionieren HR-Software 2026"]. Zusätzlich: globaler Start der KI-Plattform "Sana" am 17. März 2026, laut Quelle Ergebnis einer "Milliardentransaktion Ende 2025" — konkreter Kaufpreis nicht genannt, vor Verwendung verifizieren [Quelle: ad-hoc-news.de, "KI-HR-Agenten starten, doch Datenchaos bremst Europa"].
- **Oracle:** Über 100 Agenten Ende 2025 veröffentlicht, u. a. ein "Team Sync"-Agent (Analyse von Stimmungs-/Produktivitätsdaten der Belegschaft); bietet ein "AI Agent Studio" für kundenspezifische Agent-Entwicklung [Quelle: ad-hoc-news.de]. Das ist unter den großen Suiten-Anbietern die einzige gefundene Ausnahme mit expliziter Selbstkonfiguration durch den Kunden — strukturell am nächsten an HRPerfects "Kunden bauen eigene Agenten"-Ansatz.
- **Personio:** Als Schlüsselakteur im europäischen Mittelstand genannt, Positionierung über Einfachheit und Tempo [Quelle: activate-hr.de, ad-hoc-news.de]. Keine Angaben zu einem eigenen No-Code-Agent-Builder von Personio gefunden.
- **Microsoft Dynamics 365 HR:** neue Implementierungsangebote im Enterprise-Segment genannt, ohne weitere Details [Quelle: ad-hoc-news.de].
- **Einordnung:** Die großen Suiten-Anbieter (Workday, Oracle, SAP) investieren aktuell primär in eigene, vorgefertigte Agenten-Portfolios — nicht in Self-Service-Baukästen für den Endkunden. Oracles "AI Agent Studio" ist die einzige belegte Teilausnahme. Keiner der genannten Anbieter wird in den Quellen mit einer dedizierten deutschen Compliance-Schicht (BetrVG/BDSG-spezifisch) verknüpft — stützt tendenziell die Differenzierungsthese des Case, ist aber keine erschöpfende Feature-für-Feature-Analyse.

**c) HR-AI-Startups**
- **tlou.ai:** "Agentic AI platform for Human Resources", Positionierung "Recruiting wieder menschlicher machen", macht laut Eigenbeschreibung Potenzial, Motivation und Persönlichkeit von Bewerbern sichtbar [Quelle: tlou.ai].
- Nicht namentlich auflösbare Erwähnungen: ein HRTech-/AI-Recruiting-Automation-Startup im Seed-Stage in Saarbrücken sowie ein AI-Agent-Workflow-Automation-Unternehmen in Berlin [Quelle: Websuche-Synthese, vermutlich vcgermany.de-Startup-Liste — Namen in der Kurzrecherche nicht auflösbar].
- **mona-ai.de** und **onapply.de** erscheinen im Suchindex zu KI-Recruiting-Tools 2026; deren genaues Produktprofil (eigener Agent-Builder vs. Punktlösung/Vergleichsportal) wurde in dieser Kurzrecherche nicht verifiziert.
- **Einordnung:** Dünne Faktenlage zu deutschen HR-AI-Startups mit echtem Agent-Builder-Fokus (im Gegensatz zu Punktlösungen wie CV-Parsing oder Recruiting-Matching). Kein Startup gefunden, das explizit "No-Code Agent Builder + deutsche HR-Compliance" wie HRPerfect kombiniert. Das deutet auf ein mögliches Whitespace hin, ist aber angesichts der begrenzten Suchtiefe (quick, 5 Suchen) kein Beleg für Marktleere — primäre Wettbewerbsrecherche empfohlen, insbesondere über Crunchbase/vcgermany.de-Startup-Datenbanken mit Volltextzugriff.

## 4. Market Trends & Forces

- **Agentic-AI-Verschiebung:** Branchenweiter Trend von assistierender zu autonomer KI — Agenten erhalten ein Ziel, navigieren Systeme selbstständig, treffen Entscheidungen und koordinieren mehrstufige Prozesse ohne konstante menschliche Kontrolle [Quelle: ad-hoc-news.de, uplifted.today].
- **"Superworker"-Narrativ:** Von HR-Analyst Josh Bersin geprägt (laut Zitat) — Positionierung als Aufwertung der Belegschaft statt Jobersatz [Quelle: ad-hoc-news.de].
- **Human-in-the-Loop als Standardanforderung:** Mehrere unabhängige Quellen beschreiben vollautonome Personalentscheidungen als rechtlich riskant und Human Oversight als notwendige Design-Vorgabe, nicht als Kür [Quelle: ad-hoc-news.de, uplifted.today, activate-hr.de].
- **Regulatorischer Haupttreiber — EU AI Act:** Hochrisiko-Pflichten für KI-Systeme, die Einstellung, Beförderung, Bewertung oder Kündigung von Mitarbeitenden unterstützen oder vorbereiten, greifen ab **August 2026** — dieses Datum wird von mehreren unabhängigen Quellen übereinstimmend genannt [Quelle: activate-hr.de, skill-sprinters.de, enkaconsulting.de, it-boltwise.de, ki-spezial.systems]. Pflichten umfassen Risikomanagement, Daten-Governance, Human Oversight, Transparenz, technische Dokumentation und Audit Trails.
- **Bußgeld-Angaben widersprüchlich zwischen Quellen:** Eine Quelle nennt "bis zu 15 Mio. € oder 3 %" bei Verstößen gegen Hochrisiko-Pflichten [Quelle: Websuche-Synthese/ad-hoc-news.de-Cluster], eine andere nennt "bis zu 35 Mio. € oder 7 % des weltweiten Jahresumsatzes" [Quelle: activate-hr.de]. Diese Diskrepanz ist plausibel auf unterschiedliche Verstoßkategorien im EU AI Act zurückzuführen (verbotene Praktiken vs. Hochrisiko-Pflichtverletzung), wurde aber in den gesichteten Quellen nicht einheitlich zugeordnet. **Vor Verwendung in einem Kundendokument am AI-Act-Originaltext verifizieren.**
- **Uneinheitliches Enforcement-Datum:** Eine Quelle nennt "volle Durchsetzung der Bußgelder ab August 2027", während die materiellen Pflichten selbst laut anderen Quellen bereits ab August 2026 bindend sind. Auch hier: vor Verwendung verifizieren.
- **Deutsches Arbeitsrecht als zusätzliche Auflage:** Betriebsverfassungsgesetz §87 (Mitbestimmung) und BDSG §26 werden von mehreren Quellen als über den EU AI Act hinausgehende, DACH-spezifische Anforderungen an automatisierte Personalentscheidungen genannt [Quelle: ad-hoc-news.de, activate-hr.de].
- **Datenfragmentierung als Adoptionsbremse:** Laut einer BearingPoint-Studie (414 befragte HR-Verantwortliche) sehen zwar 80 % der HR-Leiter Effizienzvorteile durch Digitalisierung, aber rund 30 % der Organisationen können KI/erweiterte Analysen nicht sinnvoll nutzen — obwohl technischer Zugang zu den Tools besteht. Ursache: fehlende systematische Datenintegration; Kompetenz- und Talentdaten "schlummern in isolierten Excel-Tabellen oder werden nur sporadisch aktualisiert" [Quelle: ad-hoc-news.de, referenziert BearingPoint-Studie]. Das ist ein struktureller Gegenwind für jede Agent-Plattform, die auf saubere HR-Daten angewiesen ist.
- **Große Plattform-Bewegungen 2025/2026:** Workdays Sana-Launch (März 2026, nach Milliardentransaktion Ende 2025), Oracles Ausbau auf 100+ Agenten, SAPs flächendeckender Joule-Rollout — die Enterprise-Suiten investieren aggressiv in eigene, vorgefertigte Agenten-Portfolios [Quelle: ad-hoc-news.de].

## 5. Gaps & White Spaces

- **Compliance-als-Baukasten-Lücke:** Keine der recherchierten Quellen zeigt einen generischen Agent-Builder (n8n, Copilot Studio, Agentforce, ServiceNow, StackAI, Relevance AI, Dust, UiPath) mit einer vorgebauten deutschen HR-Compliance-Schicht (DSGVO Art. 22, EU AI Act Anhang III, BetrVG, BDSG §26). Diese Kombination — No-Code-Baukasten UND HR-Rechtsschicht — wurde in keiner gesichteten Quelle als bestehendes Produkt beschrieben. Das stützt die im Case beschriebene Moat-These, beruht aber auf der Abwesenheit von Gegenbeweisen in einer Quick-Recherche (5 Suchen + 4 Volltextabrufe), nicht auf einer erschöpften Konkurrenzanalyse.
- **Datenchaos bleibt ungelöst:** ca. 30 % der HR-Organisationen können KI trotz Tool-Zugang nicht nutzen, weil Daten in Silos/Excel verstreut sind [Quelle: ad-hoc-news.de/BearingPoint-Studie]. Kein gesichteter Anbieter positioniert sich explizit als Lösung für "Daten dort abholen, wo HR-Teams heute wirklich arbeiten" (CSV-Exporte, E-Mail-Workarounds) — deckt sich mit dem im Case beschriebenen "Data problem handled like Claude Code"-Ansatz, ist aber eine Beobachtungslücke im Wettbewerbsfeld, kein bestätigtes Whitespace.
- **SMB-Unterversorgung im Agent-Builder-Markt:** Die gesichteten No-Code-Agent-Builder-Vergleichsartikel adressieren durchgängig Enterprise-Teams; ein SMB-taugliches, HR-spezifisches Einstiegsprodukt mit nutzungsbasierter Kleinpreis-Option wurde in keiner Quelle gefunden [Quelle: coworker.ai]. Passt zur Zielsetzung des Case (50-Personen-Firma als valider Einstiegspunkt), ist aber nicht durch eine systematische Pricing-Studie belegt, sondern durch Abwesenheit von Gegenbeispielen.
- **Preistransparenz fehlt branchenweit:** Für keinen der genannten Agent-Builder (generisch oder HR-spezifisch) wurden konkrete Preispunkte gefunden — nur qualitative Hinweise ("usage-based pricing can escalate", "higher enterprise pricing", "scales with complexity"). Für die im Case zentrale Frage nach dem richtigen Pricing-Modell (Plattformgebühr + Nutzung, nicht token-basiert) liefert diese Recherche keine belastbare Evidenz. Insufficient public data found. Searches conducted: siehe Research Log. Recommend primary research (z. B. direkte Preisseiten-Analyse der genannten Anbieter, nicht nur Vergleichsartikel).
- **"Show, don't tell"-GTM-These nicht extern geprüft:** Keine der gesichteten Quellen äußert sich zu Conversion-Raten von Live-Demos im HR-Software- oder Agent-Builder-Vertrieb. Insufficient public data found. Recommend primary research (z. B. Vertriebs-Benchmarks von PLG-/Demo-first-B2B-SaaS-Anbietern außerhalb HR).

## Research Log

**WebSearch-Suchen (5):**
1. `DACH HR-Software Markt Größe Wachstum 2026`
2. `No-Code AI Agent Builder Plattform Unternehmen HR 2026`
3. `HR Software Anbieter KI Agenten Personio Workday SAP SuccessFactors 2026`
4. `EU AI Act Hochrisiko HR Personalabteilung Compliance Anforderungen 2026`
5. `HR AI Startup Deutschland KI Agenten Recruiting 2026`

**WebFetch-Volltextabrufe (4, zur Vertiefung/Verifikation einzelner Suchtreffer):**
1. ad-hoc-news.de — "KI-Agenten revolutionieren HR-Software 2026"
2. ad-hoc-news.de — "KI-HR-Agenten starten, doch Datenchaos bremst Europa"
3. coworker.ai — "11 No-Code AI Agent Builders for Enterprise Teams in 2026"
4. activate-hr.de — "EU AI Act 2026: Was HR im High-Risk-KI-Bereich jetzt wissen muss"

**Total sources reviewed:** über 30 Domains in den Suchergebnislisten gesichtet; 9 davon direkt ausgewertet (5 WebSearch-Synthesen + 4 WebFetch-Volltextabrufe). Wichtigste ausgewertete Domains: haufe.de, hrworks.de, businessresearchinsights.com, de.statista.com, activate-hr.de, handelsblatt.com, coworker.ai, ad-hoc-news.de (2 Artikel), skill-sprinters.de, enkaconsulting.de, it-boltwise.de, ki-spezial.systems, vcgermany.de, tlou.ai, uplifted.today.

**Confidence level: Medium** — Begründung: Die regulatorische Kernaussage (EU AI Act Hochrisiko-Pflicht für HR ab August 2026) ist durch fünf unabhängige Domains übereinstimmend belegt und damit hoch belastbar. Die großen Wettbewerberbewegungen (Workday/Oracle/SAP-Agentenstrategien, BearingPoint-Datenchaos-Statistik) stammen aus direkt per WebFetch geprüften Volltextquellen. Demgegenüber stehen: (a) eine ungeklärte Marktgrößen-Diskrepanz (3,2 Mrd. € vs. 1,8 Mrd. € DACH-HR-Software 2026), (b) widersprüchliche Bußgeld- und Enforcement-Daten zum EU AI Act, (c) eine komplett fehlende Datenbasis für die eigentliche Zielkategorie "HR-Agent-Builder-Markt DACH" als eigene Marktgröße, und (d) keine belastbaren Pricing-Daten für Agent-Builder-Plattformen. Diese vier Lücken sind für die im Case gestellten Kernfragen (Marktgröße der Zielkategorie, Pricing-Architektur) direkt relevant und sollten vor einer Investitionsentscheidung durch Primärrecherche (Analystenreports mit Rohdaten, direkte Anbieter-Preisseiten, ggf. Experteninterviews) geschlossen werden. Als "quick"-Recherche (5 Suchen + 4 Vertiefungs-Fetches statt vollständiger "deep"-Recherche mit 6+ Suchen pro Subthema) ist dies ein solider Erstüberblick, aber keine erschöpfende Marktanalyse.
