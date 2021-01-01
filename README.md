# Covid-19-Statistics Aachen

Python-Projekt zur Abfrage, Berechnung und Visualisierung von Kennwerten zur Corona-Pandemie aus den Fallzahlen der Städteregion Aachen und der Stadt Aachen. 

- Autor: Martin Holle
- Datum 01.01.2021
- Lizenz: MIT
- Projekt: https://github.com/MartinHolle/covid-19-statistics-aachen

Das Projekt besteht zur Zeit aus insgesamt fünf [Juypter-Notebooks](https://jupyter.org/), die sich jeweils auf einen Aspekt der Realisierung konzentrieren:

1. Abfrage der Daten von der [Website](https://www.staedteregion-aachen.de/de/navigation/aemter/oeffentlichkeitsarbeit-s-13/aktuelles/pressemitteilungen/aktuelle-pressemitteilungen/coronavirus/) der Städteregion Aachen mit den Presseveröffentlichungen zur Lage der Corona-Pandemie in der Städteregion und der Stadt Aachen
2. Import neuer Daten
3. Aufbereitung der Rohdaten und Berechnung verschiedener Kennzahlen
4. Visualisierung der Kennzahlen
5. Upload in ein Zielverzeichnis auf einem Web-Server per FTP
   
## Datenabfrage

Jupyter-Notebook: `c19stats-ac-abfrage.ipynb`

Im ersten Schritt werden die aktuellen Pressemitteilungen der Städteregion Aachen zur Corona-Pandemie von der [Website](https://www.staedteregion-aachen.de/de/navigation/aemter/oeffentlichkeitsarbeit-s-13/aktuelles/pressemitteilungen/aktuelle-pressemitteilungen/coronavirus/) abgerufen und anschließend analysiert. Die Kennzahlen (Gesamtanzahl der Infektionen, Anzahl wieder Genesener, Summe der Todesfälle, aktuelle Anzahl akuter Infektionen) werden aus dem eingelesenen Text extrahiert und in einer Excel-Datei für die Weiterverabeitung im nächsten Schritt zwischengespeichert. Die Excel-Datei `c19stats-rohdaten.xlsx` enthält die gesamte Historie der bisher veröffentlichten und von der Website eingelesenen Daten. 

_Hinweis: Dieses Notebook funktioniert aufgrund von Änderungen an Format und Formulierungen der Meldungen z.Zt. nicht._

## Datenimport

Jupyter-Notebook: `c19stats-ac-import.ipynb`

Import neuer Daten (als Ersatz für das Web-Scraping) aus dem Excel-Sheet `c19stats-ac-import.xlsx`.
Zusammenführung mit den existierenden Daten und Speichern des Resultats in der Excel-Datei `c19stats-rohdaten.xlsx` für die Datenübergabe an den nächsten Schritt, in dem die Daten aufbereitet werden.

## Aufbereitung der Rohdaten und Berechnung von Kennzahlen

Jupyter-Notebook: `c19stats-ac-aufbereitung.ipynb`

Im zweiten Schritt werden die Rohdaten aufbereitet und die Kennzahlen berechnet. Das Ergbnis dieses Schritts wird in einer zweiten Excel-Datei `c19stats-kennzahlen.xlsx` zwischengespeichert.

_Hinweise_:

_Seit dem 8.10.2020 verwende ich für die Berechnung der 7-Tage-Inzidenz die Einwohnerzahlen zum Stichtag 31.12.2019 (Quelle: [Landesbetrieb IT.NRW - Statistik und IT-Dienstleistungen](https://www.it.nrw/statistik/eckdaten/bevoelkerung-nach-gemeinden-93051)), wie dies auch die Behörden tun. Bis dahin verwendete ich einen älteren Stand aus Wikipedia. Die Bevölkerung hat ggü. diesem Stand zugenommen, sodass die Kennzahlen für die 7-Tage-Inzidenz geringfügig niedriger ausfallen._

_Seit dem 1.1.2021 interpoliere ich fehlende Werte in den Summenspalten der Kennzahlen _linear_, statt sie wie zuvor per `bfill` oder `ffill` einfach fortzuschreiben. Das vorherige Verfahren führte zu inakzeptablen Sprüngen insbesondere des Inzidenzverlaufs, die lineare Interpolation führte zu realistischen Ergebnissen für die Kennzahlen._ 

## Visualisierung

Jupyter-Notebook: `c19stats-ac-visualisierung.ipynb`

Im dritten Schritt werden die ermittelten Kennzahlen mit mehreren Diagrammen visualisiert:

**1. Diagramm: Covid-19-Fälle in der Städteregion Aachen**<br/>
Für die Städteregion Aachen werden die aktiven Fälle und die Summe der Genesenen und Todesfälle als gestapelter Verlauf dargestellt.

**2. Diagramm: Änderung aktiver Fälle**<br/>
Für die Städteregion Aachen wird die Änderung der aktiven Fälle (absolut und prozentual, pro Tag und gemittelt) als Liniendiagram visualisiert.

**3. Diagramm: Neue Fälle / Genesene / Todesfälle**<br/>
Für die Städteregion Aachen werden die gemittelten Werte neuer Fälle, neuer Genesener und neuer Todesfälle in einem Liniendiagramm dargestellt.

**4. Diagramm: Neuinfektionen in den letzten 7 Tagen pro 100.000 Einwohner**<br/>
Für die Städteregion und die Stadt Aachen wird die Summe der Neuinfektionen in den letzten 7 Tagen bezogen auf 100.000 Einwohner in einem Liniendiagramm dargestellt.

## Upload

Jupyter-Notebook: `c19stats-ac-upload.ipynb`

Im letzten Schritt werden die im vorherigen Schritt produzierten Grafik-Dateien und `yml`-Dateien mit den Meta-Daten per FTP in das Zielverzeichnis auf dem Web-Server hochgeladen.

## Daten

Das Verzeichnis `data` enthält die folgenden _Excel_-Dateien mit den Rohdaten und daraus berechneten Kennwerten:

- `c19stats-ac-import.xlsx`: Import neuer Daten
- `c19stats-rohdaten.xlsx`: Rohdaten
- `c19stats-kennzahlen.xlsx`: Aufbereitete Kennzahlen

## Logging

Das Logging erfolgt in die Datei `c19stats.log` im Verteichnis `logs`.

## Konfiguration

Die Konfiguration wird aus der Datei `config.ini` im Hauptverzeichnis gelesen.
