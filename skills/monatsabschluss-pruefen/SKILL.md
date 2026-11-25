---
name: monatsabschluss-pruefen
description: >-
  Prüft den aktuellen Monat oder einen gewünschten Zeitraum in bimetrics vor dem
  DATEV-Export (offene Belege, Buchungsfehler, unzugeordnete Bankumsätze,
  Kassenbücher) strikt lesend ohne Änderungen vorzunehmen.
---

# Monatsabschluss in bimetrics prüfen

Nutze ausschließlich lesende bimetrics-MCP-Werkzeuge; ändere keine Daten, solange der Nutzer nicht ausdrücklich darum bittet.

1. Ermittle mit `list_companies` die freigegebenen Unternehmen. Bei mehreren Unternehmen frage kurz nach, welches geprüft werden soll (falls im Auftrag nicht genannt).
2. Lies mit `get_company_context` Kontenrahmen, Versteuerungsart (Soll/Ist) und Grunddaten.
3. Führe für den gewünschten Monat bzw. Zeitraum parallel aus:
   - `get_export_check` (offene Buchungsfehler, fehlende Belegtypen/Rechnungsdaten, Fremdwährungen ohne Euro-Betrag, offene Kassenmonate, Exportumfang)
   - `search_transactions` mit `matchStatus: "unmatched"` (Bankumsätze ohne Beleg oder Umbuchung)
   - `get_open_tasks` (offene Aufgaben und Bankfreigaben)
4. Fasse das Ergebnis strukturiert nach Dringlichkeit zusammen:
   - **Buchungsfehler & fehlende Pflichtangaben** (mit Belegnummer, Gegenpartei, Betrag und App-Link)
   - **Bankumsätze ohne Beleg** (Datum, Gegenpartei, Betrag)
   - **Offene Kassenmonate / sonstige Hinweise**
   - **Nächster Schritt:** Frage, welche Punkte der Nutzer zuerst bereinigen möchte. Starte niemals eigenständig einen DATEV-Export oder Kassenabschluss.
