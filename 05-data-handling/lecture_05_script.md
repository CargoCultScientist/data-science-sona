# Lecture 5 - Data Handling für Analyse und Modellierung

## Erweiterte Sprechtextfassung für die Durchführung

Diese Version erweitert die Notizen, ohne den fachlichen Inhalt der Vorlesung zu verändern. Sie enthält Moderationshinweise, Übergänge, Kontrollfragen und Hinweise für den Wechsel zwischen PowerPoint und Notebook.

---

## Slide 1

Ziel dieser Einstiegsfolie: den roten Faden setzen.
Sagen Sie sinngemäß: Willkommen zur fünften Vorlesung. Nach der Regression gehen wir heute einen Schritt zurück. Wir fragen nicht zuerst, welches Modell wir rechnen, sondern: Wie müssen Daten aussehen, damit Analyse und Modellierung überhaupt sinnvoll möglich sind?
Betonen Sie: Rohdaten sind selten sofort analysebereit. Heute geht es um einen Workflow, der immer wieder gebraucht wird: einlesen, prüfen, bereinigen, neue Variablen erzeugen und am Ende eine Struktur vorbereiten, die später für Modelle genutzt werden kann.
Übergang: Wir ordnen zuerst ein, wo diese Sitzung im Kurs steht.

---

## Slide 2

Ziel: die Sitzung in den Kursverlauf einbetten.
Sagen Sie: Wir haben die technische Umgebung aufgebaut, erste Notebooks genutzt und in Lecture 4 Regression als Vorhersage-Logik verstanden. Heute kommt die Datenbasis dazu. Ein Modell kann nur so gut sein wie die Daten, die hineingehen.
Kurzer Akzent: Data Handling ist nicht nur Vorarbeit. Es entscheidet oft darüber, ob spätere Ergebnisse sinnvoll interpretierbar sind.
Frage an die Gruppe: Was könnte bei einem Datensatz schiefgehen, bevor wir überhaupt ein Modell rechnen?
Übergang: Aus dieser Perspektive ergeben sich die konkreten Lernziele für heute.

---

## Slide 3

Ziel: klare Erwartungen setzen.
Sagen Sie: Am Ende der Sitzung sollen Sie nicht jeden Befehl auswendig können. Wichtiger ist, dass Sie wissen, welche Fragen man an einen neuen Datensatz stellt und wie man diese Fragen mit pandas beantwortet.
Gehen Sie die Punkte langsam durch: CSV laden, Struktur prüfen, fehlende Werte erkennen, Kategorien bereinigen, neue Variablen bilden und schließlich Y und X vorbereiten.
Entlastender Hinweis: Die Syntax wird im Notebook wiederholbar dokumentiert. In der Sitzung geht es vor allem darum, die Arbeitslogik zu verstehen.
Übergang: Diese Arbeitslogik üben wir heute im Wechsel zwischen Folien und Notebook.

---

## Slide 4

Ziel: Arbeitsmodus erklären und technische Unruhe reduzieren.
Sagen Sie: Wir arbeiten heute in kurzen Schleifen. Eine Folie gibt die Idee, danach probieren wir es im Notebook aus. Danach besprechen wir kurz, was passiert ist.
Bitte lassen Sie VS Code geöffnet. Es ist normal, wenn jemand einmal beim Kernel oder Dateipfad hängen bleibt. Wir lösen das möglichst kurz und kehren dann wieder zum Ablauf zurück.
Moderation: Wer schneller fertig ist, kann der Person neben sich helfen.
Übergang: Bevor wir Daten laden, prüfen wir ganz kurz, ob die Umgebung funktioniert.

---

## Slide 5

Ziel: sicherstellen, dass die technische Basis steht.
Sagen Sie: Dieser Check ist bewusst kurz. Wir prüfen nicht die gesamte Installation, sondern nur das, was wir heute brauchen: richtiger Ordner, richtiger Kernel, pandas und sichtbare CSV-Datei.
Wichtig formulieren: Der Projektordner ist der Ort der Dateien. Das Conda-Environment ist die Python-Umgebung. Der Kernel ist das Python, das ein Notebook tatsächlich verwendet.
Aktion: Alle öffnen Notebook 1 und führen die erste Import-Zelle aus.
Übergang: Wenn der Minimalcheck funktioniert, starten wir mit Notebook 1.

---

## Slide 6

