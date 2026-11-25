# bimetrics für Google Antigravity

bimetrics verbindet Buchhaltung, Belege, Rechnungen und E-Rechnungen für
Selbstständige und Unternehmen in Deutschland mit deinem KI-Assistenten. Dieses
Plugin-Paket bündelt den offiziellen bimetrics-MCP-Server sowie fertige
Buchhaltungs-Skills für Google Antigravity.

Stand: MCP-Version 2026-11-23. Was jede Version kann, steht in der
[Tool-Übersicht](https://developer.bimetrics.de/mcp/tools).

## Verbinden

Du brauchst einen bimetrics-Account und ein Unternehmen mit freigeschaltetem
MCP-Zugang. Als Teammitglied benötigst du das MCP-Recht für das Unternehmen;
der Inhaber vergibt es in den Team-Einstellungen.

Nach der Installation startet Antigravity die OAuth-2.1-Anmeldung über sein
Client ID Metadata Document (`https://antigravity.google/oauth/client-metadata.json`)
mit PKCE im Browser. Dort wählst du ausdrücklich die Unternehmen und Rechte, die
du freigeben möchtest. Schreibzugriff ist vorausgewählt; ohne das Häkchen bleibt
die Verbindung lesend. Bei mehreren verbundenen Unternehmen gibst du bei deiner
Anfrage an, für welches gearbeitet werden soll.

Du gibst dein Passwort ausschließlich in der bimetrics-Anmeldung ein. Das Plugin
braucht keinen API-Schlüssel und kein Client-Secret. Mit `offline_access` bleibt
Antigravity bis zu 30 Tage verbunden. Deine eigenen Rechte im Unternehmen bleiben
maßgeblich; du kannst die Verbindung jederzeit in bimetrics unter
**Einstellungen › KI-Assistenten** widerrufen.

## Enthaltene Skills

- `/monatsabschluss-pruefen` – prüft Belege, Buchungsfehler, unzugeordnete
  Bankumsätze und Kassenbücher vor dem DATEV-Export (strikt lesend).
- `/fehlende-belege-finden` – findet Bankumsätze ohne Beleg und gleicht sie mit
  offenen Belegen und dem Belegpostfach ab.

## Beispiele

- „Prüfe, welche Belege und Bankumsätze für den Monatsabschluss noch offen sind.“
- „Zeige mir alle überfälligen offenen Rechnungen meines Unternehmens.“
- „Erstelle für diesen Kontakt einen Rechnungsentwurf und zeige mir die Vorschau.“
- „Mach aus dem Angebot AN-2026-0012 eine Auftragsbestätigung und zeig sie mir.“
- „Zeig mir, was der DATEV-Export für Oktober festschreiben würde. Noch nicht starten.“

## Änderungen, Vorschau und Grenzen

Mit Schreibrechten werden Änderungen an Kontakten, Entwürfen, Belegen,
Zuordnungen, Mahnungen, Kassenbuch, Kostenstellen, Anlagen und Layouts direkt in
bimetrics wirksam. Vor dem Festschreiben einer Rechnung, eines Stornos, einer
Rechnungskorrektur, dem Ausstellen von Angebot/Auftragsbestätigung/Mahnung, dem
Löschen von Belegen, dem Kassenabschluss, dem DATEV-Export und dem E-Mail-Versand
zeigt der Assistent eine Vorschau und wartet auf deine Bestätigung.

Das Plugin reicht keine Steueranmeldungen ein, löst keine Überweisungen aus und
ersetzt keine Steuerberatung. Die fertige DATEV-Datei lädst du in der App unter
**Einstellungen › Exporte** herunter.

## Hilfe und Lizenz

- [MCP bei bimetrics](https://bimetrics.de/mcp)
- [Entwicklerdoku zum MCP-Server](https://developer.bimetrics.de/mcp)
- [Support](mailto:support@bimetrics.de)

Dieses Plugin-Paket steht unter der [MIT-Lizenz](LICENSE). Die Lizenz betrifft
die Dateien dieses Pakets. Sie erteilt keine Rechte am gehosteten
bimetrics-Backend und ersetzt keine Vereinbarung für den bimetrics-Dienst.
