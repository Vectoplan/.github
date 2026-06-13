# VECTOPLAN

**VECTOPLAN entwickelt eine neue Art, räumliche Welten zu erstellen, zu bearbeiten und zu verstehen.**

Wir bauen einen 3D-Welteditor für Gebäude, Objekte, Geodaten und spätere Modellgenerierung – Schritt für Schritt als mehrere Python-/Flask-Microsysteme, die zusammen ein großes Programm ergeben.

VECTOPLAN ist nicht BIM-first, nicht IFC-first und nicht CAD-first.

BIM wird wichtig.
Aber wir wollen das System nicht von Anfang an von alten Arbeitsweisen, alten Dateiformaten oder alten Softwareannahmen abhängig machen.

Die Grundidee ist:

> Die Welt direkt in 3D bauen, strukturiert speichern, mit Geodaten verbinden und daraus später reichere Modelle erzeugen.

---

## Was wir bauen

VECTOPLAN verbindet mehrere Systeme zu einer Plattform:

* einen Minecraft-/Hytale-artigen 3D-Editor
* ein persistentes Chunk-/Welt-System
* eine Objekt- und Asset-Bibliothek
* Geodaten- und Layer-Systeme
* openLayer- und GeoServer-Integration
* spätere Modell-, Export- und BIM-fähige Pipelines

Das erste Ziel ist nicht ein perfektes BIM-System.

Das erste Ziel ist eine nutzbare, editierbare Welt.

---

## Kernidee

```text
Editor
→ in 3D bauen und bearbeiten

Chunks
→ die editierbare Welt speichern

Library
→ Blöcke, Objekte, Typen und Assets definieren

Geodaten
→ realen Weltkontext liefern

Core / spätere Systeme
→ strukturierte Weltdaten in 3D-Modelle, Exporte und BIM-fähige Ergebnisse überführen
```

---

## Komponenten

### `vectoplan-editor`

Der browserbasierte 3D-Editor.

Gebaut für direkte räumliche Bearbeitung mit First-Person-Steuerung, Hotbar, Targeting, Platzierung und Builder-Interaktion.

### `vectoplan-chunk`

Das Welt- und Chunk-Persistenzsystem.

Speichert editierbare Weltdaten als Chunks, Snapshots, Events und Commands.

### `vectoplan-library`

Die Objekt- und Asset-Bibliothek.

Liefert Blöcke, Objekte, Typen, Varianten, Vorschauen und später semantische Informationen für die Modellgenerierung.

### `vectoplan-openLayer`

Das Geodaten- und Kartenlayer-Frontend.

Dient zur Anzeige und Bearbeitung von räumlichen Daten, Layern und Weltkontext.

### GeoServer / PostGIS-Systeme

Das Geodaten-Backend.

Dient zur Speicherung, Veröffentlichung und Synchronisierung räumlicher Daten.

### Spätere Core- und Modell-Systeme

Spätere Systeme nutzen Chunk-Daten, Library-Daten und Geodaten, um strukturierte 3D-Modelle, Exporte und BIM-fähige Ergebnisse zu erzeugen.

---

## Warum Microsysteme?

VECTOPLAN ist zu groß, um es als eine ungeordnete Anwendung zu bauen.

Jeder Teil beginnt als kleines System.
Jeder Service soll einzeln verständlich, startbar und testbar sein.
Zusammen bilden sie ein großes Programm.

```text
Viele kleine Systeme.
Ein großes VECTOPLAN-Programm.
```

---

## Service-Struktur

Alle Python-/Flask-Services sollen dieselbe Grundstruktur verwenden:

```text
app.py
wsgi.py
config.py
extensions.py
routes/
src/
models/
bootstrap/
tests/
Dockerfile
entrypoint.sh
requirements.txt
```

Das Ziel ist Einheitlichkeit.

Jeder Entwickler soll jeden VECTOPLAN-Service öffnen und schnell verstehen, wo etwas hingehört:

```text
routes/   → HTTP API
src/      → Service-Logik
models/   → Datenbankmodelle
config.py → Konfiguration
app.py    → Flask-App-Factory
wsgi.py   → Gunicorn-Einstieg
```

---

## Aktuelle Richtung

Wir konzentrieren uns aktuell auf:

* den 3D-Editor
* die stabile Chunk-Welt
* die Anbindung der Library
* Geodaten- und Layer-Systeme
* eine einheitliche Struktur für alle Services

Der nächste große Schritt ist die Verbindung der 3D-Welt mit Geodaten.

---

## Kurzfassung

VECTOPLAN ist eine räumliche Authoring-Plattform.

Wir bauen zuerst editierbare 3D-Welten.
Wir verbinden sie mit Geodaten.
Wir erzeugen später daraus reichere technische Modelle.

BIM ist eine spätere Fähigkeit, aber nicht das Fundament, von dem wir uns abhängig machen.

**Erst bauen. Immer strukturiert speichern. Später daraus Modelle erzeugen.**
