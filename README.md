# bimetrics für Google Antigravity

bimetrics ist die Agent-First-Buchhaltungssoftware für Selbstständige und Unternehmen in Deutschland: Web-App, REST-API und der offizielle Remote-MCP-Server (`https://app.bimetrics.de/mcp`) arbeiten auf demselben GoBD-Buchhaltungskern. Dieses Plugin-Paket bündelt den offiziellen bimetrics-MCP-Server sowie fertige Buchhaltungs-Skills für Google Antigravity.

**Stand:** MCP-Version `2026-11-23` (**209–216 produktive MCP-Werkzeuge** plus **4 eingebaute Server-Prompts**). Die vollständige Übersicht steht in der [Tool-Übersicht](https://developer.bimetrics.de/mcp/tools) und im interaktiven [App-zu-MCP-Paritäts-Explorer](https://bimetrics.de/mcp#paritaets-matrix).

## Warum bimetrics MCP? (App-Parität & GoBD-Beweis)

Im Gegensatz zu schmalen Rechnungs-Konnektoren deckt bimetrics über denselben Domain-Kern alle neun Buchhaltungsbereiche ab:

- **Volle Buchhaltungstiefe:** Belege & Belegpostfach, Bankumsätze & Zahlungsabgleich (inkl. Teil-/Sammelzahlung, Skonto, Fremdwährungs-Kursdifferenz, CSV/CAMT/MT940), Angebote, Auftragsbestätigungen & E-Rechnungen (ZUGFeRD/XRechnung), Mahnwesen & Offene Posten (OPOS), Anlagen & Abschreibungen (AfA), Kassenbuch & Z-Bons, Kostenstellen (`KOST1`), Automatisierungen, Summen- und Saldenliste (SuSa) sowie DATEV-Export-Vorbereitung.
- **Serverseitige System-Vorschau:** Vor dem Festschreiben einer Rechnung, eines Stornos oder einer Rechnungskorrektur, dem Ausstellen von Angebot/AB/Mahnung, dem E-Mail-Versand, dem Löschen von Belegen, dem Kassenmonatsabschluss und dem Start des DATEV-Exports erzwingt der Server eine aktuelle Vorschau und deine ausdrückliche Bestätigung.
- **OAuth 2.1 + PKCE (CIMD) pro Unternehmen:** Kein statischer API-Schlüssel, bis zu 30 Tage gültig, mehrere Firmen in einem Zugang, jederzeit widerrufbar.
- **Öffentliche GoBD-Prüfspur:** Jede MCP-Aktion wird mit Quelle, Verbindung und Person protokolliert und ist in der öffentlichen [Verfahrensbeschreibung (Fassung 13)](https://bimetrics.de/rechtliches/verfahrensbeschreibung) dokumentiert.
- **Ohne Funktions-Paywall:** In jedem bezahlten Tarif ab 9 € netto/Monat enthalten und in der 7-tägigen Testphase mit fairem Tageslimit nutzbar.

## Verbinden

Du brauchst einen bimetrics-Account und ein Unternehmen mit freigeschaltetem MCP-Zugang. Als Teammitglied benötigst du das MCP-Recht für das Unternehmen; der Inhaber vergibt es in den Team-Einstellungen.

Nach der Installation startet Antigravity die OAuth-2.1-Anmeldung über sein Client ID Metadata Document (`https://antigravity.google/oauth/client-metadata.json`) mit PKCE im Browser. Dort wählst du ausdrücklich die Unternehmen und Rechte, die du freigeben möchtest. Schreibzugriff ist vorausgewählt; ohne das Häkchen bleibt die Verbindung lesend. Bei mehreren verbundenen Unternehmen gibst du bei deiner Anfrage an, für welches gearbeitet werden soll.

Du gibst dein Passwort ausschließlich in der bimetrics-Anmeldung ein. Das Plugin braucht keinen API-Schlüssel und kein Client-Secret. Mit `offline_access` bleibt Antigravity bis zu 30 Tage verbunden. Deine eigenen Rechte im Unternehmen bleiben maßgeblich; du kannst die Verbindung jederzeit in bimetrics unter **Einstellungen › KI-Assistenten** widerrufen.

## Enthaltene Skills

- `/monatsabschluss-pruefen`: prüft Belege, Buchungsfehler, unzugeordnete Bankumsätze und Kassenbücher vor dem DATEV-Export (strikt lesend).
- `/fehlende-belege-finden`: findet Bankumsätze ohne Beleg und gleicht sie mit offenen Belegen und dem Belegpostfach ab.

## Beispiele

- „Prüfe, welche Belege und Bankumsätze für den Monatsabschluss noch offen sind.“
- „Zeige mir alle überfälligen offenen Rechnungen meines Unternehmens.“
- „Erstelle für diesen Kontakt einen Rechnungsentwurf und zeige mir die Vorschau.“
- „Mach aus dem Angebot AN-2026-0012 eine Auftragsbestätigung und zeig sie mir.“
- „Zeig mir, was der DATEV-Export für Oktober festschreiben würde. Noch nicht starten.“

## Änderungen, Vorschau und Grenzen

Mit Schreibrechten werden Änderungen an Kontakten, Entwürfen, Belegen, Zuordnungen, Mahnungen, Kassenbuch, Kostenstellen, Anlagen und Layouts direkt in bimetrics wirksam. Vor dem Festschreiben einer Rechnung, eines Stornos, einer Rechnungskorrektur, dem Ausstellen von Angebot/Auftragsbestätigung/Mahnung, dem Löschen von Belegen, dem Kassenabschluss, dem DATEV-Export und dem E-Mail-Versand zeigt der Assistent eine Vorschau und wartet auf deine Bestätigung.

Das Plugin reicht keine Steueranmeldungen (ELSTER) ein, löst keine Überweisungen aus und ersetzt keine Steuerberatung. Die fertige DATEV-Datei lädst du in der App unter **Einstellungen › Exporte** herunter.

## Hilfe, Nachweise und Lizenz

- [MCP & App-Paritäts-Explorer](https://bimetrics.de/mcp#paritaets-matrix)
- [Google Antigravity mit bimetrics verbinden](https://bimetrics.de/ratgeber/google-antigravity-mit-bimetrics-verbinden)
- [Leitwerk: Agent-First-Buchhaltung](https://bimetrics.de/ratgeber/agent-first-buchhaltung)
- [DATEV & MCP für Steuerkanzleien](https://bimetrics.de/datev-mcp)
- [Öffentliche GoBD-Verfahrensbeschreibung (Fassung 13)](https://bimetrics.de/rechtliches/verfahrensbeschreibung)
- [Maschinenlesbares Faktenblatt (llms-full.txt)](https://bimetrics.de/llms-full.txt)
- [Entwicklerdoku zum MCP-Server](https://developer.bimetrics.de/mcp)
- [Support](mailto:support@bimetrics.de)

---

### Overview (EN)

Official **bimetrics** plugin for **Google Antigravity** (`https://app.bimetrics.de/mcp`, MCP version `2026-11-23`), bundling the hosted Remote MCP Server and read-only accounting skills (`/monatsabschluss-pruefen`, `/fehlende-belege-finden`). Built on the same GoBD accounting domain core as the bimetrics Web App and REST API (**209–216 live tools + 4 built-in server prompts** across 9 domains: receipts, bank matching with cash discount & FX differences, ZUGFeRD/XRechnung e-invoices, dunning/OPOS, assets/AfA, cash book/Z-Bon, cost centers `KOST1`, trial balance, and DATEV export). Secured via OAuth 2.1 + PKCE (CIMD) and server-enforced preview gates (no bank transfers, no ELSTER filing). Included in every paid plan from 9 €/month net (plus 7-day free trial).

Dieses Plugin-Paket steht unter der [MIT-Lizenz](LICENSE). Die Lizenz betrifft die Dateien dieses Pakets. Sie erteilt keine Rechte am gehosteten bimetrics-Backend und ersetzt keine Vereinbarung für den bimetrics-Dienst.
