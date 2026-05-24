---
disable-model-invocation: true
---

# Kurs: MCP — Externe Dienste in Skills einbinden

Willkommen. Du lernst heute was MCP ist, wann du es einsetzt, und wie du einen Skill baust der echte externe Dienste aufruft. Der Kurs hat 8 Schritte. Du navigierst mit "weiter" (nächster Schritt) oder "Schritt X" (direkt springen).

---

## Vorab: Ein ehrlicher Hinweis

**a) Nicht jeder wird alles ausprobieren können.**
In Corporate-Umgebungen sind externe App-Verbindungen oft durch IT oder Datenschutz eingeschränkt. Das Ziel dieses Kurses ist nicht, dass du heute zwingend eine funktionierende Verbindung hast. Das Ziel ist, dass du verstehst *wie* das funktioniert und *was* möglich ist.

**b) MCP-Konfiguration kann nerven.**
Besonders lokal installierte Server können frickelig sein. Du musst das nicht heute lösen. Im betrieblichen Umfeld wird Konfiguration oft zentral erledigt. Bring Fragen in den nächsten Call.

**c) Das Wichtigste ist das Prinzip.**
Wenn etwas technisch nicht klappt: lies den Schritt trotzdem durch. Das Muster bleibt dasselbe egal welcher Dienst.

---

## Schritt 1: Was ist MCP?

MCP steht für **Model Context Protocol** — ein offenes Protokoll das festlegt, wie Claude mit externen Diensten kommuniziert.

Ohne MCP kann Claude nur lesen und schreiben was du ihm direkt gibst. Mit MCP kann Claude aktiv in andere Systeme schauen: Slack-Nachrichten lesen, Kalendereinträge abrufen, E-Mails suchen — ohne dass du etwas kopieren oder einfügen musst.

**Wie funktioniert es?**

Ein MCP-Server stellt Claude eine Liste von **Tools** zur Verfügung. Claude weiß welche Tools verfügbar sind und kann sie aufrufen. Die Tool-Namen folgen einem festen Muster:

```
mcp__ServerName__tool_name
```

Zum Beispiel: `mcp__claude_ai_Slack__slack_read_channel`

Du musst diese Namen kennen wenn du einen Skill schreibst der MCP benutzt. Frag Claude Code jederzeit: *"Welche MCP-Tools habe ich gerade?"*

Sag "weiter" für Schritt 2.

---

## Schritt 2: Wann MCP — wann direkter API-Zugriff?

Es gibt zwei grundsätzlich verschiedene Wege um externe Dienste einzubinden — und die Wahl sagt etwas darüber aus wie viel Kontrolle du willst.

**Weg 1: MCP**
Einmal konfigurieren, fertig. Claude Code weiß danach selbstständig welche Daten es wo und wie findet. Du beschreibst was du willst, Claude kümmert sich um den Rest. Wenig Aufwand, wenig Reibung — aber auch weniger Einblick in was genau passiert. Das ist der "mehr agentic"-Weg.

**Weg 2: Direkter API-Zugriff mit generiertem Code**
Claude Code schreibt dir Python- oder JavaScript-Code der direkt mit der API des Dienstes spricht. Keine Angst — den Code schreibt Claude Code für dich. Dieser Weg ist präziser: du siehst genau was abgefragt wird, Fehler sind leichter zu finden, und es werden oft weniger Tokens verbraucht. Dafür ist die Einrichtung aufwändiger und kann frickelig werden. Das ist eher "wie früher" — mehr Kontrolle, mehr Mühe.

| | MCP | API + generierter Code |
|---|---|---|
| **Aufwand** | Einmalig konfigurieren | Code generieren lassen, einrichten |
| **Kontrolle** | Claude entscheidet | Du siehst jeden Schritt |
| **Fehlersuche** | Schwieriger | Einfacher |
| **Token-Verbrauch** | Höher | Oft niedriger |
| **Charakter** | Agentic | Klassisch |

Für diesen Kurs nehmen wir MCP — weil es der schnellere Einstieg ist und das Prinzip am klarsten zeigt.

Sag "weiter" für Schritt 3.

---

## Schritt 3: Konnektoren — der einfache Weg

