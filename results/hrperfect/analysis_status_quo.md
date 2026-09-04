# Status-Quo-Analyse — HRPerfect (HR Harness)

> Basis: research_market.md, research_technology.md, research_problems.md
> Unternehmen: HRPerfect | Datum: 2026-09-01

---

## 1. Relevante Marktchancen

### Was zur Strategie und den Constraints passt

**Der SMB-Einstiegspunkt im Agent-Builder-Markt ist strukturell unterversorgt — genau dort, wo HRPerfects Pricing-Constraint ansetzen muss.** Die recherchierten Vergleichsartikel zum generischen No-Code-Agent-Builder-Markt adressieren fast durchgängig Enterprise-Teams (Operations Leads, Support Manager, Finance Analysts); ein SMB-taugliches, HR-spezifisches Einstiegsprodukt mit nutzungsbasierter Kleinpreis-Option wurde in keiner Quelle gefunden (research_market.md §2, §5). Das deckt sich exakt mit der im Case verlangten Design-Vorgabe, dass ein 50-Personen-Betrieb einen validen kleinen Einstieg braucht. Wichtig: Das ist eine Abwesenheits-Beobachtung, keine bestätigte Marktlücke — die Recherche selbst weist darauf hin, dass dies nicht durch eine dedizierte Segmentierungsstudie belegt ist.

**Die Compliance-als-Baukasten-Kombination wurde in keiner geprüften Quelle als bestehendes Produkt identifiziert.** Keiner der genannten generischen Builder (n8n, Copilot Studio, Agentforce, ServiceNow, StackAI, Relevance AI, Dust, UiPath) wird mit einer vorgebauten deutschen HR-Compliance-Schicht in Verbindung gebracht (research_market.md §5). Das stützt die Kern-Differenzierungsthese des Case — mit dem Vorbehalt, dass dies auf einer Quick-Recherche beruht, nicht auf einer erschöpften Konkurrenzanalyse.

**Schatten-KI ist die stärkste verfügbare Nachfrage-Evidenz für die Grundthese des Case.** 66 % der Mitarbeitenden nutzen laut PagerDuty-Studie 2026 nicht autorisierte KI-Tools trotz Kenntnis des Regelverstoßes, 88 % teilen Arbeitsinhalte mit öffentlichen KI-Tools, 98 % der Organisationen haben Mitarbeitende mit unsanktionierter KI-Nutzung, 34 % geben dabei Kundendaten preis (research_problems.md §2.1). Das belegt: Der Bedarf, KI-gestützt zu arbeiten, existiert bereits und wird bereits gedeckt — nur ungesteuert. Genau diese Lücke (Governance nachrüsten statt Verbot aussprechen) ist die Funktion, die die HR Competency Layer laut Case übernehmen soll. Dies ist die am robustesten belegte Opportunity in der gesamten Recherche.

**Das Procurement-Vertrauens-Gate, das kleine Anbieter aussortiert, ist extern bestätigt — und HRPerfect steht bereits auf der richtigen Seite davon.** "Implementation boutiques ship faster and cost 2-5x less... procurement departments often won't approve smaller firms" (research_problems.md §1.3). HRPerfects 600 bestehende Kundenbeziehungen sind exakt der Vertrauens-Vorsprung, der dieses Gate umgeht — das ist der am klarsten strategiekonforme Fund der gesamten Recherche, weil er unmittelbar an einen bestehenden Vermögenswert andockt statt an eine noch zu beweisende Fähigkeit.

**Die etablierten Suite-Anbieter investieren aktuell primär in vorgefertigte Agenten, nicht in Self-Service-Baukästen — mit einer wichtigen Ausnahme (siehe Abschnitt 4).** SAP, Workday und Oracle bauen 2026 aggressiv eigene Agenten-Portfolios (research_market.md §3b). Oracles "AI Agent Studio" ist die einzige belegte Teilausnahme mit Kunden-Selbstkonfiguration. Das lässt Raum zwischen "vorgefertigte Suite-Agenten" und "generische horizontale Builder" — aber dieser Befund wird durch einen Fund in research_technology.md relativiert (siehe Abschnitt 4, Punkt 1).

### Was ausgeschlossen werden sollte

**Direkter Frontalangriff auf die Agenten-Portfolios der großen Suiten.** Oracle hat bereits über 100 Agenten veröffentlicht, SAP rollt vier Joule-Agenten flächendeckend aus (research_market.md §3b, research_technology.md §4). Eine 70-Personen-Firma mit primär Java-Legacy-Stack kann diese Feature-Breite nicht replizieren — das ist kein Spiel, das HRPerfect gewinnen kann oder sollte spielen.

