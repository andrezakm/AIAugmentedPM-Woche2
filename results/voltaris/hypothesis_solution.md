# Solution Hypothesis

> Based on: research_market.md, research_technology.md, research_problems.md, analysis_status_quo.md
> Company: Voltaris | Date: 2026-09-01

## 1. Concrete Solution Description

**Einordnung vorab:** Die in `input.yaml` beschriebene `solution_direction` ("Speicher end-to-end integrieren... für die gesamte Zielgruppe der Eigenheimbesitzer") wird hier nicht unverändert übernommen, sondern auf Basis der Recherche und der Status-Quo-Analyse geschärft. Zwei Erkenntnisse verändern den Zuschnitt gegenüber dem Ausgangstext spürbar: (1) Reine Preis-Arbitrage ohne PV ist laut mehreren unabhängigen Quellen wirtschaftlich dünn bis "komplett witzlos" (research_market.md, research_problems.md) — ein Angebot, das "Eigenheimbesitzer" pauschal adressiert, würde einen erheblichen Teil der eigenen Kundenbasis mit einem ökonomisch nicht tragfähigen Versprechen ansprechen. (2) Volle vertikale Hardware-Integration nach Enpal-Vorbild ist ein belegt zweigeteilter Weg (Enpal: Erfolg; Zolar: Insolvenz, strukturell ähnliches Modell, gleiches Jahr) und passt nur bedingt zu Voltaris' Kapitalrestriktion und dem Wunsch, keine schwerfällige Hardware-Marke zu werden. Die folgende Hypothese behält den Kernmechanismus der `solution_direction` bei (Automatisierung statt Verhaltensänderung), verengt aber die Zielgruppe und wählt einen leichter gewichteten Integrationsweg — gestützt auf die Empfehlung in `analysis_status_quo.md`, Abschnitt 5.

**Was die Lösung tut, für wen, in welchem Kontext:**
Voltaris erweitert sein bestehendes App-/Tarif-Angebot um ein Speicher-Abo (Hardware-as-a-Service): Kundinnen und Kunden mit eigener Photovoltaikanlage — primär aus der bestehenden Voltaris-Kundenbasis mit dynamischem Tarif — mieten über Voltaris einen Batteriespeicher, den ein kuratiertes Partner-Installationsnetzwerk liefert, installiert und wartet. Die zentrale Voltaris-Software (Erweiterung des bestehenden Python-Backends) übernimmt die Lade-/Entlade-Steuerung gegen den Day-Ahead-Preis und optimiert den PV-Eigenverbrauch; die bestehende App zeigt den Euro-Vorteil sichtbar an. Primärer Kontext ist damit ein **Attach-on-Produkt zur bestehenden Kundenbeziehung**, kein eigenständiges Neukundengeschäft ab Tag eins — das nutzt die vorhandene Vertrauensbeziehung und, wichtiger, die vorhandenen Verbrauchs-/Erzeugungsdaten dieser Kunden für eine personalisierte, ehrliche Ersparnisprognose statt eines generischen Rechners.

**Zielgruppen-Schärfung (Kernaussage dieser Hypothese):**
- **Kernsegment:** Bestehende Voltaris-Kunden mit eigener PV-Anlage, insbesondere das Nachrüstsegment (PV-Anlagen 10–15+ Jahre alt, auslaufende oder gesunkene EEG-Einspeisevergütung) — der laut `analysis_status_quo.md` ökonomisch am besten gestützte Anknüpfungspunkt.
- **Sekundärsegment (kleiner, aber real):** Haushalte ohne PV, aber mit hohem Verbrauch (ab ca. 3.500–4.000 kWh/Jahr, typischerweise durch E-Auto und/oder Wärmepumpe) — laut `research_market.md` die einzige Untergruppe, für die reine Arbitrage ohne PV nachweisbar wirtschaftlich sein kann. Kein Massenmarkt, aber ein begründbarer Zweitfall.
- **Explizit nicht adressiert (Kernaussage, kein Nebeneffekt):** Durchschnittshaushalte ohne PV und ohne überdurchschnittlichen Verbrauch. Für dieses Segment liefert die Recherche keine tragfähige Wirtschaftlichkeitsgrundlage — ein Angebot dafür würde ein Versprechen verkaufen, das die eigenen Recherchedaten nicht stützen.
- **Research-Lücke, die vor Rollout zu schließen ist:** Der PV-Anteil von Voltaris' eigener Bestandskundenbasis ist in keiner der Recherchedateien beziffert (es handelt sich um interne Kundendaten). Die gesamte Kernsegment-Größe dieser Hypothese hängt an dieser einen, aktuell unbekannten Zahl — siehe Annahme 1 in Abschnitt 5.

