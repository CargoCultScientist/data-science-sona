# Data-Handling Report

**Datensatz:** Employee Survey (fiktiv, N = 81)
**Ziel:** Rohdaten in einen analyse- und modellierbaren Datensatz überführen
**Erstellt mit:** Claude (KI-gestützter Workflow)

---

## 1. Ausgangslage

Der Rohdatensatz `lecture_05_employee_survey_raw.csv` enthält 81 Zeilen und 18 Spalten aus einer fiktiven Mitarbeiterbefragung. Die Daten enthalten absichtlich eingebaute Qualitätsprobleme, wie sie in realen Projekten typisch sind.

## 2. Durchgeführte Schritte

### 2.1 Data Audit

| Kategorie | Befund |
|---|---|
| Fehlende Werte | 8 Spalten betroffen (je 1 Wert pro Spalte) |
| Inkonsistente Kategorien | `department`: 4 Schreibweisen für 6 Kategorien (z. B. `sales`, `MKT`, `IT `) |
| | `gender`: Abkürzungen (`F`, `m`) neben Langformen |
| Doppelte IDs | `P010` kommt zweimal vor (unterschiedliche `satisfaction`-Werte) |
| Ungültige Werte | `sleep_hours = -1.0` (P031), `age = 17` (P023), `satisfaction = 6.0` (P042) |

### 2.2 Kategorienbereinigung

- **department**: Normalisierung auf 6 einheitliche Kategorien (`HR`, `IT`, `Marketing`, `Operations`, `Sales`, `Unknown`)
- **gender**: Normalisierung auf 5 Kategorien (`Female`, `Male`, `Nonbinary`, `Prefer not to say`, `Unknown`)
- Methode: `str.strip().str.lower()` + Mapping-Dictionary

### 2.3 Dubletten und Wertebereiche

- **P010** (doppelt): Erster Eintrag behalten, zweiter entfernt → 80 Zeilen
- **Ungültige Werte**: 3 Werte auf `NaN` gesetzt (Regeln aus Codebook: Likert 1–5, sleep 0–12, age 18–67)

### 2.4 Fehlende Werte

- **Strategie**: Median-Imputation für alle numerischen Spalten
- **Begründung**: Robust gegenüber Ausreißern, für Demo-Zwecke nachvollziehbar
- **Einschränkung**: Varianz wird unterschätzt; bei systematischem Missingness nicht angemessen
- **Ergebnis**: 0 fehlende Werte nach Imputation

### 2.5 Feature Engineering

| Neues Feature | Formel | Bedeutung |
|---|---|---|
| `workload_mean` | mean(workload_1, workload_2) | Arbeitsbelastung (Skala) |
| `autonomy_mean` | mean(autonomy_1, autonomy_2) | Autonomie (Skala) |
| `support_mean` | mean(support_1, support_2) | Soziale Unterstützung (Skala) |
| `overload_index` | workload_mean + stress/25 - sleep/4 | Zusammengesetzter Belastungsindex |

### 2.6 Model-ready Data

- **Zielvariable (Y):** `satisfaction` (1–5)
- **Prädiktoren (X):** 10 numerische + 9 dummy-codierte Spalten = 19 Features
- **Ausgeschlossen:** `participant_id` (ID), `satisfaction` (Zielvariable), Einzel-Items (durch Mittelwerte ersetzt)
- **Dummy-Codierung:** `pd.get_dummies(drop_first=True)` für `department` und `gender`

## 3. Ergebnis-Überblick

| Kennzahl | Rohdaten | Model-ready |
|---|---|---|
| Zeilen | 81 | 80 |
| Spalten | 18 | 21 (inkl. participant_id + Y) |
| Fehlende Zellen | 8 | 0 |
| Kategorien (department) | 8 Schreibweisen | 6 saubere Kategorien |
| Kategorien (gender) | 7 Schreibweisen | 5 saubere Kategorien |
| Prädiktoren für Modell | — | 19 |

## 4. Was Claude hier geleistet hat

Dieser Report und das begleitende Notebook wurden vollständig von Claude generiert. Die folgenden Arbeitsschritte wurden dabei automatisiert bzw. erheblich beschleunigt:

### Diagnose in Sekunden statt Minuten

- Fehlende Werte, Dubletten, Kategorie-Inkonsistenzen und ungültige Wertebereiche wurden in einem Durchlauf erkannt und tabellarisch aufbereitet.
- Manuell erfordert das mehrere `value_counts()`-, `describe()`- und `isna()`-Aufrufe mit anschließender Interpretation.

### Bereinigung mit dokumentierten Regeln

- Mapping-Dictionaries für Kategorien, Bereichsregeln für numerische Werte und Imputations-Entscheidungen wurden direkt als ausführbarer Code formuliert.
- Jede Entscheidung ist im Code nachvollziehbar — kein manuelles Copy-Paste zwischen Zellen.

### Visualisierung als Nebenprodukt

- Vorher/Nachher-Plots für jeden Schritt entstanden parallel zur Bereinigung.
- In einem manuellen Workflow wäre die Visualisierung ein zusätzlicher Aufwand, der häufig übersprungen wird.

### Report-Erstellung

- Dieser Report wurde aus den gleichen Erkenntnissen generiert, die auch das Notebook enthält.
- Statt nach der Analyse einen separaten Report zu schreiben, entsteht beides in einem Arbeitsschritt.

### Konsistenzprüfung

- Claude hat vor der Report-Erstellung die gesamten Kursmaterialien (Notebooks, Übungsblätter, Referenzdateien, Codebook) auf Inkonsistenzen geprüft und zwei Probleme gefunden und behoben:
  - Referenzdatei fehlte eine Spalte (`overload_index`)
  - Übungsblatt und Notebook hatten unterschiedliche Aufgabennummerierung

## 5. Dateien in diesem Ordner

| Datei | Inhalt |
|---|---|
| `data_handling_visual_report.ipynb` | Jupyter-Notebook mit vollständigem Workflow und Vorher/Nachher-Plots |
| `Data-Handling Report.md` | Dieses Dokument — team-taugliche Zusammenfassung |
| `model_ready_from_report.csv` | Erzeugter model-ready Datensatz (wird beim Ausführen des Notebooks erstellt) |