Ziel: erster Wechsel ins Notebook.
Sagen Sie: Jetzt wechseln wir gemeinsam in VS Code. Öffnen Sie Notebook 1. Wir prüfen den Kernel und führen die ersten Zellen aus.
Erwartung: `df.head()` sollte eine kleine Tabelle zeigen. Wenn eine Fehlermeldung kommt, prüfen Sie zuerst, ob die CSV-Datei im gleichen Ordner liegt.
Moderation: Nicht zu lange an Einzelfällen hängen. Bei größeren Problemen Studierende bitten, kurz mitzuschauen oder später gezielt nachzuziehen.
Übergang zurück zur Folie: Sobald alle den Datensatz sehen, erklären wir, warum dieser Schritt für jede Analyse so wichtig ist.

---

## Slide 7

Ziel: Bedeutung von Data Handling klären.
Sagen Sie: Data Handling klingt manchmal wie ein technischer Nebenschritt. Tatsächlich ist es ein Kernteil jeder Datenanalyse. Fehlende Werte, uneinheitliche Kategorien oder unplausible Zahlen können Ergebnisse stärker verändern als das spätere Modell.
Beispiel nennen: Wenn `Sales` und `sales` als zwei Abteilungen gezählt werden, ist jeder Gruppenvergleich fragwürdig.
Frage: Welche Art von Datenproblem wäre bei einer Mitarbeiterbefragung besonders kritisch?
Übergang: Um solche Probleme systematisch zu bearbeiten, nutzen wir eine Pipeline.

---

## Slide 8

Ziel: Pipeline als roten Faden etablieren.
Sagen Sie: Diese Folie ist unser Fahrplan. Wir starten bei Rohdaten. Danach prüfen und bereinigen wir. Dann haben wir analysis-ready data. Wenn wir modellieren wollen, brauchen wir zusätzlich model-ready data mit klarer Zielvariable Y und Prädiktoren X.
Betonen Sie: Nicht jeder Datensatz muss sofort model-ready sein. Aber jeder Datensatz sollte zumindest verstanden und geprüft werden.
Übergang: Wir schauen uns jetzt den konkreten Datensatz an, mit dem wir heute arbeiten.

---

## Slide 9

Ziel: Beispieldatensatz vorstellen.
Sagen Sie: Der Datensatz ist fiktiv, aber absichtlich realistisch unordentlich. Er enthält typische Probleme: Missing Values, unterschiedliche Schreibweisen, unplausible Werte und eine doppelte ID.
Interaktion: Fragen Sie: Welche Spalten würden Sie zuerst prüfen, wenn Sie diesen Datensatz bekommen?
Nehmen Sie 2-3 Antworten auf. Falls nötig, lenken Sie auf Kategorien, Skalenbereiche und IDs.
Übergang: Bevor wir prüfen, erinnern wir uns an die einfache Tabellenlogik.

---

## Slide 10

Ziel: DataFrame-Grundstruktur sichern.
Sagen Sie: Diese Struktur kennen viele aus Excel oder SPSS. Eine Zeile ist ein Fall, eine Spalte ist eine Variable, eine Zelle ist ein einzelner Wert.
Wichtig: Der pandas-Index ist eine technische Zeilenbeschriftung. Er ist nicht automatisch eine inhaltliche ID.
Kurze Demo-Idee: Zeigen Sie eine Zelle mit `df.loc[0, 'satisfaction']`.
Übergang: Jetzt gehen wir wieder ins Notebook und lesen die Rohdaten bewusst ein.

---

## Slide 11

Ziel: Rohdaten laden und erste Sichtprüfung machen.
Sagen Sie vor dem Wechsel: Im Notebook geht es jetzt nur um Orientierung. Wir laden die CSV und schauen, ob die Daten so aussehen, wie wir erwarten.
Aktion: Studierende führen die Zellen zu `read_csv`, `head`, `shape` und `columns` aus.
Frage nach der Ausführung: Was lernen wir aus `shape`, was wir aus `head` nicht lernen?
Übergang: Nach diesem ersten Blick brauchen wir ein kleines Standardset an Diagnosebefehlen.

---

## Slide 12

Ziel: Standardbefehle als wiederholbare Routine einführen.
Sagen Sie: Diese fünf Befehle sind ein Grundwerkzeug für fast jeden neuen Datensatz. Sie sind nicht spektakulär, aber sehr wirksam.
Gehen Sie kurz durch: `head` zeigt Beispiele, `shape` die Größe, `info` Datentypen und fehlende Werte, `describe` numerische Verteilungen, `value_counts` Kategorien.
Wichtig: Diese Befehle liefern noch keine fertige Interpretation. Sie helfen beim Audit.
Übergang: Aus diesen Befehlen ergeben sich vier Diagnosefragen.

---

## Slide 13