**Geografische Expansion über DACH hinaus.** Die Compliance-Moat-These (BetrVG, BDSG) ist genuin deutsches Recht — außerhalb DACH entfällt der Kern-Differenzierungsvorteil vollständig. Der Constraint "DACH-first" ist durch die Recherche zusätzlich gestützt, nicht nur strategisch gesetzt.

**Tokenbasierte Endkundenpreisgestaltung.** Der Case schließt dies explizit aus. Die Recherche liefert keinerlei Benchmark, wie viele Token ein typischer HR-Agenten-Case verbraucht (research_technology.md §3) — das bedeutet, der Ausschluss ist pragmatisch richtig (Preistransparenz für Kunden), aber HRPerfect trägt das volle Kostenrisiko selbst, ohne aktuell die Datenbasis, um es zu kalkulieren.

**"KI-Agenten-Plattform" als Kern-Marketingbotschaft.** Nur 4,8 % der HR-Tech-Käufer:innen erwähnten "KI" 2026 proaktiv in Evaluierungsgesprächen (Anstieg von 0 % in 2024), während "Automatisierung" mit über 50 % Nennung Top-Priorität ist (research_problems.md §3.3). Eine Positionierung, die auf der Technologie-Kategorie ("baue deine eigenen Agenten") statt auf konkreten Ergebnissen aufbaut, spricht an der dokumentierten Sprache der Käufer:innen vorbei. Das betrifft unmittelbar die "Show-don't-tell"-GTM-These des Case (dazu mehr in Abschnitt 4).

### Timing-Einschätzung

Das EU-AI-Act-Datum, das im Case implizit als Dringlichkeitstreiber mitschwingt, ist in der Recherche selbst uneinheitlich: Eine Quelle nennt materielle Pflichten ab August 2026, eine andere "volle Durchsetzung der Bußgelder" erst ab August 2027, eine dritte, nicht gegengeprüfte Quelle nennt eine Verschiebung der Gesamtfrist auf Dezember 2027 durch einen "2026 Digital Omnibus" (research_market.md §4, research_technology.md §6). Die grundsätzliche regulatorische Richtung (Hochrisiko-Pflichten kommen) ist durch mehrere unabhängige Quellen gestützt und damit belastbar — das exakte Zeitfenster für eine Dringlichkeits-Erzählung im Vertrieb ist es nicht. Vor jeder kundengerichteten Kommunikation mit konkretem Datum: verifizieren.

---

## 2. Technologie-Fit-Assessment

### Stack-Fit im Detail

**n8n als Orchestrierungsschicht ist produktionsreif für Automatisierung, aber die Eignung für komplexe Agentenlogik ist ungeklärt.** n8n ist primär ein visuelles Workflow-Tool, kein Agent-Framework im Sinne von LangGraph; ob es für mehrstufige HR-Agentenlogik ausreicht oder eine zweite Schicht (z. B. LangGraph-Muster) braucht, wurde in der Recherche nicht abschließend geklärt (research_technology.md §1b, Recherchelücke). Das ist relevant, weil n8n im Case bereits als gesetzt gilt — die Architekturfrage ist also keine Auswahl-, sondern eine Ergänzungsfrage, und aktuell unbeantwortet.

**Claude API/Agent SDK ist produktionsreif als eingebettete LLM-Schicht in Dritt-SaaS**, mit klar dokumentierten Preisen (Haiku 4.5: 1 $/5 $ pro Mio. Token; Sonnet 5: 2 $/10 $; Opus 5: 5 $/25 $; Cache-Rabatt 90 %, Batch-Rabatt 50 %) und einem Enterprise-Plan (20 $/Nutzer/Monat zzgl. API-Nutzung, inkl. SCIM, Audit-Logs, Compliance-API) (research_technology.md §1c, §3). Ein Hinweis zur Datenaktualität: Die Sonnet-5-Preisangabe war laut Quelle bis 31. August 2026 befristet — exakt der Tag vor dem Recherchedatum. Ob sich der Preis danach geändert hat, ist ungeklärt und sollte vor einer Kalkulation neu geprüft werden.

**MCP als Plugin-/Marketplace-Schicht ist ein außergewöhnlich guter architektonischer Fit** — nicht nur als Analogie, sondern als real existierender, schnell wachsender Standard: 97 Mio. monatliche SDK-Downloads bis März 2026 (970-facher Anstieg in 18 Monaten), 41 % der Software-Organisationen laut Stacklok-Report bereits in Produktion, 9.652 aktuelle Registry-Einträge (research_technology.md §1d, §4). Die im Case skizzierte Marketplace/Ecosystem-Schicht kann sich auf einen real existierenden, nicht nur hypothetischen Standard stützen.

