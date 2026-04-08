1. Im Projektordner eine virtuelle Umgebung erstellen:
   python -m venv .venv

2. Aktivieren (PowerShell):
   .\.venv\Scripts\Activate.ps1

3. Pakete installieren:
   pip install -r requirements.txt

4. Server starten:
   python -m uvicorn app.main:app --reload

5. Swagger öffnen:
   http://127.0.0.1:8000/docs

# Product API (FastAPI)

Dieses Projekt ist eine einfache REST-API zur Verwaltung von Produkten, erstellt mit FastAPI.

## Umgesetzte Features

### B.1 Neues Feld `stock`
- Jedes Produkt besitzt ein zusätzliches Feld `stock` (Integer ≥ 0)
- Validierung: Negative Werte sind nicht erlaubt
- `stock` wird beim Erstellen und Aktualisieren eines Produkts berücksichtigt

### B.2 Filter nach Preis
Der GET-Endpunkt `/products/` wurde erweitert um:

- `min_price`: Filtert Produkte mit Preis ≥ min_price
- `max_price`: Filtert Produkte mit Preis ≤ max_price
- Kombination von Filtern möglich (Kategorie + Preis)


