# Business-Modell-Hypothese

> Basis: research_market.md, research_problems.md, research_technology.md, analysis_status_quo.md
> Unternehmen: HRPerfect | Datum: 2026-09-01

*Hinweis zu den Eingaben: `hypothesis_solution.md` lag zum Zeitpunkt dieser Analyse nicht vor (kein paralleler Solution-Hypothesen-Agent in diesem Lauf verfügbar) und wird daher nicht referenziert; die Lösungsrichtung wird stattdessen direkt aus `hrperfect.yaml` (`business_case.solution_direction`) übernommen. `research_technology.md` wurde zusätzlich zur Skript-Vorgabe einbezogen, da es explizit Teil des Arbeitsauftrags war und für die Kosten-/Preislogik (Abschnitt 4) sowie die Risikobewertung (Abschnitt 6) unmittelbar relevant ist. Diese Hypothese ist die beste Antwort auf Basis der vorliegenden Recherche — noch ohne Gegenperspektive/Debatte. Wo die Recherche keine belastbare Zahl liefert, wird das explizit markiert statt stillschweigend geschätzt.*

---

## 1. Ideal Customer Profile (ICP)

### Unternehmensprofil (Company Profile)

| Dimension | Ausprägung |
|---|---|
| Branche | Branchenübergreifend — keine Branchenpriorisierung aus der Recherche ableitbar. **Lücke:** HRPerfects tatsächliche Branchenverteilung innerhalb der 600 Bestandskunden ist internes CRM-Wissen, nicht Teil dieser Recherche. |
| Größe | 250–1.500 Mitarbeitende (gehobener Mittelstand bis kleinerer Konzern) |
| HR-Teamgröße | ca. 5–20 Vollzeitkräfte in der HR-Funktion |
| Jahresumsatz | grob korrespondierend ca. 50–500 Mio. € (Schätzung anhand der Mitarbeitendenzahl, kein direkter Beleg in der Recherche) |
| Geografie | DACH mit Schwerpunkt Deutschland (Strategie-Constraint), Österreich/Schweiz sekundär |
| Tech-Reife | Cloud-affin/SaaS-erfahren — bereits HRPerfect-Job-Shop-Kunde, damit nachgewiesen Cloud-HR-Software im Einsatz; passt zur recherchierten 72-%-Cloud-Adoptionsquote bei DACH-Mittelstands-Neukunden (research_market.md §1). **Aber:** Datenreife ist NICHT automatisch hoch anzunehmen — laut BearingPoint-Studie können ca. 30 % der HR-Organisationen KI trotz Tool-Zugangs nicht sinnvoll nutzen, weil Kompetenz-/Talentdaten in Excel-Silos liegen (research_market.md §4). Das ist ein realistisches Onboarding-Risiko für Teile dieses Segments, kein Ausschlusskriterium. |
| Zusatzfilter 1 | Bereits etablierter Betriebsrat / nachweisliche Mitbestimmungserfahrung (Begründung siehe unten) |
| Zusatzfilter 2 | Bereits HRPerfect-Bestandskunde (Job Shop), mit aktiver Kundenbeziehung (bestehender Customer-Success-/Account-Kontakt) |

### Buyer Persona

**Rolle/Titel:** Personalleiter:in / Head of HR / HR-Direktor:in — bei den größeren Kund:innen im Segment (Richtung 1.500 MA) ggf. CHRO. Berichtslinie typischerweise an Geschäftsführung, COO oder direkt an den Vorstand.

**Ziele:**
- Das eigene Team spürbar von administrativer Last entlasten (siehe "Ein-Personen-HR/alle Hüte gleichzeitig"-Muster, research_problems.md §2.4 — bei diesem ICP zwar nicht Ein-Personen-Setup, aber strukturell verwandte Überlastung im kleinen Team)
- Digitalisierungs-/KI-Erwartungsdruck von der Geschäftsführung glaubwürdig beantworten
- Sichtbaren, vorzeigbaren Fortschritt liefern — **kein zweites "ROI-Analytics"**: technisch fertig, aber ohne Nutzer:innen-Pull (Case-Präzedenzfall; Parallele in research_problems.md §1.2: "Buying software without a clear question leads to dashboards nobody looks at")
- KI-Einführung ohne persönliches Compliance-/Reputationsrisiko vorantreiben