**Die HR Compliance Layer hat kein direktes zukaufbares Marktäquivalent** — Guardrail-/Policy-Engine-Anbieter (Galileo, Akto, Maxim AI) liefern die technische Hülle (Gateway-/Kontext-Ebene-Enforcement), nicht das Domänenwissen selbst (research_technology.md §2, §1g). Das bestätigt einerseits die Moat-These (nichts zu kaufen, muss selbst gebaut werden), bedeutet andererseits: Die im Case angesetzte Aufgabe "vorhandenes Wissen API-fähig machen" ist vollständig Eigenleistung ohne technologische Abkürzung — und der Aufwand dafür ist in keiner der drei Recherchedateien beziffert.

**Spannungspunkt: US-CLOUD-Act vs. "DACH-native" Anspruch.** Der im Stack gesetzte LLM-Layer (Claude API, Anthropic, USA) unterliegt laut mehreren Quellen dem US CLOUD Act — ein dokumentiertes Datenhoheitsrisiko für EU-Kunden (research_technology.md §1f, §6). Produktionsreife EU-souveräne Alternativen existieren (Mistral AI, Aleph Alpha/PhariaAI, beide mit voller EU-Datenresidenz), sind aber nicht im aktuellen Tech-Stack vorgesehen. Dieser Zielkonflikt wird in der Recherche für den HRPerfect-Fall nicht aufgelöst und bleibt eine offene Reibungsfläche zwischen der technischen Kernentscheidung (Claude als LLM-Layer, laut Case bereits "neu" gesetzt) und dem zentralen Positionierungsversprechen ("DACH-nativ", Compliance als Moat).

**Dokumentenverarbeitung für deutsche HR-Formate ist technologisch ungeprüft.** VLM-basierte Parser (LlamaParse, LandingAI ADE, Reducto) sind als generische Kategorie produktionsreif, aber keine Quelle bestätigt ihre Eignung für deutsche Spezifika wie kodierte Arbeitszeugnis-Formulierungen oder deutsche Lebenslauf-Konventionen (research_technology.md §1e). Der Case nennt "Lebenslauf, Zeugnisse, Betriebsvereinbarung" jedoch explizit als Teil des Competency-Layer-Scopes — hier klafft eine Lücke zwischen Produktversprechen und geprüfter technischer Grundlage.

### Realistischer Build/Buy-Split für ein Unternehmen dieses Profils

| Komponente | Empfehlung | Begründung |
|---|---|---|
| LLM-Kernschicht | Buy (bereits entschieden) | Claude API produktionsreif; CLOUD-Act-Frage bleibt technologisch offen, EU-Alternativen (Mistral, Aleph Alpha) vorhanden, aber nicht im Stack (research_technology.md §1f, §2) |
| Agent-Orchestrierung | Both — n8n als Basis, evtl. Ergänzung nötig | n8n ist workflow-first; ob es für komplexe HR-Agentenlogik reicht, ist ungeklärt (research_technology.md §1b, §2, Lücke) |
| No-Code-Builder-Oberfläche für HR-Anwender:innen | Build | Keine Quelle zu White-Label-/Embed-Optionen für n8n-basierte Frontends gefunden — vollständige Eigenentwicklung nötig (research_technology.md §2, Lücke) |
| HR Competency Layer | Build (laut Case größtenteils vorhanden) | Kein Marktäquivalent zukaufbar; API-Exponierung ist reine Eigenleistung, Aufwand nirgends beziffert (research_technology.md §2) |
| Plugin-/Marketplace-Ökosystem | Buy (Standard übernehmen), Kuratierung = Eigenleistung | MCP-Standard extern etabliert und wachsend; stützt Case-Prämisse "Markt liefert Integrationen" (research_technology.md §2, §4) |
| Dokumentenverarbeitung (Zeugnisse, Lebensläufe) | Buy, mit Prüfvorbehalt | Generische Parser produktionsreif; Eignung für deutsche Formate ungeprüft (research_technology.md §1e, §2) |
| HRIS-Integrationen/Konnektoren | Buy über Markt (iPaaS/HRIS-Middleware) | Reifer Drittanbietermarkt (Workato, Boomi, Kombo, Apideck, Truto) für SAP SuccessFactors, Workday, Personio, BambooHR, ADP, HiBob (research_technology.md §2, §5) — **aber: keine Quelle zu DATEV-Konnektoren gefunden**, obwohl DATEV im deutschen Mittelstand dominant ist (research_technology.md §5) |
| AI-Guardrails/Policy-Enforcement | Buy, technische Hülle nur | Galileo, Akto, Maxim AI — fragmentierte, aber produktionsreife Kategorie ohne dominanten Standard; liefert keine HR-Domänenlogik (research_technology.md §1g, §2) |

### Technologierisiken speziell für HRPerfect

