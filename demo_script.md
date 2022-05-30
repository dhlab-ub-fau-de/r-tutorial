# Demo-Runde in R und RStudio

## RStudio kennenlernen

Aufbau der RStudio-Oberfläche:

Wichtigster Bestandteil ist das Konsolenfenster.
Dies ist quasi das Fenster "direkt in R". (So sieht R ohne RStudio aus.)

Weiterhin gibt es 
- Hilfefenster
- Dateibrowser
- Shell
- Variablenliste
- Paketliste


## Die R-Umgebung

Wenn R gestartet wird, läuft es in einer aktuellen *Umgebung*.
Diese hat ein aktuelles Arbeitsverzeichnis.
Auch bestimmt die Umgebung, welche Pakete gerade geladen sind und welche Variables und Funktionen bekannt sind.

In RStudio kann die Umgebung mit Fenstern inspiziert werden. In R selbst geht das mit Befehlen.

Erstellen einer Skriptdatei
- Im R-Universum gibt es verschiedenste Dateiformate für Skripte, Daten, Profile
- teils mit Integration in andere Werkzeuge



## Grundlegende Befehle

Grundrechenarten:
- 1+2
- 10-20
- 28 * 9
- 34 / 7

Einfache Funktionen:
- sum(1:10)
- max(c(2, 10, 4, 7, 60, 3))

Achtung: prinzipiell keine Unterscheidung zwischen Skalar und Vektor! :
- 1 + 1:3

Variablen:
- Variablen- und Funktionsnamen können Buchstaben, Zahlen, Unterstrich und Punkt(!) beinhalten
  - Punkt wird häufig als Ersatz für Leerzeichen genutzt
- zahlen.1.bis.10 <- 1:10
- sum(zahlen.1.bis.10)



Grundlegende Datenstrukturen sind:
- Vektor
- Matrix
- Liste
- Data Frame

Weitere spezialisierte Datenstrukturen wie Zeitreihen.

## Hilfesystem

- help() oder ? geben Hilfe zu einem Befehl: ?sum
  Alternativ funktioniert in RStudio F1-Taste

- Hilfemenü mit Cheatsheets


## Beispieldaten

R kommt mit einigen Beispieldaten, die auch beispielhafte Verwendungsmöglichkeiten beinhalten.

- data(mtcars) # Lädt die Daten in die aktuelle Umgebung
- example(mtcars)

Beispiel AirPassengers:
- data(AirPassenger)
- Auswählen von einzelnen Werten oder Wertereihen
- summary-Funktion
- plot-Funktion zur Visualisierung


Beispiel mtcars:
- Dataframe als Grundform der tabelle
- summary und plot sind kontextabhängig
- Zugriff auf einzelne Spalten über Spaltennamen mittels $ 
- Zugriff auf einzelne Zeilen oder Spalten mittels [,]
- hist-Funktion zur Visualisierung der Werte-Verteilung: hist(mtcars$hp)
- Plotten von Zusammenhängen: plot(mpg ~ hp, mtcars)
- Erstellen eines Linearen Modells: lm(hp ~ disp, mtcars)
- Plot mit Modell: plot(hp ~ disp, mtcars); abline(lm(hp ~ disp, mtcars), col="red")


Plots speichern:
- Für die Formate gibt es einzelne Funktionen: jpeg(), png(), pdf(), ...
- Diese Funktionen stehen vor dem Plot-Befehl
- Ist der Plot abgeschlossen, folgt dev.off()

data(mtcars)
png("hp_disp.png")
plot(hp ~ disp, mtcars)
abline(lm(hp ~ disp, mtcars), col="red")
dev.off()


Daten aus Excel einlesen:

- Laden eines Zusatzpakets: install.package(readxl); library(readxl)
- Einlesen einer Excel-Datei: read_excel("Dateiname")





