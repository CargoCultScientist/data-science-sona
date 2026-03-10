# Setup-Handout - Arbeitsumgebung für den Kurs Data Science

> Status: Rohentwurf / Master-Version in Markdown
>
> Zweck: Dieses Dokument soll Ihnen helfen, die Arbeitsumgebung für den Kurs selbstständig einzurichten, auch wenn Sie in der ersten Sitzung nicht anwesend waren.

## 1. Ziel dieses Handouts

In diesem Kurs arbeiten wir mit einer professionellen, aber einsteigerfreundlichen Python-Umgebung.

Am Ende dieses Handouts sollten Sie:

- Anaconda installiert haben
- Visual Studio Code installiert haben
- die Python-Erweiterung in VS Code installiert haben
- die Jupyter-Erweiterung in VS Code installiert haben
- einen ersten Projektordner angelegt haben
- eine Python-Datei erfolgreich ausführen können
- eine Notebook-Zelle erfolgreich ausführen können
- `pandas` erfolgreich importieren können

**Wichtig:**

- Sie müssen heute noch nicht alles im Detail verstehen.
- Ziel ist zunächst eine **funktionierende Grundlage**.
- Wenn Sie eine `.py`-Datei, eine Notebook-Zelle und einen `pandas`-Import zum Laufen bringen, sind Sie für den Kursstart technisch gut vorbereitet.

---

## 2. Was Sie am Ende installiert haben sollten

### Pflicht