**Produkt-/Service-Typ:** Hybrid — ein abo-/leasingbasiertes Hardware-as-a-Service-Produkt ("Speicher-Abo"), eingebettet als Erweiterungsmodul in die bestehende SaaS-/App-Plattform, mit einer Service-/Installationsschicht über ein kuratiertes (nicht selbst betriebenes) Partnernetzwerk. Kein Marktplatz mit freier Endkundenauswahl aus vielen konkurrierenden Angeboten, sondern ein kuratiertes Angebot mit zunächst 1–2 sorgfältig ausgewählten Speicherherstellern.

**3–5 Kernfähigkeiten, die die Lösung tragen:**

1. **Speicher-Abo statt Kauf** — Hardware bleibt außerhalb von Voltaris' Bilanz (Leasing-/Finanzierungspartner, analog zu am Markt bestehenden Modellen wie Bnewable oder EWE, siehe `research_technology.md`), Kunde zahlt eine monatliche Rate statt eines Investitionsbetrags im vierstelligen Bereich.
2. **Automatisierte Lade-/Entlade-Steuerung gegen Day-Ahead-Preis plus PV-Eigenverbrauchsoptimierung** — direkte Erweiterung der bestehenden Marktanbindung im Python-Backend um eine Steuerungslogik für die zu Beginn unterstützten Speichermarken.
3. **Euro-Ersparnis-Dashboard** — Erweiterung der bestehenden "Verbrauchs-Insights"-Funktion der App um eine speicherspezifische, auf echten Kundendaten (nicht generischen Annahmen) basierende Anzeige des monatlichen/jährlichen Euro-Vorteils.
4. **Kuratiertes Partner-Installationsnetzwerk mit Kapazitäts-/Qualitätsmanagement** — keine eigenen Montage-Kolonnen (respektiert den Constraint aus `input.yaml`), aber mit einer expliziten Steuerungsschicht (Terminvergabe, SLA-Monitoring), die auf das in der Recherche dokumentierte Risiko reagiert, dass Partner-/Herstellersupport nicht im Tempo der Nachfrage mitwächst (Fenecon-Beispiel, `research_problems.md`).
5. **Garantiekontinuitäts-Zusage** — eine vertragliche Absicherung (Versicherungslösung oder Ersatzteil-/Weiterbetriebsfonds), die greift, falls ein Speicherhersteller ausfällt oder Garantiebedingungen nachträglich verschlechtert werden. Adressiert eine von der Recherche explizit als ungelöst identifizierte Marktlücke (Varta-Insolvenz, Sonnen-Gerichtsurteil zu Garantiebedingungen, Growatt-Garantieverweigerungen — `research_market.md`, Abschnitt 5).

### User Journey Sketch

Ausgangspunkt: eine bestehende Voltaris-Kundin/ein bestehender Kunde mit dynamischem Tarif und eigener PV-Anlage, App bereits installiert.

1. **Minute 0–1 — Personalisierter Anstoß:** In-App-Hinweis/Push-Notification, ausgelöst durch vorhandene Kundendaten (z. B. "Deine PV-Anlage ist seit über 10 Jahren in Betrieb — deine Einspeisevergütung sinkt bald. Sieh, was ein Speicher für dich bringen würde.").
2. **Minute 1–3 — Kurz-Check:** Nutzer beantwortet 3–4 Fragen, die die App teils schon aus Bestandsdaten kennt (PV-Größe, Baujahr, E-Auto/Wärmepumpe vorhanden, Eigenheim ja/nein) — kein Neuaufbau eines Kundenprofils von null.
3. **Minute 3–5 — Personalisierte Schätzung:** App zeigt eine Ersparnis-Bandbreite in Euro/Jahr auf Basis der eigenen historischen Verbrauchs-/Erzeugungsdaten (nicht eines generischen Rechners), plus die passende Abo-Rate für die verfügbaren Speichergrößen. Annahmen werden transparent ausgewiesen, keine Verschleierung der Bandbreite.
4. **Minute 5–7 — Paketwahl:** Nutzer sieht 2–3 Abo-Pakete (Speichergröße × Laufzeit), gekoppelt an die zu Beginn unterstützten Partnerhersteller, mit klar ausgewiesener monatlicher Rate und Kündigungsbedingungen.
5. **Minute 7–9 — Unverbindliche Terminbuchung:** Statt eines sofortigen Vertragsabschlusses bucht der Nutzer einen Vor-Ort- oder Video-Check-Termin mit einem Partner-Installateur direkt in der App (Kalender-Slot-Buchung). Das ist der eigentliche Conversion-Punkt der ersten zehn Minuten — der Vertragsabschluss selbst folgt erst nach dem technischen Check.
6. **Minute 9–10 — Erwartungsmanagement:** Bestätigung mit realistischer Zeitangabe zur Terminbestätigung (z. B. "in der Regel innerhalb von X Wochen") — bewusst gegen die in der Recherche dokumentierte Frustration über unklare/lange Wartezeiten bei Installationen gesetzt, statt sie zu verschweigen.