**Skill-Gap-Risiko (nicht durch Recherche prüfbar — Recherchelücke).** HRPerfects Tech-Stack wird im Case als "primär Java (Legacy-Plattform)" beschrieben; die neuen Schichten (n8n, Python für Claude-API/MCP-Integration) verlangen ein anderes Entwicklungsparadigma. Keine der drei Recherchedateien kann und soll eine Aussage über HRPerfects interne Teamfähigkeit treffen — das ist explizit eine Frage, die nur eine interne Kompetenzprüfung beantworten kann, nicht öffentliche Recherche.

**Kostensensitivität trifft auf eine unkalkulierte Kostenbasis.** HRPerfect befindet sich laut Case in einer "kostendeckend, aber nicht nachhaltig"-Situation (Sales-Funnel bei 50 %). Gleichzeitig fehlt jede Grundlage, den Claude-API-Token-Verbrauch pro typischem HR-Agenten-Case zu schätzen (research_technology.md §3, Lücke) — die zentrale Geschäftsmodell-Prämisse "Nutzungsgebühr statt Token-Preis" lässt sich damit aktuell nicht auf Marge prüfen.

**n8n-Kostenkurve ist kein glatter Verlauf, sondern ein möglicher Sprung.** Cloud-Preise: Starter 24 $/Monat (2.500 Ausführungen), Pro 60 $/Monat (10.000), Business 800 $/Monat (40.000); Enterprise-Verträge werden mit 2.000–3.000 $/Monat oder mehr berichtet (research_technology.md §3). Falls die Plattform-Infrastrukturkosten diesem Muster folgen, steht das im Spannungsverhältnis zum harten Case-Constraint einer durchgängigen Preisskalierung vom 50-Personen-Betrieb bis zum Konzern — die eigene Kostenbasis könnte genau die Sprünge aufweisen, die dem Kunden gegenüber vermieden werden sollen.

---

## 3. Problem-Solution-Fit-Assessment

### Wo die Lösungsrichtung dokumentierte Probleme trifft

**Schatten-KI-Governance ist die stärkste Passung im gesamten Case.** Häufigkeit "sehr hoch", Schweregrad "hoch" in der Häufigkeits-/Schweregrad-Matrix (research_problems.md §4). Die Competency Layer zielt direkt darauf, ein bereits stattfindendes, ungesteuertes Verhalten in einen governierten Rahmen zu überführen — kein hypothetischer, sondern ein empirisch belegter Bedarf (66–98 % Nutzung je nach Messung, research_problems.md §2.1).

**Procurement-Vertrauensdefizit gegenüber kleinen Anbietern** — Häufigkeit "hoch", Schweregrad "hoch" (research_problems.md §4, §1.3). HRPerfects 600 Kundenbeziehungen adressieren dies strukturell, nicht nur behauptet.

**EU-AI-Act-/DSGVO-Nachweispflicht bei der Beschaffung** — Häufigkeit "mittel-hoch", Schweregrad "hoch"; externe Vendor-Assessments dauern 3–6 Monate und binden Legal, Compliance, Risk, IT, Security, Procurement, HR und Product gleichzeitig (research_problems.md §1.4, §4). Eine vorgefertigte Compliance-Dokumentation könnte diesen Prozess strukturell verkürzen — das ist im Case nicht explizit als Feature benannt, wäre aber ein direkter Hebel auf ein dokumentiertes, teures Problem.

**Customer-Size-Mismatch beim Herauswachsen aus bestehenden Tools** — Häufigkeit "mittel", Schweregrad "hoch", der am häufigsten genannte Einzelgrund für Anbieterwechsel im Mid-Market (research_problems.md §1.5, §3.4, §4). Die Design-Vorgabe einer durchgängigen Preisskalierung adressiert dies direkt — sofern sie technisch/kommerziell tatsächlich glatt umsetzbar ist (siehe Abschnitt 2, n8n-Kostenkurve).

### Wo die Lösungsrichtung Probleme NICHT adressiert — und ob das wichtig ist

**"Zu strategisch, nicht akut" — das ist kein Rand-, sondern ein Kernrisiko.** Die Recherche beschreibt für People-Analytics-/Dashboard-Tools ein Muster, das dem aktuellen Problem von HRPerfects eigenem ROI-Analytics-Produkt fast wörtlich entspricht: "Buying software without a clear question leads to dashboards nobody looks at" — bei gleichzeitig guter Produktbewertung (G2-Kategorieschnitt 4,49/5); das Problem liegt im Nutzungskontext, nicht in der Produktqualität (research_problems.md §1.2). Eine "Fähigkeit, eigene Agenten zu bauen" ist eine Ebene abstrakter als ein Punkt-Painkiller — sie ist damit strukturell näher am Scheitern-Muster als an der akuten Schmerzlinderung. Das ist der wichtigste ungelöste Befund dieser gesamten Analyse und wird in Abschnitt 4 vertieft.

