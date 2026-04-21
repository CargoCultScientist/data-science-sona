---
title: "Lecture 5 Reader - Data Handling für Analyse und Modellierung"
subtitle: "Nachbereitung, Dateiübersicht und Grundlagenanhang"
author: "Data Science | HS Fresenius"
lang: de-DE
---

# Lecture 5 Reader - Data Handling für Analyse und Modellierung

# Zweck dieses Readers

Dieser Reader ist für die Nachbereitung gedacht. Er ist besonders für Studierende geschrieben, die in der Sitzung nicht anwesend waren oder den Workflow zu Hause Schritt für Schritt wiederholen möchten.

Die wichtigste Botschaft dieser Vorlesung:

> Es geht nicht darum, Python als Sprache auswendig zu lernen. Python und pandas sind hier Werkzeuge. Der eigentliche Lerngegenstand ist der Data-Handling-Workflow: Daten prüfen, Regeln anwenden, Entscheidungen dokumentieren und einen Datensatz für Analyse und Modellierung vorbereiten.

# Dateiübersicht

Alle Dateien sollten im gleichen Kursordner liegen. Öffnen Sie diesen Ordner in VS Code, bevor Sie ein Notebook starten.

## Präsentation und Nachbereitung

- `lecture_05_data_handling_modeling.pptx`
  - Verwendung: während der Vorlesung
  - Zweck: Folien mit Sprechtext in den Notizen

- `lecture_05_script.md`
  - Verwendung: für Durchführung und Nachbereitung
  - Zweck: ausführliche Sprechtextfassung mit Übergängen und Kontrollfragen

- `lecture_05_reader_data_handling.pdf`
  - Verwendung: nach der Vorlesung
  - Zweck: dieser Reader als PDF

- `lecture_05_reader_data_handling.md`
  - Verwendung: im Kurs-GitHub oder zur Bearbeitung
  - Zweck: Markdown-Version dieses Readers

## Daten und Codebook

- `lecture_05_codebook.md`
  - Verwendung: vor der Datenarbeit
  - Zweck: kurze Beschreibung der Variablen

- `lecture_05_employee_survey_raw.csv`
  - Verwendung: Startpunkt von Notebook 1 und Hausaufgabe
  - Zweck: fiktiver Rohdatensatz mit eingebauten Datenproblemen

- `lecture_05_employee_survey_cleaned_reference.csv`
  - Verwendung: Backup für Notebook 2
  - Zweck: bereinigte Referenzdatei, falls Notebook 1 nicht abgeschlossen wurde

- `lecture_05_employee_survey_model_ready_reference.csv`
  - Verwendung: Kontrolle
  - Zweck: Beispiel für eine model-ready Datei

## Notebooks

- `lecture_05_notebook_01_data_audit_cleaning.ipynb`
  - Verwendung: erster Notebook-Block
  - Zweck: Data Audit, Kategorien, Dubletten, Wertebereiche, Missing Values

- `lecture_05_notebook_01_data_audit_cleaning_executed.ipynb`
  - Verwendung: Nachlesen
  - Zweck: Notebook 1 mit ausgeführten Ergebnissen

- `lecture_05_notebook_02_feature_engineering_model_ready.ipynb`
  - Verwendung: zweiter Notebook-Block
  - Zweck: Feature Engineering, Summary Statistics, `Y` und `X`

- `lecture_05_notebook_02_feature_engineering_model_ready_executed.ipynb`
  - Verwendung: Nachlesen
  - Zweck: Notebook 2 mit ausgeführten Ergebnissen

- `lecture_05_home_exercises.ipynb`
  - Verwendung: Hausaufgabe
  - Zweck: selbstständige Wiederholung des Workflows

- `lecture_05_exercise_sheet.md`
  - Verwendung: Hausaufgabe oder GitHub
  - Zweck: kurze Aufgabenübersicht

\pagebreak

# Empfohlene Reihenfolge

Wenn Sie die Sitzung zu Hause nacharbeiten, gehen Sie bitte in dieser Reihenfolge vor:

1. Öffnen Sie den Kursordner in VS Code.
2. Öffnen Sie diesen Reader.
3. Öffnen Sie `lecture_05_codebook.md`.
4. Öffnen Sie `lecture_05_notebook_01_data_audit_cleaning.ipynb`.
5. Führen Sie die Environment-Check-Zelle aus.
6. Laden Sie `lecture_05_employee_survey_raw.csv`.
7. Arbeiten Sie Notebook 1 Abschnitt für Abschnitt durch.
8. Speichern Sie am Ende die bereinigte Datei.
9. Öffnen Sie `lecture_05_notebook_02_feature_engineering_model_ready.ipynb`.
10. Arbeiten Sie Feature Engineering und Vorbereitung von `Y` und `X` durch.
11. Bearbeiten Sie anschließend `lecture_05_home_exercises.ipynb`.

# Was heute fachlich gelernt werden soll

Nach dieser Vorlesung sollten Sie erklären können:

- warum Rohdaten selten sofort analysebereit sind
- was ein Data Audit ist
- warum Bereinigungsentscheidungen begründet werden müssen
- wie man fehlende Werte, Dubletten, Kategorien und Wertebereiche prüft
- was der Unterschied zwischen analysis-ready und model-ready data ist
- wie `Y` und `X` für spätere Modellierung vorbereitet werden
- warum IDs, Zielvariablen und Leakage-Variablen nicht unkritisch in `X` gehören

# Die Data-Handling-Pipeline

```text
Rohdaten
  -> Data Audit
  -> Cleaning
  -> analysis-ready data
  -> Feature Engineering
  -> model-ready data
  -> Modellierung
```

Diese Pipeline ist wichtiger als einzelne Python-Befehle. Die Befehle helfen nur dabei, die Schritte reproduzierbar auszuführen.

## Rohdaten

Rohdaten sind die Ausgangsdaten. Sie können Schreibfehler, fehlende Werte, unplausible Werte oder doppelte Fälle enthalten.

## Data Audit

Beim Data Audit prüfen wir den Datensatz, ohne sofort alles zu verändern. Ziel ist: Datenprobleme sichtbar machen.

## Cleaning

Beim Cleaning wenden wir nachvollziehbare Regeln an. Beispiele: Kategorien vereinheitlichen, unplausible Werte markieren, Dubletten behandeln.

## Analysis-ready data

Ein analysis-ready Datensatz ist sauber genug für deskriptive Analysen.

## Model-ready data

Ein model-ready Datensatz hat zusätzlich eine klare Zielvariable `Y`, eine Feature-Matrix `X` und numerisch passende Prädiktoren.

\pagebreak

# Environment-Check und Dateiorganisation

Führen Sie zu Beginn eines Notebooks diesen Check aus:

```python
import sys
import pandas as pd

print(sys.executable)
print(pd.__version__)
```

Wenn das ohne Fehler läuft, sind Kernel und pandas grundsätzlich bereit.

Wichtig ist außerdem:

- Der Kursordner muss in VS Code geöffnet sein.
- Die CSV-Dateien müssen im gleichen Ordner liegen wie die Notebooks.
- Der Kernel ist die Python-Umgebung, die das Notebook tatsächlich ausführt.
- Der Ordner ist nicht dasselbe wie das Conda-Environment.

# Notebook 1: Data Audit und Cleaning

## Ziel

Aus dem Rohdatensatz entsteht ein bereinigter Datensatz.

## Typische Diagnosebefehle

```python
df = pd.read_csv("lecture_05_employee_survey_raw.csv")
df.head()
df.shape
df.info()
df.isna().sum().sort_values(ascending=False)
df.select_dtypes(include="number").describe().T
```

## Fachliche Fragen

- Sind Fälle und Variablen plausibel?
- Welche Werte fehlen?
- Welche Kategorien sind uneinheitlich?
- Gibt es doppelte IDs?
- Welche Werte liegen außerhalb sinnvoller Bereiche?
- Welche Regeln verwenden wir für die Bereinigung?

## Ergebnis

Notebook 1 erzeugt:

```text
lecture_05_employee_survey_cleaned.csv
```

Diese Datei wird in Notebook 2 verwendet.

# Notebook 2: Feature Engineering und model-ready data

## Ziel

Aus dem bereinigten Datensatz entstehen neue Variablen und eine model-ready Struktur.