**Frustrationen:**
- Keine Kapazität für lange, generische Tool-Evaluierungszyklen
- Angst vor Fehlkauf/Kaufreue — 28 % der reuigen B2B-Käufer:innen nennen HR-Software als Ursache, 64 % davon waren Alleinentscheider:innen (research_problems.md §3.1)
- Sorge, dass KI-Einführung ohne saubere Betriebsratsbeteiligung rechtlich unwirksam oder verzögert wird
- Generische Anbieter sprechen "KI-Agenten-Plattform"-Sprache statt konkreter Ergebnisse — nur 4,8 % der HR-Tech-Käufer:innen erwähnen "KI" proaktiv, während "Automatisierung" mit über 50 % Top-Priorität ist (research_problems.md §3.3)

**Wie wird evaluiert:** Über die bestehende Vertrauensbeziehung zu HRPerfect — kein Neuanbieter-Vetting, kein Durchlaufen des dokumentierten Procurement-Vertrauens-Gates gegen kleine/unbekannte Anbieter (research_problems.md §1.3) nötig. Bevorzugt einen konkreten, funktionierenden Piloten mit eigenen Daten gegenüber einer rein abstrakten Demo — die Kaufreue-Daten legen nahe, dass eine einzelne Demo allein nicht ausreicht, wenn sie die einzige Entscheidungsgrundlage bleibt (research_problems.md §3.1, vertieft in Abschnitt 5).

### User Persona

HR-Generalist:innen / HR Business Partner im Team der Buyer Persona — bauen und pflegen im Alltag die konkreten Agenten (z. B. Urlaubsantrags-Bot, Policy-Q&A, Zeugnis-/Lebenslauf-Verarbeitung). Bei den größeren Kund:innen im Segment ggf. punktuell unterstützt durch eine "Digital HR"/HRIS-nahe Rolle, aber explizit **ohne** Software-Entwicklungshintergrund — das ist der Kernanspruch der "Claude Code für HR"-Analogie des Case.

**Wichtige Einschränkung:** Diese Trennung (HR baut selbst, nicht IT oder externe Dienstleister) ist durch die Recherche **nicht direkt bestätigt**. Das DACH-Praxisbeispiel eines Self-Service-HR-Agenten (~40 % Ticket-Entlastung) belegt technische Machbarkeit, nicht aber, wer konkret baut (research_problems.md §2.3, explizite Lücke). Diese Hypothese bleibt plausibel, nicht empirisch bestätigt.

### Warum dieses ICP zuerst?

Der Case selbst definiert den Zielmarkt bewusst breit ("horizontal reach across company sizes, not a narrow ICP", von 50-Personen-KMU bis 5.000+-Personen-Konzern) — das ist ein Produkt-/Pricing-Anspruch (die Plattform muss über alle Größen skalieren), aber **kein GTM-Startpunkt**. Für den ersten Vertriebs-Fokus braucht es einen engeren Keil, und die Recherche liefert dafür vier konvergierende Gründe, die alle auf dasselbe Segment zeigen:

1. **Umgeht das dokumentierte Procurement-Vertrauens-Gate**, das kleine/unbekannte Anbieter unabhängig von Qualität aussortiert (research_problems.md §1.3, §4 — Häufigkeit "hoch", Schweregrad "hoch"). Die 600 Bestandskund:innen haben dieses Gate für HRPerfect bereits passiert.
2. **Hat tatsächlich Kapazität zur Selbstbedienung.** Ein-Personen-HR in kleinsten KMU (50–250 MA) ist laut Recherche strukturell überlastet und knapp an Zeit für Tool-Aufbau (research_problems.md §2.4) — genau die Zielgruppe, die die Plattform-Fähigkeit "eigene Agenten bauen" am wenigsten selbst nutzen kann, obwohl sie am lautesten über Arbeitsdruck klagt. Ein Team von 5–20 HR-Kräften hat eher die Bandbreite, einen ersten Agenten tatsächlich zu bauen und zu pflegen.
3. **Mitbestimmungs-Erfahrung reduziert das GTM-Geschwindigkeitsrisiko.** analysis_status_quo.md (Abschnitt 4, Punkt 2) identifiziert die BetrVG-Mitbestimmungspflicht als möglichen Bremsklotz für die "15-Minuten-Demo überzeugt"-These. Ein Unternehmen mit bereits etabliertem Betriebsrat kennt den Ablauf und kann ihn schneller durchlaufen als eines, das diesen Prozess zum ersten Mal führt.
4. **Referenzierbar nach oben.** Der Case-Constraint verlangt explizit "faster-converting smaller entry points that accelerate enterprise deals downstream" — ein Erfolg im gehobenen Mittelstand ist ein glaubwürdiger Referenzpunkt für die 1.500+-MA-Kund:innen im Bestand, während ein Erfolg bei einem 50-Personen-Betrieb dafür weniger Zugkraft hat.

