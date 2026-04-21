# Lecture 5 - Übungsblatt: Data Handling für Analyse und Modellierung

Dieses Übungsblatt passt zu `lecture_05_home_exercises.ipynb`.

## Ziel

Sie sollen den Data-Handling-Workflow aus der Vorlesung einmal selbstständig durchlaufen:

1. Umgebung prüfen und Rohdaten laden
2. Data Audit durchführen
3. Kategorien bereinigen
4. doppelte IDs und ungültige Werte prüfen
5. fehlende Werte behandeln
6. neue Features erzeugen
7. `Y` und `X` für spätere Modellierung vorbereiten
8. Ergebnis speichern

## Benötigte Dateien

| Datei | Zweck |
|---|---|
| `lecture_05_employee_survey_raw.csv` | Ausgangspunkt für die Übung |
| `lecture_05_codebook.md` | Beschreibung der Variablen |
| `lecture_05_home_exercises.ipynb` | bearbeitbares Übungsnotebook |

## Aufgabe 1 - Umgebung und Datei prüfen

Öffnen Sie Ihren Kursordner in VS Code und wählen Sie den richtigen Kernel.

Laden Sie die CSV-Datei in einen DataFrame `df`.

Prüfen Sie:

- Zeilen und Spalten
- Spaltennamen
- erste 10 Zeilen

## Aufgabe 2 - Data Audit

Nutzen Sie mindestens diese Befehle:

```python
df.shape
df.info()
df.isna().sum().sort_values(ascending=False)
df.select_dtypes(include="number").describe().T
df["department"].value_counts(dropna=False)
```

Notieren Sie kurz:

- Welche Spalten enthalten fehlende Werte?
- Welche Kategorien sind uneinheitlich?
- Welche numerischen Werte wirken unplausibel?

## Aufgabe 3 - Kategorien bereinigen

Erstellen Sie eine Kopie `clean`.

Bereinigen Sie:

- Spaltennamen
- `department`
- `gender`

## Aufgabe 4 - Doppelte IDs und gültige Wertebereiche

Prüfen Sie:

- doppelte `participant_id`
- Werte außerhalb plausibler Bereiche

Setzen Sie ungültige Werte zunächst auf `np.nan`, statt ganze Fälle blind zu löschen.

## Aufgabe 5 - Fehlende Werte

Entscheiden Sie, wie Sie mit fehlenden numerischen Werten umgehen.

Für diese Übung dürfen Sie Median-Imputation verwenden.

Notieren Sie kurz:

- Warum ist die Entscheidung nachvollziehbar?
- Welche Einschränkung hat diese Entscheidung?

## Aufgabe 6 - Feature Engineering

Erzeugen Sie mindestens drei neue Variablen.

Mögliche Beispiele:

```python
clean["workload_mean"] = clean[["workload_1", "workload_2"]].mean(axis=1)
clean["autonomy_mean"] = clean[["autonomy_1", "autonomy_2"]].mean(axis=1)
clean["support_mean"] = clean[["support_1", "support_2"]].mean(axis=1)
```

Ergänzen Sie mindestens eine eigene Feature-Idee.

## Aufgabe 7 - Model-ready data

Definieren Sie:

- `y` als Zielvariable
- `X` als Feature-Matrix

Achten Sie darauf:

- `participant_id` gehört nicht in `X`
- die Zielvariable darf nicht in `X` enthalten sein
- kategoriale Variablen müssen mit `pd.get_dummies()` codiert werden

## Aufgabe 8 - Speichern

Speichern Sie Ihren bereinigten oder model-ready Datensatz als CSV-Datei.

Verwenden Sie `index=False`, damit der pandas-Index nicht als zusätzliche Spalte gespeichert wird.

## Reflexion

Beantworten Sie am Ende im Notebook:

1. Welche Datenprobleme waren am wichtigsten?
2. Welche Entscheidungen waren eindeutig?
3. Welche Entscheidungen könnten auch anders getroffen werden?
4. Welche Variable würden Sie in einem Modell besonders vorsichtig behandeln?
5. Welche Frage würden Sie in der nächsten Sitzung gern klären?