## Beispiel: neue Skalenvariablen

```python
df["workload_mean"] = df[["workload_1", "workload_2"]].mean(axis=1)
df["autonomy_mean"] = df[["autonomy_1", "autonomy_2"]].mean(axis=1)
df["support_mean"] = df[["support_1", "support_2"]].mean(axis=1)
```

## Zielvariable und Prädiktoren

```python
y = df["satisfaction"]

X_num = df[num_predictors]
X_cat = pd.get_dummies(df[cat_predictors], drop_first=True, dtype=int)
X = pd.concat([X_num, X_cat], axis=1)
```

## Wichtige Regeln

- `satisfaction` ist `Y`, wenn wir Zufriedenheit vorhersagen wollen.
- `satisfaction` darf dann nicht in `X` stehen.
- `participant_id` ist eine Verwaltungsvariable und normalerweise kein Prädiktor.
- Textkategorien müssen für viele Modelle in numerische Spalten umgewandelt werden.
- Variablen aus der Zukunft erzeugen Data Leakage und dürfen nicht unkritisch verwendet werden.

\pagebreak

# Hausaufgabe

Bearbeiten Sie:

```text
lecture_05_home_exercises.ipynb
```

Ziel ist, den Workflow eigenständig nachzubauen.

Bitte dokumentieren Sie in Markdown:

- welche Probleme Sie gefunden haben
- welche Bereinigungsregeln Sie angewendet haben
- welche neuen Features Sie erzeugt haben
- welche Variable Sie als `Y` verwenden
- welche Variablen in `X` liegen sollen
- welche Entscheidungen Sie unsicher fanden

# Wichtige pandas-Befehle

| Befehl | Bedeutung |
|---|---|
| `pd.read_csv(...)` | CSV-Datei laden |
| `df.head()` | erste Zeilen anzeigen |
| `df.shape` | Anzahl Zeilen und Spalten |
| `df.info()` | Datentypen und fehlende Werte |
| `df.describe()` | Summary Statistics |
| `df.isna().sum()` | fehlende Werte zählen |
| `value_counts()` | Kategorien zählen |
| `drop_duplicates()` | doppelte Fälle entfernen |
| `fillna()` | fehlende Werte ersetzen |
| `groupby()` | Kennzahlen nach Gruppen berechnen |
| `pd.get_dummies()` | Kategorien in 0/1-Spalten umwandeln |
| `to_csv(..., index=False)` | CSV-Datei speichern |

# Häufige Fehler und Lösungen

## Datei wird nicht gefunden

Prüfen Sie:

- Liegt die CSV-Datei im gleichen Ordner wie das Notebook?
- Ist der Kursordner in VS Code geöffnet?
- Ist der Dateiname exakt gleich geschrieben?

## pandas lässt sich nicht importieren

Prüfen Sie:

- Ist der richtige Kernel ausgewählt?
- Ist das richtige Conda-Environment aktiv?
- Wurde das Notebook nach einem Kernel-Wechsel neu gestartet?

## Notebook 2 findet die bereinigte Datei nicht

Lösung:

- Führen Sie Notebook 1 aus, damit `lecture_05_employee_survey_cleaned.csv` entsteht.
- Alternativ verwendet Notebook 2 die Referenzdatei `lecture_05_employee_survey_cleaned_reference.csv`.

## Dummy-Variablen sehen ungewohnt aus

Das ist normal. Textkategorien werden in 0/1-Spalten übersetzt, damit Modelle damit rechnen können.

\pagebreak

# Abschluss-Checkliste

Nach Lecture 5 sollten Sie abhaken können:

- Ich kann den Kursordner in VS Code öffnen.
- Ich kann den richtigen Kernel prüfen.
- Ich kann eine CSV-Datei mit pandas laden.
- Ich kann Struktur, Datentypen und fehlende Werte prüfen.
- Ich kann Kategorien vereinheitlichen.
- Ich kann doppelte IDs sichtbar machen.
- Ich kann unplausible Werte anhand von Regeln markieren.
- Ich kann fehlende Werte bewusst behandeln.
- Ich kann neue Features begründet erzeugen.
- Ich kann `Y` und `X` für spätere Modellierung vorbereiten.
- Ich kann erklären, warum es heute nicht um Sprachlernen, sondern um Datenlogik geht.