**Research-Lücke:** Ob eine Terminbuchung tatsächlich der richtige Ziel-Zustand für die ersten zehn Minuten ist (statt z. B. eines sofortigen Abschlusses oder einer unverbindlichen Warteliste), wurde nicht getestet — das ist eine Produktannahme dieser Hypothese, kein recherchierter Fakt.

## 2. Value Proposition

**Core value (one sentence):** Der wirtschaftliche Vorteil des dynamischen Tarifs entsteht automatisch, in Euro sichtbar gemacht — ohne dass Kundinnen und Kunden ihr Verhalten aktiv ändern müssen.

**Differenzierung:**
- Gegenüber Voltaris' eigenem Status quo (reines App-Nudging): Diese Lösung behebt die Ursache — mangelndes Verhaltens-Engagement, extern belegt durch Verivox (nur ~6,4 % Ersparnisunterschied zwischen aktiver Lastverschiebung und Nicht-Verschiebung, `research_problems.md`) — statt sie mit weiteren Nudges zu behandeln.
- Gegenüber vollintegrierten Hardware-Anbietern (Enpal, 1KOMMA5°): Voltaris baut keine eigene Montage-/Vertriebsorganisation auf und kauft keine Hardware auf eigene Bilanz, sondern bleibt bewusst schlanker — mit dem Kompromiss, dass die Kontrolle über Installationsqualität und -tempo bei Partnern liegt statt im eigenen Haus.
- Gegenüber leichtgewichtigen Software-first-Wettbewerbern (Tibber Pulse, Octopus/Kraken): Voltaris geht einen Schritt weiter in Richtung physischer Hardware, weil der recherchierte ökonomische Hebel eines echten Speichers real ist (12,7 % Kostensenkung durch reine Eigenverbrauchsoptimierung, zusätzlich bis zu 6 Prozentpunkte durch aktive Reaktion auf Preissignale, laut Bamberg/Würzburg/Zürich/Chemnitz-Studie, `research_market.md`) — größer als der eines reinen Messgeräts wie Tibber Pulse, mit entsprechend höherem Kapital- und Betriebsrisiko als Kehrseite.
- Gegenüber 1KOMMA5°, dem strukturell nächsten Vergleichsfall: Voltaris kommt aus der umgekehrten Richtung (vertrauensvolle Tarif-/App-Beziehung zuerst, Hardware danach) — laut Recherche eine aktuell unbesetzte Positionierung (`analysis_status_quo.md`, Abschnitt 5), aber unbewiesen und kein Whitespace im Sinne von risikoarm.
- Die Garantiekontinuitäts-Zusage (Kernfähigkeit 5) ist die konkreteste Einzeldifferenzierung: Keine der recherchierten Quellen beschreibt einen Anbieter, der dieses Problem heute aktiv löst.

**Retention Hook (was ein Nutzer bei Kündigung verliert):**
Bei Kündigung fällt der Speicher auf die meist deutlich simplere Werks-Standardsteuerung des Herstellers zurück — die Kundin verliert die Day-Ahead-Preisoptimierung zusätzlich zum reinen PV-Eigenverbrauch, das vereinheitlichte Euro-Dashboard über Tarif und Speicher hinweg, den Wartungs-/Supportzugang über Voltaris' Partnernetzwerk und die Garantiekontinuitäts-Absicherung (müsste dann direkt mit dem Hersteller verhandeln). Da der Speicher im Abo-/Leasingmodell nicht im Eigentum der Kundin steht, entsteht zusätzlich eine vertragliche Bindung (Rückgabe- oder Auskaufsregelung), deren genaue Ausgestaltung noch offen ist (siehe Annahme 5, Abschnitt 5).

## 3. Feature Set

### MVP