**Explizit ausgeschlossen als Erst-Fokus (nicht als Zielgruppe insgesamt):**
- **Kleinste KMU (50–250 MA):** bleiben ein wichtiges Preis-/Produktsegment (Case-Constraint: kleine Firmen brauchen einen validen Einstieg), sind aber wegen begrenzter HR-Kapazität kein idealer *erster* Beweis-Case.
- **Reines Enterprise-Neugeschäft (kalt, nicht Bestandskund:in):** Der bestehende Enterprise-Vertriebszyklus soll laut Case ergänzt, nicht ersetzt werden — kaltes Enterprise-Geschäft läuft über den bestehenden, langsameren Kanal weiter, ist aber nicht der Hebel für schnelle erste Beweise.

---

## 2. Marktgröße (Market Sizing)

**Zentrale Einschränkung vorab:** Die Recherche findet explizit **keine Marktgrößen-Zahl für die eigentliche Zielkategorie** ("No-Code-Agent-Builder speziell für HR, DACH") — diese Schnittmenge existiert in keinem gesichteten Marktreport als eigene Kategorie (research_market.md §1, §2). Zusätzlich ist bereits die übergeordnete DACH-HR-Software-Marktgröße selbst widersprüchlich beziffert (1,8 Mrd. € vs. 3,2 Mrd. €, research_market.md §1). Die folgende Kalkulation ist daher eine **Bottom-up-Modellrechnung mit explizit markierten Annahmen**, keine recherchebelegte Zahl — vor einer Investitionsentscheidung durch Primärrecherche zu validieren (Empfehlung bereits in research_market.md).

| Segment | Kalkulationslogik | Größe |
|---|---|---|
| **TAM** | ca. 140.000 DACH-Unternehmen mit 50+ Mitarbeitenden *(Schätzung anhand allgemein bekannter volkswirtschaftlicher Strukturdaten — NICHT Teil der vorliegenden Recherche, vor Verwendung an Primärquellen wie Destatis/Statistik Austria/BFS zu verifizieren)* × 60 % mit bestehendem HR-Software-Budget *(Annahme, nicht belegt)* ≈ 84.000 Unternehmen × Ø 8.000 €/Jahr blended ACV über alle Plan-Tiers *(Herleitung siehe Abschnitt 4; niedrig gewichtet, da die meisten Unternehmen in diesem Größenband am unteren Ende liegen)* | **≈ 670 Mio. € /Jahr** |
| **SAM** | ≈ 8.000 Unternehmen — die 600 direkten Bestandskund:innen plus das über HRPerfects Marke, bestehende DACH-Sichtbarkeit im HR-Software-Markt und Referral-Netzwerk realistisch erreichbare Umfeld *(Multiplikator-Schätzung, nicht recherchebelegt)*, bewusst auf mittelgroße bis größere Unternehmen verengt (kleinste KMU sind mit begrenztem Marketing-/Vertriebsbudget einer 70-Personen-Firma schwerer kosteneffizient zu erreichen) × Ø 15.000 €/Jahr ACV *(höher als TAM-Durchschnitt, da SAM zugunsten Mittelstand/Enterprise gewichtet ist)* | **≈ 120 Mio. € /Jahr** |
| **SOM (Y1–Y3)** | 80–150 Kund:innen bis Ende Jahr 3 — realistisch primär aus den 600 Bestandskund:innen konvertiert (ca. 13–25 % Konversionsquote über 3 Jahre, entspricht der ICP-Filterung aus Abschnitt 1) plus einzelne Neukund:innen über Referral × Ø 10.000–18.000 €/Jahr ACV (Jahr 1 näher am unteren Ende durch Pilotpreise, Jahr 3 höher durch Expansion) | **≈ 1,0–2,5 Mio. € ARR Ende Jahr 3** |