Ziel: Diagnosefragen strukturieren.
Sagen Sie: Bevor wir bereinigen, müssen wir wissen, welches Problem wir haben. Die vier Fragen sind eine Art Checkliste.
Interaktion: Welche Frage ist bei Befragungsdaten besonders kritisch? Lassen Sie kurz sammeln.
Mögliche Rahmung: Fehlende Werte können systematisch sein; Kategorien können unabsichtlich getrennt werden; Wertebereiche sind bei Skalen wichtig.
Übergang: Wir starten mit einem der häufigsten Probleme: fehlenden Werten.

---

## Slide 14

Ziel: Missing Values konzeptuell einordnen.
Sagen Sie: Fehlende Werte sind nicht einfach nur Lücken. Sie können auch Information enthalten. Vielleicht wurde eine Frage vergessen, vielleicht bewusst übersprungen, vielleicht technisch nicht erfasst.
Betonen Sie: Deshalb nicht reflexartig löschen oder ersetzen. Erst sichtbar machen, dann entscheiden.
Aktion vorbereiten: Im Notebook zählen wir gleich fehlende Werte pro Spalte.
Übergang: Wir wechseln in Notebook 1 und prüfen Missing Values sowie Kategorien.

---

## Slide 15

Ziel: Missingness und Kategorien sichtbar machen.
Sagen Sie: Führen Sie die Zellen aus und schauen Sie besonders auf die Sortierung der Missing Values und auf die `value_counts` der Kategorien.
Interaktion: Welche Kategorie scheint eigentlich dieselbe Bedeutung zu haben, ist aber unterschiedlich geschrieben?
Falls Zeit: Lassen Sie eine Person nennen, welche Bereinigung sie für `department` vorschlagen würde.
Übergang: Aus der Diagnose wird jetzt ein Bereinigungsschritt.

---

## Slide 16

Ziel: Kategorienbereinigung erklären.
Sagen Sie: Für Menschen ist klar, dass `Sales`, `sales` und manchmal auch eine Variante mit Leerzeichen dieselbe Kategorie meinen können. Für pandas sind das zunächst unterschiedliche Texte.
Betonen Sie: Kategorienbereinigung ist nicht nur Kosmetik. Später können Kategorien zu Modellvariablen werden.
Code erklären: `astype('string')`, `str.strip()` und `str.lower()` sind einfache Standardisierungen.
Übergang: Neben Kategorien müssen wir auch prüfen, ob Fälle doppelt vorhanden sind.

---

## Slide 17

Ziel: Dubletten als Analyseproblem erklären.
Sagen Sie: Wenn eine Person doppelt im Datensatz steht, zählt sie doppelt. Das kann Mittelwerte und Modelle verzerren.
Wichtig: In echten Projekten löscht man Dubletten nicht immer automatisch. Man prüft, welcher Eintrag korrekt ist. In dieser Übung behalten wir den ersten Eintrag, um den Workflow zu zeigen.
Übergang: Jetzt setzen wir Kategorienbereinigung und Dublettenprüfung im Notebook um.

---

## Slide 18

Ziel: Bereinigungsschritte im Notebook umsetzen.
Aktion: Studierende erstellen `clean = df.copy()`, bereinigen Kategorien und prüfen Dubletten.
Sagen Sie: Achten Sie darauf, dass wir den Rohdatensatz nicht überschreiben. Die Kopie `clean` dokumentiert unsere Bereinigungsschritte.
Frage: Warum ist eine Kopie sinnvoll?
Erwartete Antwort: Rohdaten bleiben reproduzierbar; Bereinigung ist nachvollziehbar.
Übergang: Nach Textkategorien prüfen wir numerische Wertebereiche.

---

## Slide 19

Ziel: plausible Wertebereiche einführen.
Sagen Sie: Ein Wert kann technisch vorhanden sein und trotzdem inhaltlich falsch sein. Negative Schlafdauer ist ein offensichtliches Beispiel. Bei Skalen von 1 bis 5 sind Werte außerhalb dieses Bereichs ebenfalls unplausibel.
Interaktion: Welche Regeln sind eindeutig? Welche müssten wir diskutieren?
Betonen Sie: Regeln sind Teil der Datenentscheidung und sollten dokumentiert werden.
Übergang: Im Notebook setzen wir Werte außerhalb gültiger Bereiche auf fehlend.

---

## Slide 20

