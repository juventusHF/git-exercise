# Übung

## Start in einem neuen Projekt

### 1. Clone das Repository

Um an einem Projekt zu arbeiten muss eine lokale Kopie des Remote Repository angelegt werden.  
Kommando: `git clone <URL>`  
Dokumentation: https://www.w3schools.com/git/git_glossary.asp?remote=github#clone  

Überprüfe die Commit History:  
Kommando: `git log`  
Dokumentation: https://www.w3schools.com/git/git_history.asp?remote=github  

Überprüfe tracked files:  
Kommando `git status`  
Dokumentation: https://www.w3schools.com/git/git_staging_environment.asp?remote=github  

### 2. Eine Änderung vornehmen

#### Neuer Branch
Bei der Arbeit an einem Projekt mit mehreren Entwicklern soll nie direkt auf dem `main` Branch gearbeitet werden. Also muss lokal zuerst ein neuer Branch angelegt werden.  
Kommando: `git branch <branch-name>`  
Dokumentation: https://www.w3schools.com/git/git_branch.asp?remote=github  

Überprüfe die Liste aller lokalen Branches: `git branch`  

Wechsle auf den neuen Branch: `git checkout <branch-name>`  

Überprüfe History und Status: `git log` und `git status`  

#### Code anpassen
Nun kannst du Änderungen am Code vornehmen.  
Erstelle für diese Übung eine neue Markdown Datei mit deinem Namen und einer kurzen Beschreibung über dich.  
Überprüfe dann wieder den Status: `git status`  

Lasse die neue Datei von Git tracken.  
Kommando: `git add <file>`  
Dokumentation: https://www.w3schools.com/git/git_staging_environment.asp?remote=github  

Überprüfe dann wieder den Status: `git status`  

#### Änderungen committen
Als nächstes werden die Änderungen in einem oder mehreren Commits gebündelt. Alles was mit `git add` zur Staging Area hinzugefügt wurde ist Teil vom nächsten Commit.  
Kommando: `git commit -m "message"`  
Dokumentation: https://www.w3schools.com/git/git_commit.asp?remote=github  

Überprüfe History und Status: `git log` und `git status`  

#### Änderungen pushen
Damit die Commits für andere sichtbar sind, müssen die in das Remote Repository gepushed werden.  
Kommando: `git push origin <branch-name>`  
Dokumentation: https://www.w3schools.com/git/git_glossary.asp?remote=github#push  

#### Änderungen mergen
Nun kann auf Github ein Pull-Request erstellt werden. Beim Erstellen wird spezifiziert welcher Branch in welchen gemerged werden soll.  
Nun können andere Entwickler die geplanten Änderungen überprüfen und automatisierte Checks (CI) werden ausgeführt.  
Sobald alles OK ist kann der Pull-Request gemerged werden.  

### 3. Lokales Repository aktualisieren
Nachdem dein Pull-Request gemerged wurde, kannst du und auch alle anderen Entwickler die Änderungen herunterladen.  

Wechsle dazu zuerst zurück auf den main Branch: `git checkout main`  

Überprüfe History und Status: `git log` und `git status`  

#### Eingehende Änderungen überprüfen
Bevor du dein lokales Repository aktualisierts, kannst du die neuen Committs überprüfen.  
Mit git fetch werden Metadaten aktualisiert, aber noch keine Änderungen heruntergeladen.  
Kommando: `git fetch origin`  
Dokumentation: https://www.w3schools.com/git/git_pull_from_remote.asp  

Überprüfe dann den Status: `git status` und die History auf dem Remote: `git log origin main`  

#### Änderungen herunterladen
Nun kann das lokale Repository aktualisiert werden.  
Kommando: `git pull`  
Dokumentation: https://www.w3schools.com/git/git_glossary.asp?remote=github#pull  

Überprüfe History und Status: `git log` und `git status`  

#### Aufräumen
Auf dem Remote sollte (je nach Einstellung) der Feature Branch nach dem Merge bereits gelöscht worden sein.  
Lösche auch lokal alle nicht verwendeten Branches.  

Überprüfe die Liste aller lokalen Branches: `git branch`  
Lösche den Branch: `git branch -d <branch-name>`  

## Zusammenarbeit im Team
Einer der Hauptgründe für den Einsatz eines VCS ist die vereinfachte Zusammenarbeit mit mehreren Entwicklern.  

#### Merge Conflicts verursachen
Manchmal gibt es Situationen in denen mehrere Entwickler Änderungen an der gleichen Datei vorgenommen haben.  
Beim Mergen kann es dann zu einem Merge Conflict kommen. Das heisst, Git weiss nicht wie es die Änderungen an einer Datei Zusammenführen soll und braucht manuelle Unterstützung.  

* Person A und Person B nehmen beide Änderungen in der gleichen Datei vor.
* Person A merged seine Änderungen auf main
* Person B merkt dass seine Änderungen einen Merge Conflict verursachen.

#### Merge Conflicts lösen
Es gibt verschiedene Möglichkeiten um einen Merge Conflict zu lösen.  

##### Verwendung von Tools
Es gibt verschiedene grafische Tools um Merge Conflicts einfacher zu lösen.  
* Eingebaut in Github/Gitlab/etc.
* Eingebaut in der IDE
* Extern

##### Lokaler Rebase
* Person B aktualisiert lokal den main Branch
* Führt dann den Rebase auf dem Feature Branch aus: `git rebase main`
* Löst die Merge conflicts
* Committet die Änderungen

##### Revert oder Reset
Je nach Situation kann es am einfachsten und schnellsten sein einen Teil der lokalen Änderungen zu verwerfen, den Branch ohne Konflikte zu rebasen und die Änderungen dann wieder einzufühen.  
Dazu gibt es zwei relevante Kommandos: `git revert` und `git reset`  
Dokumentation:  
https://www.w3schools.com/git/git_revert.asp?remote=github  
https://www.w3schools.com/git/git_reset.asp?remote=github  

#### Merge Conflicts vermeiden
* Kommunikation
* Kurzlebige Branches
* Feature Branches immer wieder aktualisieren mit `git merge` oder `git rebase`

## Oh shit

https://ohshitgit.com/