**Cross-Check (Top-down, Plausibilitätsprüfung, keine Bestätigung):** Die TAM-Schätzung von ≈ 670 Mio. € entspricht ca. 21–37 % der recherchierten DACH-HR-Software-Gesamtmarktgröße (1,8–3,2 Mrd. €, research_market.md §1). Für eine neue, additive Kategorie (Agent-Building-Layer *neben* bestehenden HR-Kernsystemen, nicht deren Ablösung) ist das eine plausible Größenordnung, aber ausdrücklich kein unabhängiger Beleg — beide Zahlen stammen letztlich aus derselben unsicheren Datenbasis.

**Nicht quantifiziert (bewusste Lücke):** Der im Case genannte Sekundärmarkt — HR-Softwareanbieter und Implementierungspartner als White-Label-Kund:innen der HR Competency Layer — ist in keiner der vier Recherchedateien mit Zahlen hinterlegt. Dieses Potenzial ist als Upside zu verstehen, nicht in TAM/SAM/SOM oben enthalten.

**Was die Zahlen NICHT sind:** Eine belastbare, extern validierte Marktgröße. Sie sind ein transparent hergeleitetes Modell, das primär dazu dient, die Größenordnung der Chance zu testen (SOM Y3 von 1–2,5 Mio. € ARR ist im Verhältnis zu HRPerfects aktuellem ~14-Mio.-€-Umsatz eine ergänzende, aber in drei Jahren allein nicht Existenz-sichernde Größe — das spricht für eine mehrjährige Aufbauperspektive, nicht für einen schnellen vollständigen Ersatz des Kerngeschäfts).

---

## 3. Geschäftsmodell-Optionen

### Option A: Plattformgebühr + Nutzungsbasiert (Hybrid-SaaS)

Basis-Plattformgebühr (gestaffelt nach Plan-Tier) gewährt Zugriff auf HR Competency Layer + Agent Builder; zusätzliche Nutzungsgebühr nach (a) Anzahl aktiver Agenten und (b) monatlichem Fallvolumen — **nicht token-basiert**, wie im Case explizit vorgegeben.

- **Geldfluss:** monatliche/jährliche Abo-Rechnung nach Plan-Tier; Overage-Abrechnung bei Überschreiten des inkludierten Fallvolumens/der Agentenzahl.
- **Unit-Economics-Logik:** HRPerfect trägt die LLM-Infrastrukturkosten (Claude API, n8n-Ausführung) und muss die Nutzungsgebühr so kalibrieren, dass sie diese Kosten mit Marge deckt.
- **Risiko:** Es existiert **kein Benchmark**, wie viele Token/wie viel Rechenzeit ein typischer HR-Agenten-Case verbraucht (research_technology.md §3, explizite Lücke) — die zentrale Prämisse dieses Modells lässt sich aktuell **weder bestätigen noch widerlegen**. Zusätzlich ist die n8n-Kostenkurve selbst kein glatter Verlauf, sondern zeigt Sprünge zwischen Tiers (24 $ → 60 $ → 800 $ → 2.000–3.000+ $/Monat, research_technology.md §3) — falls sich das auf die eigene Infrastrukturkostenbasis überträgt, widerspricht das der geforderten glatten Preisskalierung zum Kunden hin.

**Explizite Spannung (Quality-Rule-Hinweis):** Eine token-basierte Bepreisung wäre technisch der naheliegendste Weg, Kosten direkt weiterzugeben. Die Strategie-Vorgabe schließt das jedoch bewusst aus (Kunden-Verständlichkeit, Differenzierung von generischen Agent-Buildern mit "usage-based pricing can escalate costs"-Kritik, research_market.md §3a). Das zwingt HRPerfect, das Token-Kostenrisiko intern zu tragen und über die Agenten-/Fallvolumen-Nutzungsgebühr indirekt abzufedern — eine Kalkulationsaufgabe, die ohne Verbrauchsbenchmark aktuell offen ist (siehe Risiko 1, Abschnitt 6).