**Adoptions-/Change-Management-Scheitern — der am häufigsten dokumentierte Grund für HR-Tech-Scheitern generell — wird durch die Lösungsrichtung nicht adressiert und möglicherweise verschärft.** "Nearly 1 in 4 organizations report that their new HR tech implementations fail to meet adoption expectations", primär wegen fehlendem Change Management und Schulung, nicht wegen Technik (research_problems.md §1.1). Ein Self-Service-Modell verlagert Konfigurationsverantwortung zusätzlich auf die Kund:innen — ohne im Case erkennbare Change-Management-Komponente. Das könnte das dokumentiert größte Scheiternsrisiko eher vergrößern als lösen.

**Punktlösungs-Wildwuchs wird durch die Marketplace-Schicht nicht eindeutig gelöst, sondern möglicherweise reproduziert.** Modulare Einzelkomponenten sparen kurzfristig, kosten langfristig durch Integrations-/Verwaltungsaufwand (research_problems.md §3.2). Eine Plattform aus vielen einzelnen, kuratierten (aber nicht garantierten) Agenten und Plugins trägt strukturelle Ähnlichkeit zu genau diesem Muster — ob die Harness dieses Problem löst oder in neuem Gewand fortsetzt, ist durch die Recherche nicht beantwortet.

**Das "Datenchaos"-Problem wird im Case behauptet, aber nirgends technisch belegt gelöst.** Rund 30 % der HR-Organisationen können KI trotz Tool-Zugang nicht sinnvoll nutzen, weil Kompetenz-/Talentdaten in isolierten Excel-Tabellen liegen (research_market.md §4, BearingPoint-Studie). Der Case behauptet, dies werde "wie bei Claude Code" gelöst (Kunden kennen ihre eigenen Workarounds). Keine der drei Recherchedateien validiert, dass ein No-Code-Harness fragmentierte HR-Daten tatsächlich besser erschließt als bestehende Tools — das ist eine unbewiesene Analogie, keine recherchegestützte Aussage.

### Trifft die Lösung die häufigsten/schwersten Probleme, oder eine Nische?

Gemischt. Von den drei höchsten Einträgen der Häufigkeits-/Schweregrad-Matrix (Schatten-KI, Adoptions-/Change-Management-Scheitern, Procurement-Bias gegen kleine Anbieter — research_problems.md §4) adressiert die Lösungsrichtung zwei stark (Schatten-KI, Procurement-Vertrauen über die 600 Kundenbeziehungen) und lässt einen zentralen Punkt (Adoptions-Scheitern) unadressiert oder verschärft ihn strukturell. Das ist keine Nischen-Lösung — aber auch keine vollständige Deckung der Problemspitze.

---

## 4. Lücken, Risiken & blinde Flecken

### Was die Recherche aufdeckt, worüber sich HRPerfect Sorgen machen sollte

**1. Widerspruch zwischen den Recherchedateien zur Wettbewerbsposition der Suite-Anbieter — mit strategischer Konsequenz.** research_market.md (§3b) findet unter den großen Suite-Anbietern nur Oracles "AI Agent Studio" als Teilausnahme von "Suite-Anbieter baut vorgefertigte Agenten, kein Self-Service-Baukasten". research_technology.md (§4) findet dagegen: Workday hat im Juni 2026 "Workday Build" vorgestellt — mit Developer Agent (Agenten per natürlicher Sprache bauen), Agent-Ready Tools (Datenzugriffs-Guardrails) und Agent Passport (Sicherheits-/Compliance-Zertifizierung). Das ist strukturell dieselbe Grundidee wie HR Harness, bereits von einer der zwei größten HR-Suiten ausgeliefert. Diese beiden Recherchedateien wurden offenbar unabhängig voneinander erstellt und kommen zu unterschiedlich weitreichenden Einschätzungen desselben Wettbewerbsfelds — das ist selbst ein Befund: Die Wettbewerbslandschaft ist noch nicht sauber kartiert, und die optimistischere Lesart (research_market.md: "Suiten bauen nur vorgefertigte Agenten") ist durch einen konkreteren, späteren Fund bereits relativiert. Vor einer Strategieentscheidung sollte dieser Widerspruch aufgelöst werden — die Konkurrenzlage ist enger als die Marktrecherche allein nahelegt.

