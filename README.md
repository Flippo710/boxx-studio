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

## Griffbereiche und Abstandhalter

Die L-BOXX ist nicht quaderförmig. Eine frei zugängliche, verifizierte Herstellerzeichnung mit bemaßter Boden-Innenkontur und höhenabhängigen Griffvorsprüngen konnte für die unterstützten Varianten nicht gefunden werden. Hersteller-Innenmaße sind deshalb nicht mit einer exakten Innenkontur gleichzusetzen.

Als zusätzliche **Sicherheitszonen, nicht als exakte Gehäusegeometrie**, werden bei L-BOXX-Modellen zwei mittige Rechtecke von zunächst 20 × 100 mm an den seitlichen Rändern gesperrt. Diese Näherung stammt aus einer [dokumentierten Messung einer Schaumstoffeinlage für die L-BOXX 136](https://timbertime.de/anleitungen/schaumstoff-fuer-werkzeugeinlage-werkzeug-einlagen-selber-machen/). Dort werden ca. 420 × 320 mm für die Schaumstofffläche und ca. 20 × 100 mm für die seitlichen Aussparungen genannt. Diese Maße beziehen sich nicht zwingend auf den Kofferboden. Die genaue mittige Lage ist eine Annahme. Die Werte sind weder für die L-BOXX 102 noch für die 238 separat bestätigt. Insbesondere können die bereits verwendeten Mindest-Innenmaße die Engstellen schon berücksichtigen; zusätzliche Zonen reduzieren die Planung dann vorsichtshalber weiter.

Unter **Griff-Sicherheitszonen** lassen sich Einragtiefe und Länge ändern oder die zusätzlichen Zonen abschalten. „Kontur übernehmen“ verkleinert betroffene Kästchen auf ihr größtes verbleibendes Rechteck. Vorhandene Layouts werden beim ersten Laden dieser Version ebenfalls entsprechend angepasst. Das ist keine vollständige Rekonstruktion der realen Innenkontur; für eine genaue Passung sind Messungen am eigenen Koffer und auf der vorgesehenen Druckhöhe erforderlich.

**Abstandhalter** füllen die freien Flächen innerhalb des Planungsbereichs, ohne Kästchen oder gesperrte Zonen zu überlappen. Sie reduzieren seitliches Spiel. Sie verriegeln die Kästchen nicht gegen Anheben und gleichen keine unbekannte, höhenabhängige Gehäuseform aus. Die Vorgabe beträgt 0,2 mm Spiel zu jedem Kästchen und 0,4 mm zum äußeren Planungsrand. Dünne Restspalten unter 1,2 mm bleiben frei; an Segmentgrenzen kommt 0,1 mm hinzu. Höhe und Spiel sind einstellbar. Die tatsächliche Abstandhalterhöhe wird auf die Kästchenhöhe minus 1 mm und die Druckerhöhe begrenzt.

„Kästchen + Abstandhalter (ZIP)“ enthält je Teil eine eigene STL-Datei, eine `Montageplan.csv` mit den Einbaukoordinaten und Druckhinweise. „Nur Abstandhalter (ZIP)“ exportiert nur die Füllstücke und den Montageplan. Lange Füllstücke werden automatisch auf die Druckfläche segmentiert. Der Slicer bestimmt über die Infill-Einstellung den Materialbedarf der geschlossenen Füllstücke. Körper werden als reine Geometrie exportiert; ein Druck startet nicht automatisch.

## 3D-Drucker und Bauraumwarnung

Vordefiniert sind:

| Drucker | Nomineller Druckbereich X × Y × Z |
| --- | --- |
| [Bambu Lab A1 mini](https://store.bblcdn.eu/s8/default/87c1a9ef9f3a438a87d8f19fd8faea58/Bambu-Lab-A1-mini-tech-specs.pdf) | 180 × 180 × 180 mm |
| [Bambu Lab P1S](https://store.bblcdn.com/s5/default/78c105c0c92642a99e64b4b0b0f3ca6a.pdf) | 256 × 256 × 256 mm |
| [Original Prusa MK4S](https://www.prusa3d.com/product/original-prusa-mk4s-3d-printer/) | 250 × 210 × 220 mm |

Unter **Eigener Drucker** können Breite, Tiefe und Höhe manuell zwischen 20 und 2000 mm eingegeben werden. Ein zusätzlicher Rand von zunächst 2 mm pro Seite wird von der verfügbaren X-/Y-Fläche abgezogen. Der Vergleich prüft stehende Kästchen in 0°- und 90°-Ausrichtung, keine diagonalen oder gekippten Anordnungen. Zu große Kästchen werden farblich markiert und in einer Warnmeldung aufgelistet. Die Größe eines einzelnen Kastens wird nicht automatisch geändert oder zerlegt. Export bleibt bei bloßer Bauraumüberschreitung möglich, damit die STL extern weiterbearbeitet werden kann. Kollisionen mit den Sicherheitszonen verhindern dagegen den Export, bis das Layout angepasst ist.

Die Prüfung verwendet einen rechteckigen, nominellen Bauraum. Druckerspezifische Sperrflächen, Brims, Supports und individuelle Slicer-Einstellungen müssen zusätzlich berücksichtigt werden. Druckerwahl und eigene Maße werden mit dem Entwurf lokal gespeichert.

## Deckeleinlage, Höhen und Kleinteile beim Drehen

Die Hersteller-Innenhöhen wurden erneut geprüft: L-BOXX Baseline 102 **65 mm**, 136 **101 mm**, 238 **203 mm**. Für Systainer³ gelten die Innenhöhen aus dem TANOS-Katalog: S 76 **67 mm**, S 147 **138 mm**, M 112 **71 mm**, M 137 **96 mm**, M 187 **146 mm**, M 237 **196 mm**, L 137 **94 mm**, L 187 **144 mm**, Organizer M/L 89 jeweils **60 mm**. Modellnummern und Außenhöhen sind keine Kästchenhöhen.

**Innenhöhe ist nicht gleich Deckelkontakt-Höhe.** Die bisherige Vorgabe von 30–55 mm hohen Preset-Kästchen schließt bei höheren Koffern nicht gegen den Deckel ab. Eine Deckeleinlage schützt deshalb nur dann vor Vermischen, wenn sämtliche Kästchenränder an einer durchgehenden, geeigneten Auflagefläche anliegen. Abstandhalter gegen seitliches Rutschen ersetzen diese Auflage nicht.

Für die L-BOXX Baseline nennt der Hersteller die [Deckeleinlage LB 6000003670](https://l-boxx.com/de/produkt/deckeleinlage-lb) mit Außenmaßen 405 × 321 × 21 mm. Sortimo bietet daneben die [Deckeleinlage EPP G4 1000011324](https://www.mysortimo.de/de/BOXXen-%26-Koffer/Zubeh%C3%B6r-BOXXen-%26-Koffer/Deckeleinlagen-/Deckeleinlage-EPP-L-BOXX-G4/p/000000001000011324) für 102/136 G4 mit 327 × 438 × 28 mm an. Diese Ausführungen und ihre Außenmaße dürfen nicht verwechselt werden. Die Materialdicke ist nicht automatisch vollständig von der genannten Koffer-Innenhöhe abzuziehen: Einbaulage, Deckelvertiefung und Kompression bestimmen die wirksame Kontaktfläche.

Im TANOS-Katalog sind für Systainer³ M die EPP-Deckeleinlage 83000044 (5 mm) oder das gewölbte Polster 83570006, für L 83000045 (5 mm) oder 83570010, für S 83000911 oder 83500908 aufgeführt. Die Organizer sind ein abgestimmtes Deckel-/Einsatzboxen-System; dort ist eine zusätzliche Schaumstoffeinlage nicht pauschal erforderlich. Bei selbst gedruckten Kästchen muss die vollständige Auflage trotzdem geprüft werden.

### Kontakt-Höhe einstellen

1. Passende Einlage montieren bzw. die geeignete Auflagefläche des Organizer-Deckels ermitteln.
2. Die wirksame Höhe von der tatsächlichen **Kästchen-Aufstellfläche** bis zur Unterseite der eingebauten, geschlossenen Deckelauflage messen. Eine untergelegte Matte beeinflusst die Aufstellfläche.
3. Das Maß unter **Deckel & Kästchenhöhe** eintragen. Die Kontakt-Höhe wird je Koffermodell separat gespeichert. H63 bei 102 und H95 bei 136 sind nur Insetboxen-Referenzwerte aus dem Sortimo-System und ausdrücklich kein Nachweis für die konkrete Baseline-Variante. Für andere Modelle bleibt das Kontaktmaß zunächst leer.
4. **Alle Kästchen auf Kontakt-Höhe** setzt alle Kästchen auf die gleiche äußere Höhe. Neue Kästchen und Presets verwenden im Transportmodus dieses Maß; die ursprünglichen Preset-Höhen werden dabei nicht übernommen. Vorhandene Kästchen werden beim Ändern des Maßes nicht ungefragt angepasst.
5. Bestätigen, dass Einlage/Deckelauflage eingebaut ist und das Kontaktmaß sowie die vollständige Randauflage am eigenen Koffer geprüft wurden. Der Koffer muss sich ohne Verspannung schließen lassen. Mit einer kleinen Testmenge prüfen, ob Kleinteile beim Drehen im eigenen Fach bleiben.

Die **Kleinteile-Transportprüfung** ist standardmäßig aktiv. Fehlende Auflage, unbestätigte Kontaktmaße sowie zu niedrige oder zu hohe Kästchen erzeugen eine Warnung und verhindern den Export als transportgeprüftes Layout. Höhendifferenzen über 0,1 mm werden rechnerisch markiert; diese Rechentoleranz ist keine Material- oder Dichtheitsgarantie. Eine Änderung des Kontaktmaßes oder des Einbaustatus hebt die Prüfbestätigung auf. Beim Kofferwechsel gelten die separat gespeicherten Angaben des neuen Modells.

Für reine CAD-Experimente lässt sich die Transportprüfung ausdrücklich deaktivieren. Dann wird Geometrie ohne Bestätigung des Deckelkontakts exportiert; die Druckhinweise dokumentieren das. Die Software kann weder realen Anpressdruck noch Schaumstoffverformung, Randunterbrechungen oder das Zurückhalten beliebig kleiner Teile nachweisen. Eine passende Einlage und ein reales Kontaktmaß bleiben erforderlich.