Claude Desktop hat eine eingebaute Bibliothek von **Konnektoren** — fertig konfigurierte Verbindungen zu gängigen Diensten (Slack, Gmail, Google Calendar, …). Diese werden von Anthropic gepflegt und brauchen keine lokale Konfiguration.

**Wie aktivieren:**

1. Claude Desktop öffnen → **Einstellungen** → **Connections**
2. Dienst suchen und per Browser-Login autorisieren

**Wichtig — zwei verschiedene Status:**

| Anzeige | Bedeutung |
|---------|-----------|
| **"Konfigurieren"** | Einmalig autorisieren → danach auch in Claude Code CLI verfügbar |
| **"Verbunden"** | Nur im Desktop verwendbar — in der CLI **nicht** verfügbar |

Wenn ein Konnektor nur "Verbunden" zeigt, musst du ihn separat für die CLI einrichten (→ Schritt 8).

**Prüfen ob es in der CLI geklappt hat:**
> *"Welche MCP-Tools habe ich gerade?"*

Wenn du `mcp__claude_ai_Slack__*` oder ähnliches siehst — es funktioniert.

Diese Konnektoren erkennst du am Präfix `claude_ai` im Tool-Namen.

Sag "weiter" für Schritt 4.

---

## Schritt 4: Skill mit Account-Integration bauen

Das Muster ist in allen drei Fällen gleich:
1. Prüfen ob die Integration verbunden ist
2. Skill per Prompt von Claude Code erstellen lassen
3. Testen

**Die Eleganz von MCP:** Du musst die technischen Tool-Namen nicht kennen. Claude sieht welche Verbindungen aktiv sind und wählt selbst die richtigen Tools. Du beschreibst einfach was du willst — den Rest erledigt Claude Code.

Wähle einen der drei Dienste und folge dem jeweiligen Schritt:
- **Slack** → Schritt 5
- **Gmail** → Schritt 6
- **Google Calendar** → Schritt 7

Du kannst natürlich auch alle drei machen.

Sag "weiter" für Schritt 5 (Slack).

---

## Schritt 5: Slack Skill

**Was der Skill tut:** Die letzten 5 Nachrichten eines Kanals lesen — Absender, Uhrzeit, ein Satz Zusammenfassung.

**Verbindung prüfen:** Siehst du `mcp__claude_ai_Slack__slack_read_channel` in deinen verfügbaren Tools? Falls nicht: Schritt 3 wiederholen.

**Skill bauen lassen — Prompt für Claude Code:**

> Erstelle einen Skill `/slack-digest` der die letzten 5 Nachrichten aus einem Slack-Kanal liest. Der Kanalname wird beim Aufruf angegeben. Output: nummerierte Liste mit Absender, Uhrzeit und einem Satz pro Nachricht. Antwort direkt im Chat.

**Testen:**
> `/slack-digest — Kanal: #allgemein`

Sag "weiter" für Schritt 6 (Gmail).

---

## Schritt 6: Gmail Skill

**Was der Skill tut:** Die letzten 5 E-Mails im Posteingang — ausschließlich Betreffzeilen, Absender, Datum.

**Verbindung prüfen:** Siehst du `mcp__claude_ai_Gmail__gmail_search_messages`?

**Skill bauen lassen — Prompt für Claude Code:**

> Erstelle einen Skill `/gmail-digest` der die letzten 5 E-Mails im Posteingang abruft. Output: nummerierte Liste mit Betreffzeile, Absender und Datum. Antwort direkt im Chat.

**Testen:**
> `/gmail-digest`

Sag "weiter" für Schritt 7 (Google Calendar).

---

## Schritt 7: Google Calendar Skill

**Was der Skill tut:** Die nächsten 5 Termine — Titel, Datum, Uhrzeit, Dauer.

**Verbindung prüfen:** Siehst du `mcp__claude_ai_Google_Calendar__gcal_list_events`?

**Skill bauen lassen — Prompt für Claude Code:**

> Erstelle einen Skill `/calendar-digest` der die nächsten 5 Kalendereinträge abruft. Output: nummerierte Liste mit Titel, Datum, Uhrzeit und Dauer. Falls Teilnehmer vorhanden sind, zeige die Anzahl. Antwort direkt im Chat.

**Testen:**
> `/calendar-digest`

Sag "weiter" für Schritt 8.

---

## Schritt 8: MCP-Server direkt konfigurieren