**2. Die BetrVG-Mitbestimmungspflicht könnte die zentrale GTM-Geschwindigkeit strukturell ausbremsen.** Laut einer 2026 zitierten BAG-Rechtsprechung reicht "objektive Eignung zur Überwachung" für die Mitbestimmungspflicht aus; ohne Betriebsratsbeteiligung ist die KI-Einführung unwirksam, und "rechtzeitige" Information muss vor jeder unumkehrbaren Entscheidung erfolgen (research_technology.md §6; Quellenhinweis: Kanzlei-/Beratungs-Blogs, keine BAG-Urteilstexte direkt geprüft, mittlere Konfidenz). Praktisch jeder mit dem Harness gebaute Agent, der Mitarbeiterdaten verarbeitet, dürfte mitbestimmungspflichtig sein. Das steht in Spannung zur "15 Minuten Live-Demo überzeugt"-GTM-These: Eine überzeugte HR-Person kann einen Agenten möglicherweise nicht einfach live schalten, sondern muss zuerst einen Betriebsrats-Prozess durchlaufen — die Konversions-Geschwindigkeit der Demo und die Deployment-Geschwindigkeit des Produkts könnten deutlich auseinanderfallen.

**3. Die technologische Verteidigungslinie der Harness selbst ist laut Recherche schwach — der Case hat dieses Risiko bereits selbst beobachtet, ohne es aufzulösen.** "Vibe Coding" ermöglicht laut mehreren Quellen SaaS-Nachbauten innerhalb eines Wochenendes bis einer Woche; reine Code-/Feature-Moats gelten 2026 nicht mehr als verlässliche Verteidigung (research_technology.md §4). Der Case selbst berichtet den Präzedenzfall des Wiener Voice-AI-Startups, dessen Plattform in einer Woche vibe-coded kopiert wurde. Das bedeutet: Der Agent-Builder-Teil der Harness ist für sich genommen kein Moat. Übrig bleiben als mögliche Verteidigung: die Competency-Layer-Inhalte selbst, deren architektonische Durchsetzung (Workflow-Gates, noch keine Design-Entscheidung), die 600-Kunden-Distribution und künftig akkumulierte Nutzungsdaten. Keines davon ist im Case bereits als das priorisierte Moat-Element benannt.

**4. Datenlage zur eigentlichen Zielkategorie fehlt vollständig.** Keine Marktgröße für "No-Code-Agent-Builder speziell für HR, DACH" wurde gefunden — diese Schnittmenge existiert in keinem gesichteten Marktreport als eigene Kategorie (research_market.md §1, §2). Die DACH-HR-Software-Marktgröße selbst ist zudem widersprüchlich beziffert (3,2 Mrd. € vs. 1,8 Mrd. €, research_market.md §1). Jede TAM-Kalkulation für HR Harness steht aktuell auf keiner belastbaren Zahlenbasis.

**5. DATEV-Blindspot für den deutschen Mittelstand.** Keine Quelle zu DATEV-Konnektoren gefunden, obwohl DATEV im deutschen Mittelstand für Lohn-/Gehaltsabrechnung weit verbreitet ist (research_technology.md §5). Da HRPerfects bestehende Kundenbasis explizit "von SME bis Enterprise" reicht, ist das ein konkreter, schließbarer blinder Fleck vor einer GTM-Priorisierung des Mittelstandssegments.

**6. Die "Show, don't tell"-These steht im Spannungsverhältnis zur Kaufreue-Evidenz.** 90 % der reuigen HR-Software-Käufer:innen verließen sich ausschließlich auf Herstellerangaben; erfolgreiche Käufer:innen ziehen deutlich häufiger unabhängige Quellen hinzu (research_problems.md §3.1). Eine einzelne, wenn auch überzeugende 15-Minuten-Demo ist strukturell genau das Verhaltensmuster, das mit Kaufreue korreliert ist. Das heißt nicht, dass die Demo nicht konvertiert — sondern dass Konversion allein nicht mit Kundenbindung/Zufriedenheit gleichzusetzen ist, ohne zusätzliche Vertrauensanker (Referenzen, unabhängige Bewertungen).

### Wo die Evidenz dünn oder widersprüchlich ist

**EU-AI-Act-Fristen und Bußgeldhöhen sind über die Recherche hinweg uneinheitlich** — drei verschiedene Daten kursieren (August 2026 für materielle Pflichten, August 2027 für "volle Bußgeld-Durchsetzung" laut einer Quelle, Dezember 2027 laut einer weiteren, nicht gegengeprüften Quelle zum "2026 Digital Omnibus") sowie zwei verschiedene Bußgeldrahmen (15 Mio. €/3 % vs. 35 Mio. €/7 %) (research_market.md §4, research_technology.md §6). Vor jeder kundengerichteten Aussage: am Originaltext verifizieren.

