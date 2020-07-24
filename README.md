# Covid-19-Statistics Aachen

Python-Projekt zur Berechnung von Kennwerten zur Corona-Pandemie aus den Fallzahlen der Städteregion Aachen und der Stadt Aachen. 

Im ersten Schritt werden dazu die aktuellen Pressemitteilungen der Städteregion Aachen zur Corona-Pandemie von der Website

https://www.staedteregion-aachen.de/de/navigation/aemter/oeffentlichkeitsarbeit-s-13/aktuelles/pressemitteilungen/aktuelle-pressemitteilungen/

abgerufen und anschließend analysiert; die Kennzahlen werden aus dem eingelesenen Text extrahiert und in einer Excel-Datei  für die Weiterverabeitung im nächsten Schritt zwischengespeichert.

Im zweiten Schritt werden die Rohdaten aufbereitet und die Kennzahlen berechnet. Das Ergbnis dieses Schritts wird in einer zweiten Excel-Datei zwischengespeichert.

Im letzten Schritt werden die Kennzahlen in insgesamt 3 Diagrammen visualisiert.

- Autor: Martin Holle
- Datum 24.07.2020
- Lizenz: MIT

## TODO

### Allgemein

- Zentrale Konfiguration hinzufügen

### Datenabfrage

- Erweiterung um Auswertung des Meldungsarchivs
- Formatierung des Loggings finalisieren

### Visualisierung

- Senkrechte Grid-Linien
- Legenden platzieren
- Farben anpassen
- Dicke der Linien setzen
- Maße optimieren: Statt 15:10 vielleicht eher 16:10 oder sogar mehr? Ausprobieren!
- Ränder optimieren (aktuell im gespeicherten jpg zu breit)
- Meta-Daten für Grafiken als yaml-Datei erzeugen