### Option B: Reines Tier-Abo (Flatfee nach Unternehmensgröße)

Klassische SaaS-Staffelung nach Unternehmensgröße/HR-Team-Größe, ohne separate Nutzungsmessung — ähnlich generischer HR-Software-Preismodelle (2–8 $ PEPM Einstieg bis 30–100+ $ PEPM Enterprise, research_problems.md §3.2).

- **Geldfluss:** planbare, vorhersehbare wiederkehrende Abogebühr, für Kund:innen einfach zu verstehen und zu budgetieren — relevant, da die "Customer-Size-Mismatch"-Abwanderung häufig mit unvorhersehbaren Kostensprüngen zusammenhängt (research_problems.md §1.5).
- **Unit-Economics-Logik:** HRPerfect übernimmt die gesamte Nutzungsvarianz innerhalb der Flatfee — ein Kunde mit 50 rechenintensiven Agenten zahlt gleich viel wie einer mit 2 einfachen.
- **Risiko:** Ohne harte Tier-Obergrenzen für Agentenzahl/Volumen erodiert die Marge bei genau den Power-User:innen, die HRPerfect am meisten als Referenz/Upsell-Kandidat:in braucht. Mit harten Obergrenzen nähert sich das Modell faktisch wieder Option A an, nur anders benannt — der vermeintliche Vorteil (Einfachheit) verwässert sich in der Praxis.

### Option C: Services + Software (Consulting-verankertes Hybridmodell)

Bezahlte, strukturierte Pilot-/Einführungs-Sprints (Festpreis, liefern einen ersten funktionierenden Agenten) als eigenständige Umsatzlinie, mit Konversion in ein Plattform-Abo danach.

- **Geldfluss:** Vorab-Zahlung für den Sprint (Services-Umsatz, arbeitsgebunden) + nachgelagertes Abo bei Konversion.
- **Unit-Economics-Logik:** Services-Marge ist niedriger und linear (skaliert mit Personentagen, nicht mit Software-Grenzkosten), senkt aber das "zu strategisch, nicht akut"-Risiko (research_problems.md §1.2) massiv, weil der erste Kontakt ein konkretes Ergebnis liefert statt eines abstrakten Plattform-Versprechens.
- **Risiko:** Skaliert nicht wie Software — ohne diszipliniertes Conversion-Tracking wird HRPerfect faktisch wieder zur Boutique-Beratung, also genau der Anbieterkategorie, die laut Recherche von Procurement strukturell schwerer akzeptiert wird (research_problems.md §1.3) — mit dem Unterschied, dass HRPerfects 600 Bestandsbeziehungen dieses Gate bereits umgehen. Der Case selbst positioniert Consulting explizit **nicht als P&L-Zeile**, sondern als "paid acquisition" — diese Hypothese folgt dieser Einordnung (siehe Abschnitt 5), behandelt Option C hier aber als eigenständige Variante, weil das Template dies verlangt und weil eine reine Akquise-Kosten-Betrachtung die reale Umsatzwirkung im ersten Jahr unterschätzen würde.

### Empfehlung: Option A (Plattformgebühr + Nutzungsbasiert), ergänzt um Option C als GTM-Mechanismus

Option A passt am besten zum harten Strategie-Constraint "Pricing muss von KMU bis Enterprise auf derselben Plattform skalieren" — eine reine Flatfee (Option B) tendiert dazu, entweder bei Power-User:innen unrentabel zu werden oder sich in der Praxis wieder in Nutzungsstaffeln aufzulösen. Option C ist keine Alternative zu Option A, sondern deren Vorstufe: bezahlte Pilot-Sprints als Einstiegsangebot, die in Option-A-Abos konvertieren — exakt die im Case beschriebene "Consulting as paid acquisition"-Logik. Diese Kombination wird in Abschnitt 5 als Go-to-Market-Motion ausgearbeitet.

**Wichtigster offener Vorbehalt:** Die Empfehlung für Option A steht und fällt mit einer Zahl, die in keiner der vier Recherchedateien existiert — dem Token-/Rechenkosten-Verbrauch pro typischem Agenten-Case. Diese Empfehlung ist daher eine **Richtungsentscheidung**, keine kalkulierte Preisfreigabe (siehe Risiko 1, Abschnitt 6).