**Die DACH-Kompetenz der recherchierten HR-AI-Startup-Landschaft bleibt dünn.** Nur ein Startup (tlou.ai) wurde konkret identifiziert, mehrere Erwähnungen blieben namentlich nicht auflösbar (research_market.md §3c). Das "Whitespace"-Signal beruht auf Abwesenheit von Gegenbeweisen bei begrenzter Suchtiefe ("quick", 5 Suchen) — keine belastbare Aussage über tatsächliche Marktleere.

**Die Kernanalogie "Claude Code für HR" ist bislang nicht direkt bestätigt.** Das DACH-Praxisbeispiel eines Self-Service-HR-Agenten (~40 % Ticket-Entlastung) belegt technische Machbarkeit, aber nicht eindeutig, dass HR-Fachbereiche selbst (statt IT oder externe Dienstleister) die Agenten bauen (research_problems.md §2.3). Direkte, zitierfähige Aussagen von HR-Entscheider:innen im Sinne von "ich will meine eigenen Agenten bauen können" wurden in keiner der drei Dateien gefunden (research_problems.md §5, explizite Lücke). Die zentrale Produktmetapher des Case ist damit plausibel, aber nicht empirisch bestätigt.

### Welche Annahmen der Lösungsrichtung noch nicht validiert sind

**Annahme: Eine 15-minütige Demo genügt zur Konversion.** Nicht durch Recherche geprüft — keine der drei Dateien äußert sich zu Demo-Conversion-Raten im HR-Software- oder Agent-Builder-Vertrieb (research_market.md §5, explizite Lücke). Im Gegensatz dazu steht die Kaufreue-Evidenz zu Alleinentscheidungen auf Basis von Herstellerangaben (research_problems.md §3.1, siehe oben).

**Annahme: Consulting als bezahlter Akquisekanal, der sich in Plattform-Abos umwandelt.** In keiner der drei Recherchedateien evidenziert. Reines Case-Konstrukt, nicht recherchegestützt.

**Annahme: "Kunden kennen ihre eigenen Datentricks (CSV, E-Mail) und die Harness holt sie dort ab."** Nicht durch Marktevidenz gestützt; die dokumentierte Datenfragmentierung (research_market.md §4) ist als Adoptionsbremse belegt, aber keine Quelle bestätigt, dass ein No-Code-Baukasten dieses Problem strukturell besser löst als bestehende Tools.

**Annahme: Die Preisarchitektur (Plattformgebühr + Nutzung nach Agentenzahl/Fallvolumen, nicht Token) lässt sich profitabel kalkulieren.** Ohne Token-Verbrauchs-Benchmark pro Case (research_technology.md §3, Lücke) ist diese zentrale Geschäftsmodell-Prämisse aktuell nicht überprüfbar — weder zu bestätigen noch zu widerlegen.

---

## 5. Strategisches Positionierungssignal

### Überfüllter Raum, Nische oder echter Whitespace?

Auf der Ebene "KI-Agenten in HR" allgemein: überfüllt. SAP, Workday und Oracle investieren 2026 alle aggressiv in agentische KI-Portfolios (research_market.md §3b, research_technology.md §4); dazu kommt ein breites Feld generischer, horizontaler No-Code-Builder (research_market.md §3a).

Auf der Ebene "Self-Service-Baukasten (nicht vorgefertigte Agenten) für HR, mit eingebauter deutscher Compliance, DACH-fokussiert, horizontal von SME bis Enterprise auf einer Plattform": dünn besetzt, aber **nicht mehr sauberer Whitespace** — der Widerspruch aus Abschnitt 4 (Punkt 1) ist hier entscheidend. Workday Build zeigt, dass mindestens ein globaler Suite-Anbieter bereits strukturell dieselbe Produktidee verfolgt (Self-Service-Agentenbau durch Kund:innen, mit Governance-Bausteinen). Was Workday Build laut Recherche fehlt, ist die deutsche Compliance-Tiefe (BetrVG, BDSG) als eingebaute Schicht — das bleibt der am klarsten offene Winkel. Die treffendste Beschreibung ist daher nicht "weißer Fleck", sondern "umkämpfte, aber noch nicht besetzte Kategorie mit einem spezifisch offenen DACH-Compliance-Winkel".

### Der verteidigungsfähigste Winkel für HRPerfect

Aus der Recherche ergibt sich am klarsten ein Dreiklang, der jeweils einzeln schwer von außen zu replizieren ist:

1. **Die 600 bestehenden Kundenbeziehungen** als Umgehung des dokumentierten Procurement-Vertrauens-Gates (research_problems.md §1.3) — dies ist der einzige Vorteil, der nicht durch technische Nachahmung (Vibe Coding) angreifbar ist.
2. **Die deutsche Compliance-Tiefe als eingebaute, nicht nachträgliche Schicht** — insbesondere ein BetrVG-Mitbestimmungs-Gate im Produkt selbst, das laut Recherche bei keinem geprüften Wettbewerber (auch nicht bei Workday Build oder Oracle AI Agent Studio) gefunden wurde (research_technology.md §6) — mit dem Vorbehalt, dass dies keine erschöpfende Feature-Analyse ist.
3. **Nicht der Agent-Builder selbst** — dieser ist laut Recherche technologisch commodity-artig und vibe-codebar (research_technology.md §4) und sollte weder in der Positionierung noch in der internen Priorisierung als Kernverteidigung behandelt werden.

