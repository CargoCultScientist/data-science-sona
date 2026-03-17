# Übungsblatt - Vorlesung 2

**Thema:** VS Code, Jupyter, Variablen, Vektoren, Matrizen und erste Schritte mit pandas  
**Kurs:** Data Science, HS Fresenius

## Ziel des Übungsblatts

Mit diesem Übungsblatt wiederholen Sie die wichtigsten Schritte aus der zweiten Vorlesung selbstständig.

Am Ende sollten Sie:

- Ihre Python-Umgebung im Notebook prüfen können
- den Unterschied zwischen Interpreter, Kernel und Conda-Umgebung praktisch wiedererkennen
- Markdown- und Code-Zellen in Jupyter sicher verwenden können
- einfache Variablen und Datentypen anlegen und mit `type()` prüfen können
- mit kleinen Vektoren und Matrizen arbeiten können
- einen einfachen `pandas`-DataFrame erstellen und auswerten können

## So arbeiten Sie mit dem Übungsblatt

- Öffnen Sie Ihr Notebook aus der Vorlesung **oder** legen Sie ein neues Jupyter-Notebook an.
- Bearbeiten Sie die Aufgaben in der vorgegebenen Reihenfolge.
- Wenn etwas nicht funktioniert, notieren Sie **die genaue Fehlermeldung**.
- Arbeiten Sie möglichst in Ihrer Kursumgebung, nicht in einer zufälligen anderen Python-Umgebung.

---

## Aufgabe 0 - Dev Environment Check

Starten Sie Ihr Notebook und führen Sie folgende Zellen aus:

```python
import sys
import pandas as pd

print(sys.executable)
print(pd.__version__)
```

### Prüfen Sie anschließend kurz:

- Wird ein Python-Pfad aus Ihrer Kursumgebung angezeigt?
- Lässt sich `pandas` ohne Fehlermeldung importieren?

---

## Aufgabe 1 - Die wichtigsten Begriffe kurz wiederholen

Beantworten Sie in **einer Markdown-Zelle** kurz die folgenden Fragen:

1. Was ist eine **Conda-Umgebung**?
2. Was ist ein **Python-Interpreter**?
3. Was ist ein **Kernel** in Jupyter?
4. Wofür nutzen wir **VS Code**?
5. Was ist der Unterschied zwischen einem **Python-Skript**, **Markdown** und einem **Jupyter-Notebook**?

> Ziel ist keine perfekte Definition, sondern eine verständliche eigene Erklärung in 1 bis 3 Sätzen pro Begriff.

---

## Aufgabe 2 - Markdown üben

Erstellen Sie eine neue Markdown-Zelle mit folgenden Elementen:

- einer Überschrift erster Ebene
- einer Überschrift zweiter Ebene
- einer Liste mit mindestens drei Punkten
- einem kurzen Satz, in dem das Wort **pandas** fett formatiert wird
- einem kurzen Satz, in dem das Wort *Kernel* kursiv formatiert wird

### Beispielstruktur

```markdown
# Meine Wiederholung
## Was ich heute verstanden habe
- Punkt 1
- Punkt 2
- Punkt 3

Heute habe ich mit **pandas** gearbeitet.
Ein *Kernel* führt Notebook-Zellen aus.
```

---

## Aufgabe 3 - Einfache Rechnungen

Legen Sie zwei Zahlenvariablen an und führen Sie mit ihnen mehrere Rechenoperationen durch.

### Mindestanforderung

```python
x = 12
y = 5
```

Berechnen und speichern Sie jeweils in einer neuen Variablen:

- Summe
- Differenz
- Produkt
- Quotient

Geben Sie die Ergebnisse anschließend aus.

### Zusatzfrage

Was ist der Datentyp Ihres Quotienten?

---

## Aufgabe 4 - Variablen und Datentypen

Legen Sie mindestens **vier Variablen unterschiedlicher Typen** an, zum Beispiel:

- eine Ganzzahl
- eine Fließkommazahl
- einen Text
- einen Wahrheitswert

Beispiel:

```python
age = 24
height = 1.72
name = "Lea"
ready = True
```

### Bearbeiten Sie dann folgende Schritte:

1. Geben Sie alle Variablen aus.
2. Prüfen Sie mit `type()` jeweils den Datentyp.
3. Schreiben Sie in einer Markdown-Zelle kurz auf, was die Typen `int`, `float`, `str` und `bool` bedeuten.

---

## Aufgabe 5 - Vektor und Matrix

Importieren Sie NumPy:

```python
import numpy as np
```

### Teil A - Vektor

Erstellen Sie einen Vektor mit mindestens vier Zahlen.

Beispiel:

```python
v = np.array([1, 3, 5, 7])
```

Prüfen Sie dann:

- `v`
- `v.shape`
- `v.mean()`

### Teil B - Matrix

Erstellen Sie eine 2x2-Matrix.

Beispiel:

```python
M = np.array([[1, 2], [3, 4]])
```

Prüfen Sie dann:

- `M`
- `M.shape`
- `M + 1`
- `M[1, 0]`

### Reflexionsfrage

Worin besteht für Sie der wichtigste Unterschied zwischen einem Vektor und einer Matrix?

---

## Aufgabe 6 - Erster DataFrame mit pandas

Erstellen Sie einen kleinen DataFrame mit mindestens fünf Zeilen und vier Spalten.

### Beispiel

```python
import pandas as pd

df = pd.DataFrame({
    "participant": [1, 2, 3, 4, 5],
    "stress": [2, 4, 3, 5, 4],
    "motivation": [4, 5, 3, 2, 4],
    "satisfaction": [3, 4, 4, 2, 5]
})
```

### Bearbeiten Sie dann mindestens folgende Schritte:

1. Lassen Sie sich den gesamten DataFrame anzeigen.
2. Prüfen Sie `df.shape`.
3. Prüfen Sie `df.columns`.
4. Berechnen Sie den Mittelwert von `stress`.
5. Berechnen Sie den Mittelwert von `motivation`.
6. Erzeugen Sie eine neue Spalte, zum Beispiel:

```python
df["balance"] = df["motivation"] - df["stress"]
```

7. Lassen Sie sich den DataFrame danach erneut anzeigen.

### Zusatzfrage

Welche Spalte hat in Ihrem Beispiel den höchsten Mittelwert?

---

## Aufgabe 7 - Kurze schriftliche Reflexion

Beantworten Sie am Ende in einer Markdown-Zelle kurz die folgenden Fragen:

1. Was war heute für Sie am einfachsten?
2. Was war noch unklar?
3. Wo hatten Sie technische Schwierigkeiten?
4. Welchen Unterschied verstehen Sie jetzt besser als vor der Sitzung?

---

## Mindestziel bis zur nächsten Vorlesung

Wenn Sie wenig Zeit haben, konzentrieren Sie sich mindestens auf diese Punkte:

- Notebook starten
- Dev Environment Check ausführen
- eine Markdown-Zelle schreiben
- Variablen und `type()` ausprobieren
- einen Vektor und eine Matrix anlegen
- einen kleinen DataFrame erzeugen

---

## Wenn etwas nicht funktioniert

Notieren Sie bitte möglichst genau:

- **welcher Schritt** nicht funktioniert hat
- **welche Fehlermeldung** angezeigt wurde
- ob das Problem in einer `.py`-Datei oder im Notebook aufgetreten ist
- ob Sie den richtigen Interpreter bzw. Kernel gewählt hatten

Diese Informationen helfen uns in der nächsten Sitzung deutlich mehr als nur die Aussage: „Es ging nicht.“