Wenn ein Konnektor in der Desktop-App nur "Verbunden" zeigt oder ein Dienst gar nicht in der Bibliothek ist, kannst du einen MCP-Server direkt in der CLI einrichten — unabhängig vom Desktop.

**Der direkte Weg: `/mcp add`**

```
/mcp add
```

Claude Code führt dich durch die Konfiguration: Transporttyp, Server-URL oder Paketname, Authentifizierung.

Alternativ über die Kommandozeile — Beispiel für einen HTTP-Server:

```
claude mcp add --transport http notion https://mcp.notion.com/mcp
```

Oder mit API-Key als Umgebungsvariable:

```
claude mcp add --transport stdio --env AIRTABLE_API_KEY=DEIN_KEY airtable -- npx -y airtable-mcp-server
```

**Alternative: `/plugin install`**
Für Dienste bei denen ein fertiges Plugin-Bundle existiert (MCP-Server + Skills + Hooks zusammen):

```
/plugin install github
```

Plugins kommen aus einem Marketplace und sind vorgebaut — weniger Konfiguration, aber weniger Kontrolle.

**Der Unterschied zum Konnektor:**
- Lokal konfiguriert → nur auf diesem Rechner verfügbar
- Kein Anthropic-Account nötig
- Mehr Konfigurationsaufwand
- Volle Kontrolle über Version und Verhalten

**Weiterführend:** [docs.anthropic.com/de/claude-code/mcp](https://docs.anthropic.com/de/claude-code/mcp)

---

**Die größere Welt — eine Auswahl:**

| Kategorie | Dienst | Was möglich wird |
|---|---|---|
| Kommunikation | Slack | Kanäle lesen, Nachrichten senden |
| Kommunikation | Gmail | E-Mails lesen, suchen, Entwürfe erstellen |
| Planung | Google Calendar | Termine lesen, erstellen, freie Zeiten finden |
| Planung | Google Workspace | Docs, Sheets, Drive |
| Meetings | Granola | Meeting-Transkripte und Notizen abrufen |
| Projektmanagement | Airtable | Datenbanken lesen und schreiben |
| Projektmanagement | Jira | Issues, Sprints, Backlogs |
| Design | Figma | Designs lesen, Kommentare abrufen |
| Kollaboration | Miro | Boards lesen und schreiben |
| Entwicklung | GitHub | Repos, Issues, Pull Requests |
| Entwicklung | Linear | Issue-Tracking |
| Web | Brave Search | Websuche direkt aus Claude |
| Lokal | Filesystem | Dateien auf deinem Rechner lesen/schreiben |

Das ist kein vollständiges Bild — die Community wächst schnell. Jeder dieser Dienste folgt demselben Muster das du heute gelernt hast.

Sag "weiter" für Schritt 9 (Reflexion).

---

## Schritt 9: Reflexion

Du hast heute:
- Verstanden was MCP ist und wie Tool-Namen aufgebaut sind
- Den Unterschied zwischen Account-Integrationen und lokalen Servern gelernt
- Mindestens einen Skill gebaut der einen externen Dienst aufruft
- Die Breite des MCP-Ökosystems gesehen

**Drei Fragen für deinen Kontext:**

1. **Welchen Dienst** würdest du als erstes dauerhaft einbinden — und was würdest du damit täglich tun?

2. **Lesen ist risikoarm. Schreiben ist eine andere Frage.** Was wäre dein Komfortlevel mit einem Skill der auch sendet — `/slack-send`, `/gmail-reply`, `/calendar-create`?

3. **Im betrieblichen Umfeld** wird Konfiguration oft zentral erledigt. Was würdest du deiner IT vorschlagen wenn du MCP-Zugriff für dein Team möchtest?

Offene Fragen und Setup-Probleme: bring sie in den nächsten Call.

---

**Kurs MCP abgeschlossen.**

---

## Zusatzmaterial

- `MCPKonnektorenDoc.md` — Die vier Stufen von einfach zu komplex als Referenz zum Nachschlagen
- `ClaudeRemoteDoc.md` — Remote Interfaces: Channels (Telegram/Discord/iMessage), Remote Control, Computer Use
- `SkillsAgentsDoc.md` — Taxonomie Skills vs. Agents: wann welche Ebene?
