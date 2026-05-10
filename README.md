# Zeiterfassung

Lokales Zeiterfassungstool zur automatischen Erfassung und Auswertung von Arbeitszeiten nach Projekt und Aufgabe.

## Description

Diese Anwendung wurde entwickelt, um Arbeitszeiten lokal auf einem Windows-Rechner zu erfassen. Der Tracker erkennt aktive Fenster und Anwendungen, ordnet Zeitbloecke anhand von Keywords Projekten zu und fragt bei unsicherer Zuordnung per Popup nach. Im Browser-Dashboard koennen Projekte, Aufgaben, Zeitbloecke und Auswertungen eingesehen werden. Die Anwendung eignet sich besonders fuer projektbasierte Arbeit, z. B. Webdesign, Softwareentwicklung oder Kundenprojekte.

## Getting Started

### Dependencies

Getestete Umgebung:

- Windows 10 / Windows 11
- moderner Browser, z. B. Microsoft Edge, Chrome oder Firefox

Fuer die Ausfuehrung aus dem Quellcode werden benoetigt:

- Python 3
- pip
- Abhaengigkeiten aus `requirements.txt`
- optional: virtuelle Python-Umgebung `.venv`

Die benoetigten Python-Pakete sind:

```text
fastapi
uvicorn
sqlalchemy
psutil
pywin32
```

Zum Bauen einer portablen Windows-Version wird zusaetzlich PyInstaller benoetigt.

### Installing

Repository herunterladen oder klonen:

```bat
git clone <REPOSITORY-URL>
cd ba-zeiterfassung
```

Virtuelle Umgebung erstellen:

```bat
python -m venv .venv
```

Virtuelle Umgebung aktivieren:

```bat
.venv\Scripts\activate
```

Abhaengigkeiten installieren:

```bat
python -m pip install -r requirements.txt
```

### Executing program

Dashboard aus dem Quellcode starten:

```bat
python run_dashboard.py
```

Danach:

1. Browser oeffnen.
2. `http://127.0.0.1:8000/dashboard` aufrufen.
3. Im Dashboard auf `Tracking einschalten` klicken.
4. Bei Bedarf im Popup Projekt und Aufgabe zuordnen.

Das Dashboard laeuft lokal unter:

```text
http://127.0.0.1:8000/dashboard
```

Optionale portable Windows-Version bauen:

```bat
build_portable.bat
```

Das Ergebnis liegt danach unter:

```text
dist_portable\Zeiterfassung
```

## Help

### Tracking-API nicht erreichbar

Diese Meldung erscheint, wenn das Dashboard im Browser geoeffnet ist, aber das Backend nicht erreichbar ist.

Moegliche Loesungen:

1. Browserfenster schliessen.
2. Im Task-Manager alte Prozesse wie `Dashboard.exe`, `Tracker.exe` oder passende `python.exe` beenden.
3. Danach `python run_dashboard.py` erneut starten.

### Tracking einschalten macht nichts

Bei Ausfuehrung aus dem Quellcode pruefen, ob alle Abhaengigkeiten installiert sind:

```bat
python -m pip install -r requirements.txt
```

Bei der portablen Version pruefen, ob diese Datei vorhanden ist:

```text
Tracker\Tracker.exe
```

Wenn diese Datei fehlt, wurde der portable Ordner unvollstaendig erstellt oder kopiert.

## Authors

Jelena Koc

## Version History

- 0.2
  - portable Windows-Version
  - Dashboard mit Auswertungen und CSV-Export
  - manuelle Projekt- und Aufgaben-Zuordnung per Popup
  - Verbesserungen beim Tracking-Start und bei der Projektverwaltung

- 0.1
  - Initial Release
  - Grundfunktion fuer Zeiterfassung, Projektzuordnung und Dashboard

## License

Dieses Projekt wurde im Rahmen einer Bachelorarbeit erstellt. Eine separate Lizenzdatei ist aktuell nicht enthalten.

## Acknowledgments

- FastAPI
- SQLAlchemy
- PyInstaller
- Chart.js