- [Anaconda Distribution](https://www.anaconda.com/download)
- [Visual Studio Code](https://code.visualstudio.com/download)
- [Python-Erweiterung für VS Code](https://marketplace.visualstudio.com/items?itemName=ms-python.python)
- [Jupyter-Erweiterung für VS Code](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter)

### Optional, aber empfohlen

- [GitHub-Konto](https://github.com/signup)
- [Git](https://git-scm.com/downloads.html)
- [GitHub Pull Requests and Issues für VS Code](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github)

### Optional

- [GitHub Copilot für VS Code](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot)
- [Codex - Übersicht](https://help.openai.com/en/articles/11369540/)
- [Claude Code - Übersicht](https://docs.anthropic.com/en/docs/claude-code/overview)

---

## 3. Offizielle Links

Bitte verwenden Sie nach Möglichkeit nur die offiziellen Installations- und Dokumentationsseiten.

### Anaconda

- [Anaconda Download](https://www.anaconda.com/download)
- [Anaconda Installationsanleitung](https://www.anaconda.com/docs/getting-started/anaconda/install)
- [Anaconda Überblick](https://www.anaconda.com/docs/getting-started/anaconda/main)
- [Anaconda Getting Started](https://www.anaconda.com/docs/getting-started)

### Visual Studio Code

- [VS Code Download](https://code.visualstudio.com/download)
- [VS Code auf Windows](https://code.visualstudio.com/docs/setup/windows)
- [VS Code auf macOS](https://code.visualstudio.com/docs/setup/mac)
- [VS Code Command Line Interface](https://code.visualstudio.com/docs/editor/command-line)

### Python und Jupyter in VS Code

- [Python in VS Code](https://code.visualstudio.com/docs/languages/python)
- [Python-Erweiterung im Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-python.python)
- [Jupyter-Erweiterung im Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter)
- [Python Interactive Window / Jupyter-Unterstützung](https://code.visualstudio.com/docs/python/jupyter-support-py)

### Git und GitHub

- [GitHub-Konto erstellen](https://docs.github.com/articles/signing-up-for-a-new-github-account)
- [GitHub Einstieg](https://docs.github.com/en/get-started/onboarding/getting-started-with-your-github-account)
- [Git Download](https://git-scm.com/downloads.html)
- [Git für Windows](https://git-scm.com/install/windows.html)
- [Git für macOS](https://git-scm.com/install/mac.html)
- [Git für Linux](https://git-scm.com/install/linux)

### Optionale KI-Tools

- [GitHub Copilot im Marketplace](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot)
- [Codex - Übersicht](https://help.openai.com/en/articles/11369540/)
- [Codex - Produktseite](https://openai.com/index/codex-now-generally-available/)
- [Claude Code - Übersicht](https://docs.anthropic.com/en/docs/claude-code/overview)
- [Claude Code - Setup](https://docs.anthropic.com/en/docs/claude-code/setup)

---

## 4. Welche Rolle spielen diese Werkzeuge?

### Python

Python ist die Programmiersprache, mit der wir im Kurs arbeiten.

### Anaconda

Anaconda bündelt mehrere Dinge an einem Ort:

- Python
- den Paket- und Umgebungsmanager `conda`
- eine große Zahl häufig genutzter Pakete für Data Science
- einen einfachen Einstieg in Jupyter-Workflows

Für den Kurs ist das praktisch, weil Sie nicht alles einzeln installieren müssen.

### Conda

`conda` verwaltet Pakete und Python-Umgebungen. Das wird später wichtig, wenn wir mit zusätzlichen Bibliotheken arbeiten.

### VS Code

VS Code ist unsere Arbeitsumgebung. Dort schreiben, starten und organisieren wir Python-Dateien und Jupyter-Notebooks.

### Jupyter

Jupyter-Notebooks sind interaktive Dokumente, in denen sich Code in kleinen Zellen ausführen lässt. Das ist besonders hilfreich beim Lernen, Testen und Explorieren von Daten.

### Pandas

`pandas` ist eine zentrale Python-Bibliothek für tabellarische Daten.

### GitHub

GitHub ist für diesen Kurs zunächst optional. Es wird später wichtig für Versionierung, Austausch und professionelle Projektarbeit.

---

## 5. Hinweise vor dem Start

### Zeitbedarf

Planen Sie für die Ersteinrichtung etwa **30 bis 60 Minuten** ein.

Wenn etwas nicht sofort funktioniert, ist das normal. Die erste Installation kostet fast immer mehr Zeit als die spätere Nutzung.

### Betriebssysteme

Dieses Handout ist in erster Linie für **Windows 10/11** formuliert, weil dort erfahrungsgemäß die meisten Rückfragen auftreten.

Wenn Sie macOS oder Linux verwenden, können Sie das meiste trotzdem analog nachvollziehen. Wo nötig, finden Sie weiter unten kurze Hinweise.

### Administratorrechte

Auf manchen Geräten benötigen Sie Rechte, um Software zu installieren. Falls Ihr Gerät von einer Organisation verwaltet wird, kann es sein, dass Sie Unterstützung durch IT oder Administratorrechte brauchen.

### Wichtiger Hinweis zu Anaconda

Anaconda verteilt die aktuelle Distribution über die offizielle Download-Seite. Je nach Weg über die Seite kann es sein, dass Sie sich mit einer E-Mail-Adresse registrieren oder sich den Download-Link zusenden lassen müssen.

---

## 6. Schritt 1 - Anaconda installieren

### Ziel dieses Schritts

Nach diesem Schritt sollte Anaconda installiert sein und `python` sowie `conda` sollten funktionieren.

### Was Sie tun

1. Öffnen Sie die offizielle Download-Seite:
   - [Anaconda Download](https://www.anaconda.com/download)
2. Laden Sie die passende Version für Ihr Betriebssystem herunter.
3. Führen Sie den Installer aus.

### Empfehlung für Windows

Wenn Sie Windows verwenden, ist in der Regel sinnvoll:

- **Just Me** wählen
- nicht als Administrator installieren, wenn das nicht nötig ist
- den vorgeschlagenen Installationspfad beibehalten
- die Option **Anaconda nicht manuell zum PATH hinzufügen**, wenn der Installer davon abrät
- die Option **als Standard-Python registrieren** aktiviert lassen, wenn Sie keine besondere Mehrfach-Python-Konfiguration haben

### Nach der Installation

Öffnen Sie eines der folgenden Programme:

- **Anaconda Prompt**
- **Anaconda Navigator**

Für die technischen Checks ist **Anaconda Prompt** am praktischsten.

### Funktionstest

Geben Sie im **Anaconda Prompt** nacheinander ein:

```bash
python --version
```

```bash
conda --version
```

### Erfolgskriterium

Beide Befehle geben eine Versionsnummer zurück.

### Screenshot-Platzhalter

- Screenshot 1: Anaconda Download-Seite
- Screenshot 2: Installer mit empfohlenen Optionen
- Screenshot 3: Erfolgreicher `python --version`- und `conda --version`-Check

### Typische Probleme

#### Problem: `conda` wird nicht erkannt

Versuchen Sie Folgendes:

- Schließen Sie den Installer vollständig.
- Öffnen Sie **Anaconda Prompt**, nicht nur ein beliebiges Terminal.
- Starten Sie den Rechner neu.
- Prüfen Sie die offizielle Installationsanleitung:
  - [Anaconda Installationsanleitung](https://www.anaconda.com/docs/getting-started/anaconda/install)

#### Problem: Installation schlägt fehl

Versuchen Sie Folgendes:

- Installieren Sie für **Just Me** statt für alle Benutzer
- Wählen Sie einen Ordner ohne Sonderzeichen
- deaktivieren Sie Sicherheitssoftware nur dann kurzzeitig, wenn Ihre lokale Richtlinie das erlaubt

### Hinweise für macOS

- Nutzen Sie die offizielle Anaconda-Installationsanleitung für macOS.
- Wenn Sie ein Intel-Mac-Gerät haben und Probleme mit aktuellen Installern auftreten, lesen Sie bitte die Hinweise in den offiziellen Anaconda-Dokumenten.

### Hinweise für Linux

- Folgen Sie der offiziellen Anaconda-Anleitung für Linux.
- Nach der Installation kann ein Terminal-Neustart nötig sein.

---

## 7. Schritt 2 - Visual Studio Code installieren

### Ziel dieses Schritts

Nach diesem Schritt sollte VS Code installiert und einmal gestartet sein.

### Was Sie tun

1. Öffnen Sie die offizielle Download-Seite:
   - [VS Code Download](https://code.visualstudio.com/download)
2. Laden Sie die passende Version für Ihr Betriebssystem herunter.
3. Installieren Sie VS Code **direkt über die offizielle Microsoft-Seite**.
4. Öffnen Sie VS Code nach der Installation mindestens einmal.

### Warum wir VS Code direkt installieren

Für den Kurs ist der direkte Installationsweg über Microsoft am robustesten.

So stellen wir sicher, dass:

- alle dieselbe offizielle Installationsquelle verwenden
- VS Code unabhängig von Anaconda zuverlässig startet
- Erweiterungen direkt in VS Code eingerichtet werden können

### Optionaler Weg über Anaconda Navigator

Wenn Anaconda Navigator VS Code korrekt erkennt, können Sie VS Code später auch **aus Navigator heraus starten**.

Das kann hilfreich sein, wenn Sie später gezielt mit Conda-Umgebungen arbeiten möchten.

Für die erste Sitzung ist das aber **nicht erforderlich**. Wichtig ist zunächst nur, dass VS Code installiert ist und zuverlässig geöffnet werden kann.

### Empfehlung für Windows

Wenn Sie Windows verwenden, ist meist der **User Installer** die unkomplizierteste Wahl.

### Erste Orientierung in VS Code

Beim ersten Start müssen Sie noch nicht alles verstehen. Für den Anfang reichen diese Bereiche:

- **Explorer** - zeigt Dateien und Ordner
- **Terminal** - dort laufen Befehle
- **Extensions** - dort installieren Sie Erweiterungen
- **Editor** - dort schreiben Sie Code

### Erfolgskriterium

VS Code startet ohne Fehlermeldung.

### Screenshot-Platzhalter

- Screenshot 4: VS Code Download-Seite
- Screenshot 5: Geöffnetes VS Code-Fenster
- Optionaler Screenshot: VS Code als App in Anaconda Navigator

### Typische Probleme

#### Problem: VS Code startet nicht richtig

Versuchen Sie Folgendes:

- Starten Sie den Rechner neu.
- Installieren Sie VS Code erneut von der offiziellen Download-Seite.
- Prüfen Sie die Systemanforderungen auf der offiziellen VS Code-Seite.

---

## 8. Schritt 3 - Python- und Jupyter-Erweiterungen installieren

### Ziel dieses Schritts

Nach diesem Schritt soll VS Code für Python-Dateien und Jupyter-Notebooks einsatzbereit sein.

### Was Sie tun

1. Öffnen Sie VS Code.
2. Klicken Sie links auf **Extensions**.
3. Suchen Sie nacheinander nach den folgenden Erweiterungen.

### Pflicht-Erweiterungen

#### Python

- Name: **Python**
- Publisher: **Microsoft**
- Link: [Python-Erweiterung für VS Code](https://marketplace.visualstudio.com/items?itemName=ms-python.python)

#### Jupyter

- Name: **Jupyter**
- Publisher: **Microsoft**
- Link: [Jupyter-Erweiterung für VS Code](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter)

### Optional, aber empfohlen

#### GitHub Pull Requests and Issues

- Publisher: **GitHub**
- Link: [GitHub Pull Requests and Issues](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github)

### Optional

#### GitHub Copilot

- Publisher: **GitHub**
- Link: [GitHub Copilot](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot)

### Wichtige Hinweise

- Installieren Sie zunächst nur die **Pflicht-Erweiterungen**.
- Wenn Sie zusätzlich KI-Werkzeuge ausprobieren möchten, installieren Sie am Anfang am besten **nur eines**.
- KI-Tools sind in diesem Kurs **optional**.
- Sie können beim Erklären, Formulieren und Fehlersuchen helfen, ersetzen aber nicht Ihr eigenes Verständnis.

### Erfolgskriterium

Die Erweiterungen **Python** und **Jupyter** sind installiert und aktiviert.

### Screenshot-Platzhalter

- Screenshot 6: Extensions-Ansicht in VS Code
- Screenshot 7: Installierte Python-Erweiterung
- Screenshot 8: Installierte Jupyter-Erweiterung

### Typische Probleme

#### Problem: Erweiterung lässt sich nicht installieren

Versuchen Sie Folgendes:

- Prüfen Sie Ihre Internetverbindung.
- Starten Sie VS Code neu.
- Installieren Sie die Erweiterung direkt über den Marketplace-Link.

#### Problem: Erweiterung ist installiert, aber nicht aktiv

Versuchen Sie Folgendes:

- Öffnen Sie eine `.py`- oder `.ipynb`-Datei.
- Starten Sie VS Code neu.
- Prüfen Sie, ob die Erweiterung deaktiviert wurde.

---

## 9. Schritt 4 - Ersten Projektordner anlegen

### Ziel dieses Schritts

Nach diesem Schritt haben Sie einen Arbeitsordner für den Kurs erstellt und in VS Code geöffnet.

### Empfehlung

Legen Sie auf Ihrem Rechner einen neuen Ordner an, zum Beispiel:

```text
business-psychology-python
```

### Was Sie tun

1. Erstellen Sie auf Ihrem Rechner den Ordner.
2. Öffnen Sie in VS Code:
   - **File** → **Open Folder**
3. Wählen Sie Ihren neuen Ordner aus.

### Warum das wichtig ist

Wir arbeiten im Kurs projektbasiert. Ein eigener Ordner hilft dabei,

- Dateien übersichtlich zu halten
- Skripte und Notebooks an einem Ort zu sammeln
- später GitHub und Versionierung sauber einzubinden

### Erfolgskriterium

Der Ordner ist im Explorer von VS Code sichtbar.

### Screenshot-Platzhalter

- Screenshot 9: Neuer Projektordner im Explorer von VS Code

---

## 10. Schritt 5 - Erste Python-Datei ausführen

### Ziel dieses Schritts

Nach diesem Schritt sollte eine einfache Python-Datei erfolgreich laufen.

### Was Sie tun

1. Erstellen Sie im Projektordner eine neue Datei mit dem Namen:

```text
hello.py
```

2. Fügen Sie diesen Code ein:

```python
print("Hello, business psychology")
```

3. Speichern Sie die Datei.
4. Führen Sie die Datei aus.

### So können Sie die Datei ausführen

Sie haben mehrere Möglichkeiten:

- den **Run Python File**-Button in VS Code
- Rechtsklick in die Datei und **Run Python File in Terminal**
- Terminal und manueller Aufruf

### Falls VS Code nach einem Interpreter fragt

Wählen Sie den Python-Interpreter aus Ihrer Anaconda-Installation.

### Optionaler Terminal-Aufruf

Wenn Sie den Aufruf im Terminal machen möchten:

```bash
python hello.py
```

### Erfolgskriterium

Im Terminal erscheint:

```text
Hello, business psychology
```

### Screenshot-Platzhalter

- Screenshot 10: `hello.py` im Editor
- Screenshot 11: Erfolgreiche Ausgabe im Terminal

### Typische Probleme

#### Problem: VS Code findet keinen Interpreter

Versuchen Sie Folgendes:

1. Öffnen Sie die Command Palette:
   - `Ctrl+Shift+P` unter Windows/Linux
   - `Cmd+Shift+P` unter macOS
2. Suchen Sie nach:

```text
Python: Select Interpreter
```

3. Wählen Sie den Interpreter aus, der zu Anaconda gehört.

#### Problem: Die Datei läuft nicht

Versuchen Sie Folgendes:

- Prüfen Sie, ob die Datei als `.py` gespeichert wurde.
- Prüfen Sie, ob der Code exakt übernommen wurde.
- Starten Sie VS Code neu.

---

## 11. Schritt 6 - Pandas testen

### Ziel dieses Schritts

Nach diesem Schritt sollte `pandas` in Ihrer Python-Umgebung importiert werden können.

### Was Sie tun

Ersetzen Sie den Inhalt von `hello.py` durch:

```python
import pandas as pd

print(pd.__version__)
```

Führen Sie die Datei erneut aus.

### Erfolgskriterium

Im Terminal erscheint eine Versionsnummer von `pandas`.

### Screenshot-Platzhalter

- Screenshot 12: Erfolgreicher `pandas`-Import

### Typische Probleme

#### Problem: `ModuleNotFoundError: No module named 'pandas'`

Wahrscheinliche Ursache:

- VS Code verwendet nicht den Interpreter Ihrer Anaconda-Umgebung.

Versuchen Sie Folgendes:

1. `Python: Select Interpreter` erneut aufrufen
2. den Anaconda-Interpreter wählen
3. Datei erneut starten

---

## 12. Schritt 7 - Erstes Notebook starten

### Ziel dieses Schritts

Nach diesem Schritt sollte eine `.ipynb`-Datei in VS Code laufen.

### Was Sie tun

1. Erstellen Sie eine neue Datei mit dem Namen:

```text
first_notebook.ipynb
```

2. Öffnen Sie die Datei in VS Code.
3. Wählen Sie oben rechts einen Python-Kernel aus.
4. Erstellen Sie eine erste Code-Zelle.

### Erste Test-Zelle

```python
2 + 2
```

Führen Sie die Zelle aus.

### Zweite Test-Zelle

```python
print("Notebook works")
```

### Erfolgskriterium

Die Zellen laufen ohne Fehlermeldung und zeigen ein Ergebnis an.

### Screenshot-Platzhalter

- Screenshot 13: Geöffnetes Notebook in VS Code
- Screenshot 14: Erfolgreich ausgeführte erste Notebook-Zelle

### Typische Probleme

#### Problem: Notebook startet nicht

Versuchen Sie Folgendes:

- Prüfen Sie, ob die Jupyter-Erweiterung installiert ist.
- Prüfen Sie, ob ein Python-Kernel ausgewählt ist.
- Starten Sie VS Code neu.
- Wählen Sie den Kernel erneut.

#### Problem: Kernel wird nicht angezeigt

Versuchen Sie Folgendes:

- Öffnen Sie zuerst eine normale Python-Datei.
- Wählen Sie dort den richtigen Interpreter.
- Öffnen Sie danach das Notebook erneut.

---

## 13. Mini-Übung nach dem Setup

### Ziel dieser Übung

Das Setup soll nicht nur formal abgeschlossen sein, sondern direkt mit einem ersten kleinen Data-Handling-Beispiel verbunden werden.

### Code für die Mini-Übung

Fügen Sie in Ihr Notebook oder in eine neue Datei ein:

```python
import pandas as pd

df = pd.DataFrame({
    "participant": [1, 2, 3],
    "stress": [2, 4, 3],
    "motivation": [4, 5, 3]
})

print(df)
print(df["stress"].mean())
```

### Was Sie sehen sollten

- eine kleine Tabelle
- den Mittelwert der Spalte `stress`

### Erfolgskriterium

Der Code läuft ohne Fehlermeldung.

### Screenshot-Platzhalter

- Screenshot 15: Erfolgreiche Mini-Übung mit Tabelle und Mittelwert

---

## 14. Optional - GitHub einrichten

> Dieser Abschnitt ist optional für den ersten Kurstag.
>
> Wenn bei Ihnen Anaconda, VS Code, Python, Jupyter und `pandas` funktionieren, ist das für den Start völlig ausreichend.

### Ziel dieses Schritts

GitHub soll als Werkzeug für spätere Versionierung und Zusammenarbeit vorbereitet werden.

### Schritt 1 - GitHub-Konto anlegen

Wenn Sie noch kein GitHub-Konto haben:

- [GitHub-Konto erstellen](https://github.com/signup)
- [GitHub Doku zum Anlegen eines Kontos](https://docs.github.com/articles/signing-up-for-a-new-github-account)

### Schritt 2 - E-Mail bestätigen

Bestätigen Sie Ihre E-Mail-Adresse, wenn GitHub Sie dazu auffordert.

### Schritt 3 - Optional Git installieren

Wenn Sie mit Git später auch lokal im Terminal arbeiten möchten, installieren Sie zusätzlich Git:

- [Git Download](https://git-scm.com/downloads.html)
- [Git für Windows](https://git-scm.com/install/windows.html)
- [Git für macOS](https://git-scm.com/install/mac.html)
- [Git für Linux](https://git-scm.com/install/linux)

### Schritt 4 - Optional GitHub-Erweiterung in VS Code

Installieren Sie optional:

- [GitHub Pull Requests and Issues](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github)

### Wichtiger Hinweis

GitHub wird im Kurs wichtig werden, aber **nicht** als Voraussetzung dafür, dass heute Ihr erster Python-Code läuft.

---

## 15. Optional - KI-gestützte Assistenten

> Auch dieser Abschnitt ist optional.

Wenn Sie zusätzlich mit KI-gestützten Coding-Tools arbeiten möchten, können Sie optional **einen** der folgenden Assistenten ausprobieren:

- [GitHub Copilot im Marketplace](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot)
- [Codex - Übersicht](https://help.openai.com/en/articles/11369540/)
- [Codex - Produktseite](https://openai.com/index/codex-now-generally-available/)
- [Claude Code - Übersicht](https://docs.anthropic.com/en/docs/claude-code/overview)
- [Claude Code - Setup](https://docs.anthropic.com/en/docs/claude-code/setup)

### Empfehlung für den Anfang

- Installieren Sie am ersten Tag höchstens **einen** KI-Assistenten.
- Nutzen Sie ihn zum Erklären, Nachfragen und Überprüfen.
- Verlassen Sie sich nicht blind auf automatisch erzeugten Code.

### Welche Option ist für den Einstieg am einfachsten?

#### GitHub Copilot

GitHub Copilot ist für viele Studierende der niedrigschwelligste Einstieg, weil es sich direkt in VS Code integrieren lässt.

#### Codex

Codex ist ein stärker agentisch ausgerichtetes Coding-Tool. Es kann lokal in Tools wie Terminal oder IDE verwendet werden und eignet sich eher als Erweiterung, wenn Ihre Grundumgebung bereits stabil läuft.

#### Claude Code

Claude Code ist ebenfalls ein agentisches Tool, arbeitet aber stärker terminalbasiert. Für viele Studierende ist es deshalb eher eine spätere Zusatzoption als Teil des ersten Setups.

### Gute Einsatzmöglichkeiten

- „Erkläre mir diesen Code in einfachen Worten.“
- „Wo ist der Fehler in diesem kleinen Skript?“
- „Wie kann ich diese Variable verständlicher benennen?“

### Schlechte Einsatzmöglichkeiten

- ganze Aufgaben ungeprüft generieren lassen
- Code übernehmen, den Sie nicht verstanden haben
- sich vollständig auf den Assistenten verlassen

### Wichtiger Hinweis

Für den Kursstart sind diese Tools **nicht erforderlich**.

Wichtiger ist zunächst, dass Ihre Python-, Jupyter- und Pandas-Umgebung funktioniert.

---

## 16. Troubleshooting - typische Probleme und erste Lösungen

### Problem 1 - `python` funktioniert im normalen Terminal nicht

**Wahrscheinliche Ursache:**

- Sie verwenden nicht den Interpreter aus Ihrer Anaconda-Installation.

**Versuchen Sie Folgendes:**

- Testen Sie zuerst im **Anaconda Prompt**.
- Öffnen Sie in VS Code `Python: Select Interpreter`.
- Wählen Sie den Anaconda-Interpreter.

### Problem 2 - `conda` wird nicht erkannt

**Versuchen Sie Folgendes:**

- Öffnen Sie **Anaconda Prompt** statt PowerShell oder CMD.
- Starten Sie den Rechner neu.
- lesen Sie die offizielle Anleitung:
  - [Anaconda Installationsanleitung](https://www.anaconda.com/docs/getting-started/anaconda/install)

### Problem 3 - Notebook-Zellen laufen nicht

**Versuchen Sie Folgendes:**

- Prüfen Sie, ob die **Jupyter-Erweiterung** installiert ist.
- Prüfen Sie, ob oben rechts ein Kernel ausgewählt ist.
- Starten Sie VS Code neu.
- Wechseln Sie den Interpreter und öffnen Sie das Notebook erneut.

### Problem 4 - `pandas` lässt sich nicht importieren

**Versuchen Sie Folgendes:**

- Prüfen Sie den gewählten Interpreter.
- Führen Sie das Skript in der Anaconda-Umgebung aus.
- testen Sie den Import noch einmal:

```python
import pandas as pd
print(pd.__version__)
```

### Problem 5 - Sie sind unsicher, ob Ihr Setup „gut genug“ ist

Für die erste Sitzung reicht Folgendes vollkommen aus:

- VS Code öffnet sich
- eine `.py`-Datei läuft
- ein Notebook läuft
- `pandas` importiert erfolgreich

Das ist ein guter Start.

---

## 17. Abschluss-Checkliste

Bitte prüfen Sie, ob Sie die folgenden Punkte abhaken können:

- [ ] Anaconda ist installiert
- [ ] VS Code ist installiert
- [ ] Python-Erweiterung ist installiert
- [ ] Jupyter-Erweiterung ist installiert
- [ ] der Projektordner ist angelegt
- [ ] `hello.py` läuft
- [ ] `pandas` lässt sich importieren
- [ ] `first_notebook.ipynb` läuft
- [ ] die Mini-Übung läuft

Wenn Sie diese Punkte abhaken können, ist Ihre Arbeitsumgebung für den Kursstart einsatzbereit.

---

## 18. Aufgabe bis zur nächsten Sitzung

Bitte testen Sie Ihr Setup **noch einmal selbstständig**, ohne direkt dieses Handout Zeile für Zeile nachzuvollziehen.

### Wiederholen Sie kurz:

1. VS Code öffnen
2. den Projektordner öffnen
3. `hello.py` starten
4. das Notebook öffnen
5. eine Zelle ausführen
6. `pandas` importieren

### Dokumentieren Sie kurz für sich selbst:

- Was hat problemlos funktioniert?
- Was war schwierig?
- Was ist noch unklar?

### Optional

Machen Sie einen Screenshot Ihrer funktionierenden Arbeitsumgebung.

---

## 19. Bitte mit in den Kurs bringen

Zum nächsten Termin bringen Sie bitte mit:

- Ihren Laptop
- Ihr Ladegerät
- Ihre installierte Arbeitsumgebung
- Ihren Projektordner

Wenn etwas noch nicht funktioniert, kommen Sie trotzdem in die Sitzung. Dann können wir gezielt an den offenen Punkten arbeiten.

---

## 20. Kurzfassung - minimaler Erfolg für Sitzung 1

Wenn Sie wenig Zeit haben, konzentrieren Sie sich zuerst auf diese Minimalziele:

1. Anaconda installieren
2. VS Code installieren
3. Python- und Jupyter-Erweiterung installieren
4. `hello.py` erfolgreich ausführen
5. `import pandas as pd` erfolgreich testen
6. eine Notebook-Zelle erfolgreich ausführen

Wenn diese sechs Punkte funktionieren, sind Sie bereit für den Kursstart.
