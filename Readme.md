# Package Development 

Materialien für eine Einführung zum Thema Package-Entwicklung in R. Die Einführung basiert auf einem useR2019-Tutorial:

https://github.com/jennybc/pkg-dev-tutorial

## 1. Intro 

Package-Workflow
https://github.com/jennybc/pkg-dev-tutorial/blob/master/intro-basic-workflow.pdf

Documentation 
https://github.com/jennybc/pkg-dev-tutorial/blob/master/document-share.pdf


## 2. Wir entwickeln gemeinsam ein Package 

Wir wollen gemeinsam ein Package entwickeln, welches es ermöglicht, Datensätze in Excel-Dateien mit minimaler Formattierung abzuspeichern. Im Repository liegt ein R-Skript (fancy_excel.R) bereit, welches eine erste Funktion enthält, die Teil des Packages sein soll.

Klont dieses Repository und legt selber ein Package an, damit wir den Prozess gemeinsam durchgehen können. Wir schauen uns die Stuktur des packages an und generieren die Dokumentation dazu.

Folgende packages benötigen wir für  die Erstellung unseres Beispiel-Packages. Das `usethis`-Package erleichtert den Entwicklungsprozess massgeblich. Das `openxlsx`-package benötigen wir für die Beispiel-Funktion, die wir in unserem Package anbieten wollen. 

```
install.packages(c(
"devtools", "roxygen2", "knitr","openxslx"
))

library("devtools")
library("openxlsx")
```

Das `usethis`-Package erleichtert den Entwicklungsprozess massgeblich (wird beim laden von devtools mitgeladen).

```
usethis::create_package("fancyexcel")
```


__Aufgaben__

1. Legt unsere `fancy_excel`- Funktion in den für sie vorgesehenen Ordner. Ladet im Anschluss das Package um die Funktion ausführen zu können (`devtools::load_all()`).

2. Überlegt euch ein kurzes Beispiel für die Verwendung unserer 'fancy_excel' Funktion mit einem Testdatensatz und fügt es unter @examples hinzu  [document & share Präsentation, Folie 5](https://github.com/jennybc/pkg-dev-tutorial/blob/master/document-share.pdf)

3. Tragt euch als Maintainer im Description-File ein.

4. Erzeugt die Dokumentation neu via `devtools::document()`

__Extras__

5. Erweitert die `fancy_excel` Funktion damit auch eine Quelle angegeben werden kann. Dafür könnt ihr einen neuen source - parameter einführen, der analog zum Titel übergeben werden kann. Führt das Argument als neuen @param in der Dokumentation ein.

6. Erzeugt eine pkgdown-Seite [siehe document & share Präsentation, Folie 28](https://github.com/jennybc/pkg-dev-tutorial/blob/master/document-share.pdf)