# Anhang: Grundbegriffe aus den vorherigen Vorlesungen

## VS Code, Ordner, Environment, Interpreter und Kernel

| Begriff | Bedeutung |
|---|---|
| Ordner / Workspace | Speicherort und Projektkontext Ihrer Dateien |
| Conda-Environment | eigene Python-Umgebung mit eigenen Paketen |
| Python-Interpreter | das konkrete Python, das `.py`-Dateien ausführt |
| Jupyter-Kernel | das Python, das ein Notebook ausführt |
| `sys.executable` | zeigt den Pfad des tatsächlich laufenden Python |

Merksatz:

```text
Ordner = wo die Dateien liegen
Environment / Kernel = welches Python die Dateien ausführt
```

## Python-Skript, Markdown und Jupyter-Notebook

| Begriff | Bedeutung |
|---|---|
| `.py`-Skript | Datei mit Python-Code |
| Markdown | Textformat für Überschriften, Erklärungen und Reflexionen |
| Jupyter-Notebook | Mischung aus Markdown-Zellen und Code-Zellen |
| Code-Zelle | führt Python-Code aus |
| Markdown-Zelle | erklärt, was und warum etwas gemacht wird |

Für diese Vorlesung ist Markdown wichtig, weil Sie Bereinigungsentscheidungen dokumentieren sollen.

## DataFrame-Grundlogik

| Begriff | Bedeutung |
|---|---|
| DataFrame | tabellarische Datenstruktur in pandas |
| Zeile | Fall, Beobachtung oder Person |
| Spalte | Variable oder Merkmal |
| Zelle | einzelner Wert |
| Index | technische Zeilenbeschriftung |

Beispiel:

```python
df.loc[0, "satisfaction"]
```

Das bedeutet: Wert der ersten Zeile in der Spalte `satisfaction`.

\pagebreak

## Variablen und Datentypen

Wichtige Datentypen im Data Handling:

| Typ | Beispiel | Bedeutung |
|---|---|
| numerisch | `stress_score = 62` | kann direkt für Rechnungen genutzt werden |
| kategorial | `department = "sales"` | muss oft bereinigt oder codiert werden |
| Boolean | `is_manager = True` | Wahr/Falsch-Information |
| fehlend | `NaN` | Wert fehlt oder wurde als ungültig markiert |

## Verbindung zu Regression und Modellierung

Aus Lecture 4 kennen Sie:

```text
Y = abhängige Variable / Zielvariable
X = unabhängige Variablen / Prädiktoren
```

In Lecture 5 bereiten wir genau diese Struktur vor.

Beispiel:

```python
y = df["satisfaction"]
X = df[["stress_score", "motivation", "workload_mean"]]
```

Data Handling ist also die Brücke von Rohdaten zu einer Regressions- oder Modellierungsfrage.

## Die wichtigsten Bereinigungsregeln

1. Rohdaten nicht überschreiben.
2. Immer zuerst prüfen, dann bereinigen.
3. Auf einer Kopie arbeiten, zum Beispiel `clean = df.copy()`.
4. Kategorien vereinheitlichen, bevor sie gezählt oder modelliert werden.
5. Wertebereiche fachlich prüfen.
6. Fehlende Werte nicht automatisch löschen.
7. Dubletten sichtbar machen, bevor sie entfernt werden.
8. Bereinigungsentscheidungen in Markdown dokumentieren.
9. `Y` nicht versehentlich in `X` aufnehmen.
10. IDs und Leakage-Variablen kritisch prüfen.

# Minimalpfad für Abwesende

Wenn Sie nur einen sehr knappen Nachholweg brauchen:

1. Lesen Sie Abschnitt 1 bis 5 dieses Readers.
2. Öffnen Sie Notebook 1 und führen Sie alle Zellen aus.
3. Lesen Sie die Markdown-Erklärungen direkt vor jeder Codezelle.
4. Öffnen Sie Notebook 2 und führen Sie alle Zellen aus.
5. Bearbeiten Sie die Hausaufgabe.
6. Notieren Sie mindestens drei Fragen für die nächste Sitzung.