Ziel: ungültige Werte markieren.
Sagen Sie: Wir löschen nicht blind ganze Personen. Wir markieren zuerst gezielt die problematischen Werte als fehlend. Dadurch bleibt sichtbar, dass hier ein Datenproblem vorlag.
Aktion: Studierende führen die Regeln aus und prüfen anschließend erneut die Missingness.
Hinweis: Wenn jemand ein anderes Ergebnis bekommt, zuerst prüfen, ob die vorherigen Zellen in Reihenfolge ausgeführt wurden.
Übergang: Sobald ungültige Werte als fehlend markiert sind, müssen wir entscheiden, wie wir mit Missing Values umgehen.

---

## Slide 21

Ziel: Strategien für fehlende Werte erklären.
Sagen Sie: Es gibt mehrere Möglichkeiten: löschen, ersetzen oder fehlend bewusst als Information behandeln. Für diese Übung verwenden wir Median-Imputation, weil sie einfach und robust ist.
Wichtig: Median-Imputation ist nicht automatisch die beste Lösung. Sie ist heute eine transparente Demo-Entscheidung.
Kurze Rückbindung: Genau solche Entscheidungen sollten später in einer Analyse dokumentiert werden.
Übergang: Wir wenden die Strategie im Notebook an und speichern den bereinigten Datensatz.

---

## Slide 22

Ziel: bereinigte Daten erzeugen und speichern.
Aktion: Studierende führen die Imputation durch und speichern `lecture_05_employee_survey_cleaned.csv`.
Sagen Sie: Das Speichern ist wichtig, weil Notebook 2 auf diesem bereinigten Stand aufbaut. Wir wollen nicht jedes Mal alle Rohdaten-Schritte wiederholen müssen.
Kontrollcheck: `clean.isna().sum().sum()` sollte 0 ergeben.
Übergang: Aus dem bereinigten Datensatz erzeugen wir jetzt neue, inhaltlich nützliche Variablen.

---

## Slide 23

Ziel: Feature Engineering niedrigschwellig erklären.
Sagen Sie: Feature Engineering heißt: Wir erzeugen Variablen, die für unsere Frage besser nutzbar sind als einzelne Rohspalten. Das kann sehr einfach sein, zum Beispiel ein Mittelwert aus zwei Items.
Betonen Sie: Ein Feature ist nicht nur ein technisches Produkt, sondern eine inhaltliche Entscheidung.
Beispiel: `workload_mean` ist verständlicher als zwei getrennte Workload-Items, wenn beide dasselbe Konstrukt messen.
Übergang: Diese Schritte machen wir in Notebook 2.

---

## Slide 24

Ziel: Wechsel zu Notebook 2.
Sagen Sie: Öffnen Sie Notebook 2. Wenn Notebook 1 erfolgreich gelaufen ist, wird die bereinigte CSV geladen. Falls nicht, gibt es eine Referenzdatei, damit alle weiterarbeiten können.
Aktion: Skalenmittelwerte berechnen und `overload_index` erzeugen.
Frage: Welche der neuen Variablen wirkt inhaltlich am plausibelsten? Welche wäre eher diskutierbar?
Übergang: Danach beschreiben wir den bereinigten Datensatz.

---

## Slide 25

Ziel: Summary Statistics nach der Bereinigung einordnen.
Sagen Sie: Jetzt sind deskriptive Statistiken aussagekräftiger, weil die groben Datenprobleme behandelt wurden.
Betonen Sie: Summary Statistics sind noch keine Kausalerklärung. Sie beschreiben Verteilungen und Muster.
Nennen Sie Beispiele: Mittelwert, Standardabweichung, Min, Max, Gruppenmittelwerte.
Übergang: Im Notebook berechnen wir genau diese Kennzahlen.

---

## Slide 26

Ziel: erste Deskription im Notebook.
Aktion: Studierende führen `describe()` und `groupby()` aus.
Sagen Sie: Achten Sie darauf, wie sich die Perspektive ändert. Erst haben wir Daten geprüft, jetzt beschreiben wir Daten.
Interaktion: Welche Gruppe hat im Beispiel den höchsten Mittelwert bei Zufriedenheit? Was dürfen wir daraus noch nicht schließen?
Erwartung: Keine kausale Aussage.
Übergang: Jetzt knüpfen wir wieder an die Regression an: Für Modelle brauchen wir Y und X.

---

## Slide 27

Ziel: Brücke von Data Handling zu Modellierung.
Sagen Sie: In Lecture 4 haben wir mit Y und X gearbeitet. Heute sehen wir, wie diese Objekte praktisch in pandas entstehen.
Y ist die Zielvariable. X ist eine Tabelle aus Prädiktoren. Jede Zeile in X muss zur gleichen Person gehören wie der entsprechende Wert in Y.
Wichtig: IDs bleiben zur Verwaltung erhalten, aber normalerweise nicht als Prädiktoren.
Übergang: Kategoriale Variablen müssen vor der Modellierung noch numerisch vorbereitet werden.