---

## 4. Preismodell

- **Struktur:** Zwei-Komponenten-Modell — gestaffelte Basis-Plattformgebühr (Starter / Professional / Enterprise) + Nutzungsgebühr nach aktiver Agentenzahl und monatlichem Fallvolumen, nicht token-basiert.

| Tier | Zielgröße | Basisgebühr | Inkludiert | Geschätzter ACV |
|---|---|---|---|---|
| Starter | ca. 50–250 MA | 490 €/Monat | bis zu 3 aktive Agenten, 500 Fälle/Monat | ≈ 5.900–9.000 €/Jahr |
| Professional (ICP-Tier) | ca. 250–1.500 MA | 1.900–3.900 €/Monat | bis zu 15 aktive Agenten, 5.000 Fälle/Monat | ≈ 23.000–47.000 €/Jahr |
| Enterprise | 1.500+ MA | ab ca. 8.000 €/Monat, individuell verhandelt | unlimitierte Agenten, individuelles Volumen, SSO/Audit-Log/Compliance-API | ≈ 100.000+ €/Jahr |

*Alle Preispunkte sind eine unvalidierte Hypothese — die Recherche findet für keinen einzigen HR- oder generischen No-Code-Agent-Builder einen konkreten öffentlichen Preispunkt (research_market.md §5: "Für keinen der genannten Agent-Builder... wurden konkrete Preispunkte gefunden"). Vor Rollout zu testen, z. B. mit einer Van-Westendorp-Preissensitivitätsbefragung unter Bestandskund:innen.*

- **Preisspanne (Overall):** ≈ 490 €/Monat (Einstieg) bis 8.000+ €/Monat (Enterprise, individuell) — bewusst ohne Preisdeckel nach oben, um Expansion nicht künstlich zu begrenzen.
- **ACV-Zielwert für das ICP:** ≈ 30.000 € (Spanne 23.000–47.000 € je nach Größe innerhalb des Professional-Tiers).
- **Expansionslogik:**
  - Mehr aktive Agenten pro Kund:in über Zeit (organisches Wachstum der Nutzung)
  - Steigendes Fallvolumen bei erfolgreicher Adoption
  - Aufstieg zwischen Plan-Tiers bei Mitarbeiterwachstum des Kunden — bewusst **kein** Preisverfall bei Wachstum vorgesehen, gezielt gegen das dokumentierte "Customer-Size-Mismatch"-Abwanderungsmuster (häufigster Einzelgrund für Anbieterwechsel im Mid-Market, research_problems.md §1.5, §3.4)
  - Perspektivisch (nicht Day-1): Marketplace-/Skills-Ökosystem mit Rev-Share-Anteil, sobald die MCP-basierte Plugin-Schicht eine kritische Masse an Drittanbieter-Skills erreicht (research_technology.md §1d, §4) — heute noch kein tragfähiges eigenständiges Modell mangels Ökosystem (Henne-Ei-Problem), aber ein plausibler zukünftiger Expansionshebel
- **Wettbewerbs-Anker (was zahlen Kund:innen heute?):**
  - Boutique-/Agentur-Punktlösungen: keine öffentlichen Preispunkte gefunden, aber qualitativ "2–5x günstiger als Big-4-artige Anbieter" beschrieben (research_problems.md §1.3) — impliziert eher niedrige vier- bis niedrige fünfstellige Jahresbeträge, nicht verifiziert
  - HR-Software allgemein: 2–8 $ PEPM (Einstieg) bis 30–100+ $ PEPM (Enterprise-Suiten mit Analytics) (research_problems.md §3.2) — Referenzrahmen, nicht spezifisch für Agent-Builder
  - n8n als Infrastruktur-Kostenreferenz (kein Endkundenpreis): 24–800 $/Monat Cloud-Tiers, Enterprise-Verträge 2.000–3.000+ $/Monat berichtet (research_technology.md §3)
  - Claude Enterprise: 20 $/Nutzer/Monat + separat abgerechnete API-Nutzung (research_technology.md §1c) — Referenzpunkt für Enterprise-Preisstaffel-Architektur
  - **Explizite Lücke:** kein einziger konkreter Preispunkt für einen vergleichbaren HR- oder generischen Agent-Builder wurde gefunden. Die obige Preisspanne ist eine Hypothese ohne direkten Wettbewerbsbeleg.

