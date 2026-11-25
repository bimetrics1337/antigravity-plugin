---
name: fehlende-belege-finden
description: >-
  Findet Bankumsätze ohne zugeordneten Beleg in bimetrics, gleicht sie mit
  offenen Belegen und dem Belegpostfach ab und schlägt konkrete Zuordnungen oder
  Rückfragen vor – ohne ungefragt etwas zu ändern.
---

# Fehlende Belege in bimetrics finden

Arbeite zunächst strikt lesend; erst nach ausdrücklicher Bestätigung des Nutzers dürfen Zuordnungen angelegt, Belege aus dem Postfach übernommen oder Rückfragen versendet werden.

1. Prüfe über `list_companies` das betroffene Unternehmen.
2. Suche mit `search_transactions` (`matchStatus: "unmatched"`, Zeitraum nach Wunsch oder letzter Monat) alle Bankumsätze ohne Beleg.
3. Prüfe parallel:
   - `search_documents` (`matchStatus: "unmatched"`) für bereits hochgeladene, noch unzugeordnete Belege
   - `search_inbox_mails` für eingegangene Belege im Belegpostfach
4. Ordne offensichtliche Kandidaten (Betrag, Datum, Gegenpartei) übersichtlich in einer Tabelle zu und kennzeichne Umsätze, zu denen wirklich ein Beleg fehlt.
5. Biete gezielt die nächsten Schritte an (Beleg zuordnen, Anhang aus Postfach übernehmen, Beleg per Upload-Link nachreichen oder Beleg beim Lieferanten anfordern – letzteres erst nach Vorschau und ausdrücklicher Bestätigung).
