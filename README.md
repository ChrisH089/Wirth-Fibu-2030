# Wirth-Fibu-2030
Minimalistisches, ablenkungsfreies Buchhaltungs-Dashboard für Kleinunternehmer. Fokus auf sofortige Belegerfassung mit smartem 'Flat-Record'-Export für Excel – ganz ohne Datenbank-Overhead

# 📊 Minimalist Booking Dashboard (MVP)

Ein radikal einfaches Dashboard für die tägliche Buchhaltung (EÜR), entwickelt für maximale Konzentration und sofortigen Workflow.

## 🎯 Das Konzept: "The Quiet Office"
Buchhaltung ist oft überladen und stressig. Dieses Dashboard verfolgt den **"Quiet Office"-Ansatz**:
- **Keine Ablenkung:** Nur 4 Kern-Kennzahlen und eine primäre Aktion.
- **Bento-Box Design:** Klare visuelle Trennung der Funktionsbereiche.
- **Mobile First:** Optimiert für die schnelle Erfassung von Belegen via Smartphone.

## 📈 Datenstrategie: "Flat-Record" für Excel
Dieses Projekt verzichtet bewusst auf eine komplexe SQL-Datenbank. Stattdessen werden alle Buchungen in einer **flachen JSON-Struktur** gespeichert.

### Warum Redundanz hier ein Feature ist:
Um den Export nach **Excel oder Google Sheets** so einfach wie möglich zu machen, speichert jeder Datensatz (Record) berechnete Werte redundant ab:
- **Netto/USt/Brutto:** Alle drei Werte stehen in jeder Zeile (keine Formeln in Excel nötig).
- **Zeit-Dimensionen:** Jahr, Monat und Quartal werden separat gespeichert, um sofortige **Pivot-Auswertungen** zu ermöglichen.
- **Status:** Direkte Sichtbarkeit von Export- und Zahlungsstatus.

**Beispiel eines Datensatzes:**
```json
{
  "id": "2026-X8Y2",
  "datum": "2026-01-13",
  "typ": "AUSGABE",
  "betrag_brutto": 89.00,
  "betrag_netto": 74.79,
  "ust_betrag": 14.21,
  "jahr": 2026,
  "quartal": 1,
  "ist_exportiert": false
}
