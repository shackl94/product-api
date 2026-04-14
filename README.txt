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

##Neu umgesetzte Aufgabe: Verwaltung der Produkte und Authentifizierung

###Authentifizierung (JWT)
1. Benutzer registrieren

POST /users/

{
  "username": "testuser",
  "password": "1234"
}

2. Login

POST /token (Form Data!)

username
password

Antwort:

{
  "access_token": "...",
  "token_type": "bearer"
}

3. Token verwenden

In Swagger:

Klick auf Authorize
Token einfügen

Oder im Header:

Authorization: Bearer <token>


###Geschützte Endpunkte

Diese benötigen ein gültiges Token:

POST /products
PUT /products/{id}
DELETE /products/{id}
GET /users/me

