# Finanzmathe & Stochastik

Eine Quarto-Website mit Themen aus der Finanzmathematik, hergeleitet mit Wahrscheinlichkeitstheorie.
Jedes Thema ist wie ein Vorlesungsskript aufgebaut: erst das Modell, dann Definitionen, Sätze und
Beweise, und nach jedem wichtigen Schritt eine kurze Erklärung in Worten. Simulationen in R machen
die Aussagen sichtbar.

## Themen

- **Brownsche Bewegung**: von der einfachen Irrfahrt zum Zufall in stetiger Zeit (ZGS, Konstruktion
  nach Lévy, Martingale und Ruinproblem, quadratische Variation, geometrische Brownsche Bewegung)
- **Kelly-Kriterium**: optimaler Einsatz bei günstigen Wetten (Wachstumsrate, Submartingale,
  Optimalität über Martingalkonvergenz, Maximum Likelihood und KL-Divergenz)
- weitere Themen folgen

Vorausgesetzt wird Stoff aus Stochastik und Wahrscheinlichkeitstheorie: bedingte Erwartung,
Martingale und das starke Gesetz der großen Zahlen.

## Entstehung

Die Inhalte entstehen mit Unterstützung von KI (Claude von Anthropic): beim Ausarbeiten von
Herleitungen und Beweisen, beim Schreiben des R-Codes für die Simulationen und beim Aufbau der
Website. Ich lese und prüfe die Inhalte nach und nach; noch ist nicht alles durchgesehen.

## Aufbau

```
_quarto.yml               Website-Konfiguration (Navigation, Theme, Freeze)
index.qmd                 Startseite
notation.qmd              Schreibweisen
styles.scss               eigenes Styling (Hell- und Dunkelmodus)
themen/
  brownsche-bewegung.qmd
  kelly.qmd
```

## Lokal rendern

Voraussetzungen:

- [Quarto](https://quarto.org/docs/get-started/) (getestet mit 1.9)
- [R](https://cran.r-project.org/) mit den Paketen `rmarkdown`, `knitr` und `ggplot2`:

  ```r
  install.packages(c("rmarkdown", "knitr", "ggplot2"))
  ```

Dann im Projektordner:

```bash
quarto preview   # Vorschau im Browser, aktualisiert sich beim Speichern
quarto render    # baut die komplette Website nach _site/
```

Durch `freeze: auto` wird der R-Code einer Seite nur neu ausgeführt, wenn sich ihre `.qmd`-Datei
geändert hat. `_site/`, `_freeze/` und `.quarto/` werden nicht versioniert.