Gegeben das ROI-Analytics-Präzedenzfall und die Adoptions-Scheitern-Evidenz (Abschnitt 3, 4) sollte die Positionierung nicht mit der abstrakten Plattform-Erzählung ("baue deine eigenen Agenten") beginnen, sondern mit einem konkreten, akuten Painkiller — am naheliegendsten: Schatten-KI-Governance/-Retrofit für Verhalten, das in den Kundenunternehmen bereits stattfindet —, verkauft zuerst in die bestehenden 600 Kundenbeziehungen hinein, nicht horizontal kalt in den DACH-Markt. Das entspricht eher dem im Case selbst benannten Gegenmodell zur "Joy"-Herangehensweise (über-versprochen, unter-geliefert): nicht "wir haben die Plattform für alles", sondern ein enger, belegbarer erster Anwendungsfall, der die Plattform-Fähigkeit sichtbar macht.

---

## Zentrale Spannungsfelder & offene Fragen

Die fünf wichtigsten ungelösten Fragen, die Phase 3 (Hypothesenbildung) adressieren muss:

**1. Wiederholt "HR Harness" als Plattform das "zu strategisch, nicht akut"-Scheitern-Muster von ROI-Analytics — nur eine Abstraktionsebene höher?**
Die Recherche zeigt, dass Tools ohne klare, akute Fragestellung zu Shelfware werden, unabhängig von der Produktqualität (research_problems.md §1.2). Eine "Fähigkeit, Agenten zu bauen" ist abstrakter als ein einzelner Painkiller. Phase 3 muss klären, welcher konkrete, vorgefertigte Erst-Anwendungsfall (nicht: die Baukasten-Fähigkeit selbst) als Einstiegskeil dient.

**2. Übersteht die "15-Minuten-Demo überzeugt"-GTM-Geschwindigkeit den Kontakt mit der BetrVG-Mitbestimmungspflicht?**
Wenn praktisch jeder mitarbeiterdatenverarbeitende Agent laut Recherche mitbestimmungspflichtig ist und ohne Betriebsratsbeteiligung unwirksam wäre (research_technology.md §6), kollidiert das mit dem Versprechen schneller Selbstbedienung. Ungeklärt, mit welcher Verzögerung und welchem Produktbaustein (z. B. ein eingebautes Freigabe-Gate) dies aufgefangen werden soll.

**3. Was genau ist der Moat, mechanisch — jetzt, da Workday Build zeigt, dass mindestens ein globaler Suite-Anbieter dieselbe Grundidee bereits verfolgt und der Builder selbst vibe-codebar ist?**
Ist es die Competency-Layer-Substanz, deren technische Durchsetzung (noch keine Architekturentscheidung), die 600-Kunden-Distribution, oder künftige Nutzungsdaten? Der Case benennt dies explizit als offene Frage (business_case.solution_direction) — die Recherche verengt die Antwortoptionen, löst sie aber nicht auf.

**4. Lässt sich das Geschäftsmodell "Plattformgebühr + Nutzungsgebühr (Agentenzahl/Fallvolumen), nicht Token-basiert" überhaupt kalkulieren, solange kein Token-Verbrauchs-Benchmark pro Agenten-Case existiert und die eigene Infrastrukturkostenbasis (n8n) selbst Sprünge statt einer glatten Kurve zeigt?**
Ohne diese Zahlen ist unklar, ob die geforderte durchgängige Preisskalierung vom 50-Personen-Betrieb zum Konzern technisch-ökonomisch überhaupt glatt darstellbar ist, oder ob HRPerfect intern dieselbe Kostenklippe hat, die dem Kunden gegenüber vermieden werden soll.

**5. Löst der Claude-API-Layer (US, CLOUD-Act-Exposition) den Anspruch "DACH-nativ, Compliance als Kern" ein — oder widerspricht die zentrale technische Entscheidung der zentralen Positionierungsbehauptung?**
EU-souveräne Alternativen (Mistral, Aleph Alpha) sind produktionsreif verfügbar, aber nicht im Stack. Phase 3 muss klären, ob dieser Konflikt durch Kommunikation, durch eine hybride Architektur oder durch einen Stack-Wechsel aufgelöst werden soll — und was das für Kosten und Time-to-Market bedeutet.