- Speicher-Abo-Angebot in der bestehenden App, beschränkt auf 1–2 kuratierte Partnerhersteller mit nachweislich stabiler, dokumentierter Drittanbieter-API (laut `research_technology.md` z. B. ein Hersteller mit seit 2024 offizieller Tesla-FleetAPI oder ein Hersteller mit lokaler SMA-/Fronius-artiger Schnittstelle)
- Kern-Steuerungslogik: Laden/Entladen gegen Day-Ahead-Preis, PV-Eigenverbrauchsoptimierung, als Erweiterung des bestehenden Python-Backends
- Euro-Ersparnis-Dashboard (Erweiterung der bestehenden Verbrauchs-Insights-Funktion)
- In-App-Terminbuchung mit einer kleinen Zahl regional vetteter Installationspartner (kein bundesweiter Vollausbau zum Start)
- Kurz-Fragebogen plus personalisierte Ersparnisschätzung auf Basis vorhandener Kundendaten (PV-Größe, Baujahr, E-Auto/Wärmepumpe)
- Leasing-/Finanzierungsvertrag über einen externen Partner (kein Kauf auf eigene Bilanz)

**Anmerkung zur Herstellerwahl:** sonnen böte sich für den MVP-Start eher weniger an, weil die recherchierte Cloud-only-API mit eingeschränktem lokalem Zugriff (`research_technology.md`) mehr Integrationsrisiko trägt als Hersteller mit dokumentierter, stabiler Dritt­anbieter-Schnittstelle. Das ist eine eigene Einschätzung dieser Hypothese auf Basis der recherchierten technischen Fakten, keine explizite Empfehlung aus der Recherche selbst.

### V2 (defensibility layer)

- Garantiekontinuitäts-/Ersatzteilfonds-Absicherung als eigenständiges, mitversichertes oder zubuchbares Feature — direkte Umsetzung der identifizierten Marktlücke
- Erweiterung des Partnerherstellerkatalogs über die anfänglichen 1–2 Marken hinaus, gestützt durch eine herstellerunabhängige Integrationsschicht (Eigenbau einer dünnen Abstraktionsschicht oder Lizenzierung eines bestehenden Anbieters wie gridX/Solar Manager, statt jede Hersteller-API einzeln und dauerhaft selbst zu pflegen)
- Automatisierte §14a-Netzentgelt-Optimierung als integriertes Feature (registriert/optimiert die steuerbare Last automatisch für den Netzentgeltrabatt, wo anwendbar) — nutzt einen bereits recherchierten, konkreten regulatorischen Mechanismus (110–200 €/Jahr laut `research_technology.md`; `research_market.md` nennt an anderer Stelle 120 bis über 400 €/Jahr je nach Modul — Diskrepanz zwischen den beiden Recherchedateien nicht aufgelöst)
- Partner-Kapazitäts-/Qualitäts-Dashboard (B2B2C-Werkzeug für Installationspartner: Terminlast, SLA-Einhaltung, Eskalationspfad) als direkte Antwort auf das dokumentierte Skalierungsrisiko von Support-/Installationskapazität
- Wärmepumpen-Anbindung als nächster steuerbarer Verbraucher in derselben Steuerungslogik (folgt dem in der Recherche belegten 1KOMMA5°-Heartbeat-Präzedenzfall)

### Long-term vision

Voltaris entwickelt sich zu einer schlanken "Heim-Energie-Betriebssystem"-Plattform: Tarif, Speicher, perspektivisch Wärmepumpe und bidirektionales Laden (V2H/V2G, laut `research_market.md` ab 2026 kommerziell verfügbar) werden über eine einheitliche Steuerungs- und Anzeigeschicht orchestriert — Voltaris bleibt dabei bewusst Software- und Kurations-Unternehmen, nicht Hersteller oder Installationsbetrieb. Flexibilitäts-/VPP-Vermarktung wird, gestützt durch das Kiwigrid×Tibber-Vorbild (`research_market.md`), eher über eine offene Plattform-Partnerschaft als über eine eigene Aggregator-Lizenz erschlossen und bleibt Zusatzerlös, nicht tragende Säule. Erfolgsmaßstab ist, ob Voltaris die aktuell unbesetzte Positionierung "vertrauenswürdige Software-/Tarifmarke mit kuratierter, kontrollierter Hardware-Erweiterung" besetzen kann, bevor sie von einer der beiden Seiten geschlossen wird — durch Software-first-Wettbewerber, die denselben Schritt gehen (Tibber, Octopus, Ostrom), oder durch Hardware-first-Wettbewerber, die bereits die Tarifebene besetzen (1KOMMA5°).

## 4. Fit with Company Profile