---

## Slide 28

Ziel: Dummy-Codierung erklären.
Sagen Sie: Viele Modelle können mit Textkategorien nicht direkt rechnen. `department` als Text muss daher in 0/1-Spalten übersetzt werden.
Beispiel: Eine Dummy-Spalte zeigt, ob eine Person zu einer bestimmten Kategorie gehört.
Betonen Sie: Auch diese Codierung ist Data Handling und Modellvorbereitung, nicht nur technischer Formalismus.
Übergang: Im Notebook bauen wir nun die Feature-Matrix X.

---

## Slide 29

Ziel: Y und X praktisch erzeugen.
Aktion: Studierende definieren `y`, `X_num`, `X_cat` und `X`.
Sagen Sie: Prüfen Sie die Dimensionen. `y` hat eine Spalte bzw. einen Vektor, `X` hat mehrere Prädiktorspalten.
Kontrollfrage: Warum darf `satisfaction` nicht in X landen, wenn `satisfaction` Y ist?
Übergang: Daraus folgt eine allgemeine Regel: Nicht alles, was im Datensatz steht, gehört in ein Modell.

---

## Slide 30

Ziel: Modellierungsentscheidungen vorbereiten.
Sagen Sie: Data Handling schützt auch vor schlechten Modellentscheidungen. IDs, Zielvariable oder Zukunftsinformationen dürfen nicht einfach als Prädiktoren genutzt werden.
Interaktion: Welche Spalten würden Sie aus X ausschließen? Warum?
Beispiel geben: `participant_id` identifiziert Personen, erklärt aber nicht sinnvoll Zufriedenheit.
Übergang: Optional zeigen wir kurz, wie nah wir damit schon an einem Modell sind.

---

## Slide 31

Ziel: Übergang zur Modellierung zeigen, ohne den Fokus zu verschieben.
Sagen Sie: Dieser Schritt ist optional und nicht die eigentliche Modellierungslecture. Er zeigt nur: Wenn Y und X sauber vorbereitet sind, kann ein Modell technisch sehr schnell berechnet werden.
Betonen Sie: Die Interpretation wäre ein eigener Schritt. Heute geht es um die Datenvorbereitung.
Aktion: Bei Zeit den Mini-Modelltest ausführen lassen; sonst nur zeigen.
Übergang: Zum Abschluss fassen wir die Data-Handling-Checkliste zusammen.

---

## Slide 32

Ziel: Workflow als Checkliste sichern.
Sagen Sie: Diese Checkliste ist das wichtigste Arbeitswerkzeug der Sitzung. Sie können sie für fast jeden neuen Datensatz verwenden.
Gehen Sie die Fragen zügig durch. Betonen Sie: Ein sauberer Workflow ist wichtiger als ein einzelner perfekter Befehl.
Frage an die Gruppe: Welche Frage aus der Checkliste würden Sie in Zukunft als Erstes stellen?
Übergang: Zum Abschluss kommt die Hausaufgabe.

---

## Slide 33

Ziel: Hausaufgabe erklären.
Sagen Sie: Die Hausaufgabe ist eine Wiederholung des heutigen Workflows. Sie arbeiten den Prozess einmal selbstständig durch und dokumentieren kurz, welche Entscheidungen Sie getroffen haben.
Betonen Sie: Es geht nicht um perfekte Syntax, sondern um nachvollziehbare Datenentscheidungen.
Hinweis: Wer nicht fertig wird, soll zumindest den Data Audit und die Reflexionsfragen bearbeiten.
Abschluss: Nächstes Mal können wir auf dieser Grundlage weitere Analysen aufbauen.

---

## Qualitätsnotiz für die Durchführung

Diese Sitzung soll nicht als Python-Sprachkurs wirken. Die Codebeispiele sind bewusst kurz und wiederholbar. Im Mittelpunkt stehen:

- die Orientierung in VS Code und im geöffneten Kursordner
- die Anwendung nachvollziehbarer Data-Handling-Regeln
- die Dokumentation von Bereinigungsentscheidungen
- die Vorbereitung von `Y` und `X` für spätere Modellierung

Wenn Studierende technische Fragen stellen, zuerst prüfen:

1. Ist der richtige Ordner geöffnet?
2. Ist der richtige Kernel aktiv?
3. Liegt die CSV-Datei im selben Ordner?
4. Wird die Fehlermeldung durch Dateiort, Kernel oder Syntax verursacht?

Danach zum fachlichen roten Faden zurückkehren: Welche Regel wenden wir auf welches Datenproblem an?
