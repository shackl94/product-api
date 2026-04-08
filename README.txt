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