---

## 5. Go-To-Market-Strategie

- **Primärer Kanal:** Bestandskunden-Expansion in die 600 bestehenden Job-Shop-Kundenbeziehungen — nicht kaltes horizontales DACH-Outbound. Ergänzt um "Consulting-as-Acquisition" (Option C, Abschnitt 3): ein bezahlter, strukturierter Pilot-Sprint (fester Umfang, liefert einen ersten funktionierenden Agenten), der als Conversion-Mechanismus zum Plattform-Abo dient — explizit kein kostenloser Demo-Call.
  - **Wichtige Korrektur zur "15-Minuten-Demo überzeugt"-These des Case:** Die Kaufreue-Daten zeigen, dass 90 % der reuigen HR-Software-Käufer:innen sich ausschließlich auf Herstellerangaben verließen, während erfolgreiche Käufer:innen deutlich häufiger unabhängige Quellen/Referenzen hinzuziehen (research_problems.md §3.1). Eine einzelne, überzeugende Demo mag konvertieren, korreliert aber strukturell mit dem Muster, das zu Kaufreue führt. Empfehlung: die Demo/den Pilot-Sprint von Anfang an mit sichtbaren Referenzkund:innen aus der eigenen Pilot-Kohorte flankieren, nicht auf die Demo allein setzen.
  - **Auswahl des Erst-Agenten bewusst treffen:** Der erste im Piloten gebaute Agent sollte ein administrativer/Service-Anwendungsfall sein (z. B. Urlaubsantrags-/Policy-Q&A-Agent, Zeugnis-/Dokumentenverarbeitung) — **nicht** Recruiting/Bewerber:innen-Bewertung. Letzteres fällt unter EU-AI-Act-Anhang-III-Hochrisiko-Klassifizierung (research_technology.md §6) und löst die volle Art.-9–15-Pflichtenkette aus. Ein administrativer Agent verarbeitet zwar weiterhin wahrscheinlich mitbestimmungspflichtige Mitarbeitendendaten (die BAG-Rechtsprechungs-Schwelle "objektive Eignung zur Überwachung" ist niedrig, research_technology.md §6) — vermeidet aber die zusätzliche AI-Act-Hochrisiko-Compliance-Last und ist damit der schnellere erste Beweis-Case.
- **Erste 10 Kund:innen:** Gefiltert aus den 600 Bestandskund:innen auf das ICP-Profil (250–1.500 MA, aktive Kundenbeziehung mit Customer-Success-Kontakt, im Idealfall bereits geäußerte Frustration mit ROI-Analytics oder anderen "zu abstrakten" Tools als Gesprächseinstieg, etablierter Betriebsrat). Ansprache über bestehende Account-Management-/Customer-Success-Kontakte, **nicht** neue Kaltakquise. Pitch startet mit dem konkreten Painkiller (z. B. Schatten-KI-Governance-Retrofit — die am robustesten belegte Nachfrage-Evidenz der gesamten Recherche, 66–98 % ungesteuerte KI-Nutzung, research_problems.md §2.1), nicht mit der abstrakten Plattform-Erzählung (Empfehlung aus analysis_status_quo.md, Abschnitt 5).
- **Sales-Motion:** Sales-assisted — weder rein Self-Serve noch reiner Enterprise-RFP-Zyklus. Geführter Einstieg über den Consulting-Sprint mit Account-Team, danach Self-Service-Erweiterung (mehr Agenten bauen) innerhalb des Accounts nach initialer Aktivierung. Für das Enterprise-Tier bleibt der bestehende, langsamere Enterprise-Vertriebszyklus (RFP, Security-Review, Betriebsratseinbindung) parallel bestehen, wie im Case als "muss ergänzt, nicht ersetzt werden" vorgegeben.
  - **Explizite Spannung:** Die beiden Case-Constraints "Enterprise-Zyklus ergänzen, nicht ersetzen" und "Pricing darf nicht Enterprise-only sein" ziehen in unterschiedliche Richtungen — ein reines Product-Led-Growth-Modell würde langfristig auf Reduktion des Sales-Aufwands zielen, während ein reines Enterprise-Modell den KMU-Einstieg verletzt. Die hier empfohlene Sales-assisted-Hybrid-Motion (geführter Start, dann Self-Service-Erweiterung) ist der Versuch, beide Constraints gleichzeitig zu erfüllen, ist aber selbst unvalidiert.