| Strength leveraged | Gap to close |
|---|---|
| Bestehende App-/UX-/Nudging-Kompetenz — laut Recherche explizit als Voltaris-Kernstärke eingeordnet (`research_technology.md`) — direkt einsetzbar für Euro-Dashboard, Kurz-Fragebogen und Automatisierungs-UI | Keine eigene Hardware-/Installationskompetenz (`input.yaml`) — muss über kuratierte Partner geschlossen werden; Qualitäts-/Kapazitätsmanagement ist eine für Voltaris komplett neue organisatorische Fähigkeit |
| Bestehende Kundenbasis mit Vertrauensbeziehung und vorhandenen Verbrauchs-/Erzeugungsdaten — ermöglicht personalisierte Erstansprache ohne Kaltakquise-Kosten | PV-Anteil der eigenen Bestandskundenbasis ist intern nicht beziffert bekannt (jedenfalls nicht in den Research-Dateien) — die zentrale Unbekannte für die gesamte Segmentierung dieser Hypothese |
| Python-Cloud-Backend mit bestehender Day-Ahead-Marktanbindung — direkte Erweiterungsbasis für die Lade-/Entlade-Steuerungslogik | Technische Kompatibilität des bestehenden Backends mit den infrage kommenden Hersteller-APIs ist ungeklärt (`research_technology.md` nennt dies explizit als unternehmensinterne, öffentlich nicht recherchierbare Lücke) |
| Energiemarkt-/Beschaffungs-Know-how im Team — direkt einschlägig für §14a-/Netzentgelt-Optimierung (V2) und für die Bewertung von Leasing-/Finanzierungspartnern | Begrenztes Kapital (`input.yaml`) — Speicher-Kauf auf eigene Bilanz ist ausgeschlossen; ein tragfähiger Leasing-/Finanzierungspartner ist heute nicht vorhanden und muss verhandelt werden |
| Schlanke, vertrauenswürdige Software-Marke als Ausgangsbasis | Reales Risiko, durch Hardware-Logistik und Installationsservice als "schwerfällig" wahrgenommen zu werden (`input.yaml`-Constraint) — das kuratierte statt vollintegrierte Modell muss dieses Risiko aktiv und sichtbar managen, z. B. durch die Deutlichkeit, mit der Installation an Partner ausgelagert bleibt |

## 5. Key Assumptions to Validate

| Assumption | How to validate |
|---|---|
| Der PV-Anteil der bestehenden Voltaris-Kundenbasis ist groß genug, um einen tragfähigen Einstiegskeil zu bilden (die Kernsegmentierung dieser Hypothese steht und fällt mit dieser Zahl, siehe Abschnitt 1) | Interne Auswertung der Kundendatenbank (PV-Anlage ja/nein, Anlagengröße, Baujahr, EEG-Vergütungsablauf); falls nicht vorhanden, kurze Kundenumfrage an einer Stichprobe |
| "Einrichten und vergessen" plus sichtbare Euro-Ersparnis überzeugt Kunden tatsächlich zu einer monatlichen Abo-Zahlung — trotz des dokumentierten geringen Engagements und des allgemeinen Vertrauensdefizits gegenüber dynamischen Tarifen (81 % fühlen sich laut vzbv/forsa schlecht informiert, `research_problems.md`) | Zahlungsbereitschafts-Test vor Vollrollout: z. B. Landingpage mit echten Preispunkten und Warteliste, oder Concierge-Pilot mit einer kleinen Kohorte aus der Bestandskundenbasis |
| 1–2 kuratierte Partnerhersteller reichen aus, um einen relevanten Teil der Zielgruppe technisch abzudecken, ohne dass Wechselrichter-/Anlagenkompatibilität zum Blocker wird | Technischer Kompatibilitätscheck gegen eine Stichprobe realer Bestandskundenanlagen (Wechselrichtermarken, Baujahre) vor endgültiger Partnerauswahl; 10–20 Pilotinstallationen vor Skalierung |
| Das kuratierte Partner-Installationsnetzwerk hält Qualität und Kapazität auch bei wachsender Nachfrage (Gegenbeispiel: dokumentiertes Fenecon-Support-Skalierungsproblem, allgemeiner Fachkräftemangel im Elektrohandwerk, `research_technology.md`/`research_problems.md`) | Klar definierte SLAs mit Pilotpartnern; Monitoring von Reaktionszeiten und Terminverzug über die ersten 50–100 Installationen, bevor auf mehrere Bundesländer skaliert wird |
| Eine für Voltaris margenfähige Leasing-/Abo-Struktur lässt sich mit einem externen Finanzierungspartner abschließen (Bilanz-Constraint aus `input.yaml`) | Konkrete Angebote/Verhandlungen mit Leasinggebern oder Battery-as-a-Service-Partnern einholen; Vergleich gegen die recherchierten Markt-Mietpreise (69–114 €/Monat, `research_technology.md`) zur Prüfung der eigenen Marge |
