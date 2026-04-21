# Lecture 5 - Codebook für Demonstrationsdaten

Datensatz: `lecture_05_employee_survey_raw.csv`

Alle Daten sind fiktiv und dienen nur der Demonstration von Data Handling.

## Variablen

- `participant_id`: eindeutige ID pro Person. Nicht als Prädiktor verwenden.
- `department`: Abteilung. Muss bereinigt und ggf. dummy-codiert werden.
- `gender`: Geschlecht / Angabe. Muss bereinigt und ggf. dummy-codiert werden.
- `age`: Alter in Jahren.
- `weekly_hours`: Wochenarbeitszeit.
- `sleep_hours`: durchschnittliche Schlafdauer pro Nacht.
- `commute_minutes`: Pendelzeit in Minuten.
- `workload_1`, `workload_2`: Arbeitsbelastung, 1 bis 5.
- `autonomy_1`, `autonomy_2`: Autonomie, 1 bis 5.
- `support_1`, `support_2`: soziale Unterstützung, 1 bis 5.
- `stress_score`: Stresswert, 0 bis 100.
- `motivation`: Motivation, 1 bis 5.
- `satisfaction`: Arbeitszufriedenheit, 1 bis 5. In unseren Übungen oft Zielvariable `Y`.
- `performance_rating`: Leistungsbewertung, 1 bis 5.
- `absent_days`: Fehltage.

## Eingebaute Datenprobleme

Der Rohdatensatz enthält absichtlich kleine Probleme:

- fehlende Werte
- inkonsistente Schreibweisen von Kategorien
- eine doppelte ID
- Werte außerhalb erwarteter Bereiche
- Variablen, die für Modelle ungeeignet sind, z. B. IDs

## Ziel

Aus diesem Rohdatensatz entsteht schrittweise ein analyse- und modellierbarer Datensatz.
