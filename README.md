# Covid-19-Statistics Aachen

Python-Projekt mit zur Abfrage, Berechnung und Visualisierung von Kennwerten zur Corona-Pandemie aus den Fallzahlen der Städteregion Aachen und der Stadt Aachen. 

- Autor: Martin Holle
- Datum 08.08.2020
- Lizenz: MIT

Das Projekt besteht zur Zeit aus insgesamt drei [Juypter-Notebooks](https://jupyter.org/), die sich jeweils auf einen Aspekt der Realisierung konzentrieren:

1. Abfrage der Daten von der [Website](https://www.staedteregion-aachen.de/de/navigation/aemter/oeffentlichkeitsarbeit-s-13/aktuelles/pressemitteilungen/aktuelle-pressemitteilungen/coronavirus/) der Städteregion Aachen mit den Pressenveröffentlichungen zur Lage der Corona-Pandemie in der Städteregion und der Stadt Aachen
2. Aufbereitung der Rohdaten und Berechnung verschiedener Kennzahlen
3. Visualisierung der Kennzahlen
   
## Datenabfrage

Jupyter-Notebook: `c19stats-ac-abfrage.ipynb`

Im ersten Schritt werden die aktuellen Pressemitteilungen der Städteregion Aachen zur Corona-Pandemie von der [Website](https://www.staedteregion-aachen.de/de/navigation/aemter/oeffentlichkeitsarbeit-s-13/aktuelles/pressemitteilungen/aktuelle-pressemitteilungen/coronavirus/) abgerufen und anschließend analysiert; die Kennzahlen werden aus dem eingelesenen Text extrahiert und in einer Excel-Datei  für die Weiterverabeitung im nächsten Schritt zwischengespeichert.

## Aufbereitung der Rohdaten und Berechnung von Kennzahlne

Jupyter-Notebook: `c19stats-ac-aufbereitung.ipynb`

Im zweiten Schritt werden die Rohdaten aufbereitet und die Kennzahlen berechnet. Das Ergbnis dieses Schritts wird in einer zweiten Excel-Datei zwischengespeichert.

## Visualisierung

Jupyter-Notebook: `c19stats-ac-visualisierung.ipynb`

Im letzten Schritt werden die ermittelten Kennzahlen mit mehreren Diagrammen visualisiert.

**1. Diagramm: Covid-19-Fälle in der Städteregion Aachen**<br/>
Für die Städteregion Aachen werden die aktiven Fälle und die Summe der Genesenen und Todesfälle dargestellt.

**2. Diagramm: Änderung aktiver Fälle**<br/>
Für die Städteregion Aachen wird die Änderung der aktiven Fälle (absolut und prozentual, pro Tag und gemittelt) visualisiert.

**3. Diagramm: Neue Fälle / Genesene / Todesfälle**<br/>
Für die Städteregion Aachen werden die gemittelten Werte neuer Fälle, neuer Genesener und neuer Todesfälle dargestellt.

**4. Diagramm: Neuinfektionen in den letzten 7 Tagen pro 100.000 Einwohner**<br/>
Für die Städteregion und die Stadt Aachen wird die Summe der Neuinfektionen in den letzten 7 Tagen bezogen auf 100.000 Einwohner dargestellt.

## Daten

Das Verzeichnis `data` enthält die beiden _Excel_-Dateien mit den Rohdaten und daraus berechneten Kennwerten:

- `c19stats-rohdaten.xlsx`: Rohdaten
- `c19stats-kennzahlen.xlsx`: Aufbereitete Kennzahlen