---

## 6. Zentrale kommerzielle Risiken

| Risiko | Warum es wichtig ist | Mitigation |
|---|---|---|
| Unkalkulierte Unit Economics — kein Token-/Rechenkosten-Benchmark pro Agenten-Case (research_technology.md §3) | Die zentrale Prämisse des empfohlenen Geschäftsmodells (Nutzungsgebühr statt Token-Preis) lässt sich aktuell weder bestätigen noch widerlegen. Fehlkalkulation bedeutet entweder Margenverlust oder zu hohe Kundenpreise. | Sofortige interne Kosten-Pilotierung: reale Claude-API- und n8n-Ausführungskosten für 5–10 repräsentative HR-Agenten-Cases messen, bevor Preise final fixiert werden. |
| "Zu strategisch, nicht akut" — Wiederholung des ROI-Analytics-Scheiterns auf einer Ebene abstrakter (analysis_status_quo.md, Abschnitt 4/5) | Die Baukasten-Fähigkeit selbst ist ein Plattform-Versprechen, kein akuter Painkiller. Research_problems.md §1.2 zeigt: Produktqualität ist bei diesem Scheitern-Muster nicht die Ursache — der fehlende akute Anlass ist es. | GTM startet konsequent mit einem konkreten Erst-Anwendungsfall (Schatten-KI-Governance/administrativer Agent), nicht mit der Plattform-Erzählung. Siehe Abschnitt 5. |
| BetrVG-Mitbestimmungspflicht bremst Time-to-Value und kollidiert mit der "schnelle Demo überzeugt"-GTM-Geschwindigkeit (research_technology.md §6) | Praktisch jeder mitarbeitendendatenverarbeitende Agent dürfte laut zitierter BAG-Rechtsprechung mitbestimmungspflichtig sein; ohne Betriebsratsbeteiligung ist die Einführung unwirksam. | ICP bewusst auf Unternehmen mit bereits etabliertem Betriebsrat eingegrenzt (Abschnitt 1); ein produktseitiges "Freigabe-Gate" mit vorstrukturierter Betriebsvereinbarungs-Dokumentation als Beschleuniger prüfen (noch keine Architekturentscheidung, siehe analysis_status_quo.md Frage 2). |
| Preismodell ohne jede Wettbewerbsvalidierung — kein einziger öffentlicher Preispunkt für vergleichbare Agent-Builder-Angebote gefunden (research_market.md §5) | Risiko systematischer Fehlbepreisung in beide Richtungen: zu hoch schreckt ab, zu niedrig verschenkt Marge und ist später schwer nach oben zu korrigieren (siehe Customer-Size-Mismatch-Abwanderungsmuster). | Preissensitivitätstest (z. B. Van-Westendorp) mit einer Stichprobe von Bestandskund:innen vor breitem Rollout; erste Kohorte zu expliziten Pilotkonditionen mit Lernschleife, nicht zu finalen Listenpreisen. |

**Fragilste Annahmen im Geschäftsmodell:**
- Dass sich die Nutzungsgebühr (Agentenzahl × Fallvolumen) profitabel kalibrieren lässt, ohne Kenntnis der tatsächlichen Rechenkosten pro Fall — die mit Abstand fragilste Annahme, weil praktisch die gesamte Preisarchitektur in Abschnitt 4 darauf aufbaut.
- Dass Consulting-Pilot-Sprints zuverlässig in Abo-Kund:innen konvertieren — in keiner der vier Recherchedateien evidenziert, reine Case-Konstruktion. Ohne belastbare Konversionsquote (Zielgröße vorschlagen und tracken, z. B. ≥ 50 %) besteht das Risiko, dass HRPerfect zeitlich in Services-Delivery statt Plattform-Vertrieb gebunden bleibt.
- Dass eine kurze Demo/ein kurzer Pilot ausreicht, um Alleinentscheider:innen in kleineren Organisationen zu überzeugen, ohne die dokumentierte Kaufreue-Dynamik (Verlass auf Herstellerangaben) zu reproduzieren.
