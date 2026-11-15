# BOXX Studio

Browserbasierter Einsatz-Konfigurator für L-BOXX und Systainer³. Rechteckige Kästchen anordnen, Abmessungen anpassen und einzeln als STL für den 3D-Druck exportieren.

**[Konfigurator öffnen](https://flippo710.github.io/boxx-studio/)** · [Fehler oder Vorschlag melden](https://github.com/Flippo710/boxx-studio/issues)

## Funktionen

- 13 Koffermodelle: L-BOXX 102, 136 und 238; Systainer³ S 76 und S 147; M 112, M 137, M 187 und M 237; L 137 und L 187; Organizer M 89 und L 89.
- 21 Kästchen-Presets für Schrauben, Nägel, Dübel, Muttern, Unterlegscheiben und Bits in mehreren Größen.
- Kästchen per Maus verschieben oder über Maßfelder bearbeiten. Beim Verschieben einer gemeinsamen Trennwand passen sich angrenzende Fächer an.
- „Kästchen hinzufügen“ halbiert die Auswahl entlang der längeren Seite. Entfernen und Rückgängig sind ebenfalls möglich.
- Feste Modellgrenzen, Überlappungsprüfung, Mindestgrößen und optionales 5-mm-Raster.
- Höhe pro Kästchen sowie gemeinsame Wand- und Bodenstärke einstellen.
- Auswahl als einzelne STL oder alle Kästchen als ZIP mit separaten STL-Dateien herunterladen.
- Automatische lokale Speicherung im Browser. Kein Benutzerkonto und kein Backend erforderlich.

## Bedienung

1. Koffermodell auswählen. Eine bestehende Aufteilung wird proportional auf das neue Modell angepasst, sofern die Mindestgrößen eingehalten werden. Preset-Kästchen ändern dabei ebenfalls ihre Abmessungen.
2. Für einen eigenen Aufbau „Leeres Layout“ wählen oder eine Layout-Vorlage verwenden. „Leeres Layout“ ersetzt die aktuelle Aufteilung; „Zurück“ stellt sie wieder her.
3. Bei einem Preset die Teilegröße wählen und auf **＋** klicken. Es wird zunächst in freier Fläche eingesetzt. Ist keine passende Fläche frei, wird das ausgewählte Kästchen unterteilt. Restflächen unter 20 mm werden abgelehnt.
4. Kästchen auswählen und Maße bzw. Höhe bearbeiten. Die rechte oder untere Trennwand verändert auch angrenzende Kästchen. Am äußeren Rand bleibt die Begrenzung fest.
5. Über **Auswahl als STL** ein Kästchen exportieren oder mit **Alle einzeln als ZIP** sämtliche Kästchen separat herunterladen.

Die Preset-Beschriftung benennt die vorgesehenen Teile, die angezeigten Maße sind empfohlene Außenmaße des Kästchens. Wandstärke reduziert den tatsächlich verfügbaren Innenraum. Die Presets sind keine offiziellen Hersteller-Insetboxen.

## 3D-Druck

Jede exportierte STL enthält ein offenes Kästchen mit Boden und vier Wänden. Alle Größen sind in **Millimetern** zu interpretieren. Jede Einzeldatei beginnt bei X=0 und Y=0; die Einbauposition im Koffer wird nicht als leerer Druckraum mitexportiert.

Das ZIP enthält je Kästchen eine eigene, nummerierte STL-Datei. Drucke die Kästchen einzeln und setze sie anschließend entsprechend dem Layout in den Koffer ein. Sehr große individuell konfigurierte Kästchen können weiterhin größer als das Druckbett sein; ihre Maße sind vor dem Export sichtbar.

## Maße und Grenzen

Die Planungsfläche ist eine **rechteckige Annäherung nach veröffentlichten Innenmaßen**. Verrundungen, Rippen, Verschlüsse, Bodenverjüngung und andere Gehäusekonturen werden noch nicht nachgebildet. Vor einem vollständigen Druck die eigene Koffervariante und Drucktoleranzen prüfen, gegebenenfalls einen Probedruck anfertigen. Es gibt keine garantierte Passgenauigkeit.

Maßquellen:

- [L-BOXX 102](https://l-boxx.com/de/produkt/l-boxx-102), [L-BOXX 136](https://l-boxx.com/de/produkt/l-boxx-136), [L-BOXX 238](https://l-boxx.com/de/produkt/l-boxx-238)
- [TANOS Systainer Produktkatalog 2026](https://www.systainer.com/upload/document/systainer-product-catalouge.pdf), Tabellen der Innenmaße für S, M, L und Organizer

## Technik und Hosting

HTML, CSS und JavaScript ohne Framework oder Build-Abhängigkeiten. Die veröffentlichte `index.html` enthält Styles und Skripte und wird über GitHub Pages aus dem Wurzelverzeichnis des Branches `main` ausgeliefert.

Lokal kann die Datei mit einem statischen HTTP-Server geöffnet werden, etwa:

```sh
python3 -m http.server 8000
```

Anschließend `http://localhost:8000` öffnen. Die Anwendung speichert Entwürfe ausschließlich in `localStorage` des jeweiligen Browsers und Ursprungs. Schriftarten werden von Google Fonts geladen; ohne Verbindung greifen Systemschriften.

Unabhängiges Projekt, keine offizielle Anwendung von L-BOXX, TANOS oder Festool. Produkt- und Markennamen gehören den jeweiligen Rechteinhabern.
