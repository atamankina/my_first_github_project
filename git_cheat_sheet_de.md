[No sources were provided for this request. As a result, no citations are included in the response.]

Git-Spickzettel

GIT-GRUNDLAGEN

* `git init <directory>`: Erstellt ein leeres Git-Repository im angegebenen Verzeichnis. Ohne Argumente wird das aktuelle Verzeichnis als Git-Repository initialisiert.
* `git clone <repo>`: Klont das Repository, das sich unter `<repo>` befindet, auf den lokalen Rechner. Das Original-Repository kann sich auf dem lokalen Dateisystem oder auf einem Remote-Rechner über HTTP oder SSH befinden.
* `git config user.name <name>`: Definiert den Autorennamen, der für alle Commits im aktuellen Repository verwendet werden soll. Entwickler verwenden häufig das Flag `--global`, um Konfigurationsoptionen für den aktuellen Benutzer festzulegen.
* `git add <directory>`: Staged alle Änderungen im `<directory>` für den nächsten Commit. Ersetzen Sie `<directory>` durch `<file>`, um eine bestimmte Datei zu ändern.
* `git commit -m "<message>"`: Committet den gestageten Snapshot, aber anstatt einen Texteditor zu starten, wird `<message>` als Commit-Nachricht verwendet.
* `git status`: Listet auf, welche Dateien gestaged, ungestaged und ungetrackt sind.
* `git log`: Zeigt die gesamte Commit-Historie im Standardformat an. Für Anpassungen siehe zusätzliche Optionen.
* `git diff`: Zeigt ungestagete Änderungen zwischen Ihrem Index und Ihrem Arbeitsverzeichnis an.

ÄNDERUNGEN RÜCKGÄNGIG MACHEN

* `git commit -amend`: Ersetzt den letzten Commit durch die gestageten Änderungen und den letzten Commit zusammen. Verwenden Sie dies ohne gestagete Änderungen, um die Nachricht des letzten Commits zu bearbeiten.
* `git rebase <base>`: Rebasiert den aktuellen Branch auf `<base>`. `<base>` kann eine Commit-ID, ein Branch-Name, ein Tag oder eine relative Referenz zu HEAD sein.
* `git reflog`: Zeigt ein Protokoll der Änderungen am HEAD des lokalen Repositorys an. Fügen Sie das Flag `--relative-date` hinzu, um Datumsangaben anzuzeigen, oder `--all`, um alle Referenzen anzuzeigen.
* `git revert <commit>`: Erstellt einen neuen Commit, der alle in `<commit>` vorgenommenen Änderungen rückgängig macht, und wendet ihn dann auf den aktuellen Branch an.
* `git reset <file>`: Entfernt `<file>` aus dem Staging-Bereich, lässt aber das Arbeitsverzeichnis unverändert. Dies entstaget eine Datei, ohne Änderungen zu überschreiben.
* `git clean -n`: Zeigt an, welche Dateien aus dem Arbeitsverzeichnis entfernt würden. Verwenden Sie das Flag `-f` anstelle des Flags `-n`, um die Bereinigung auszuführen.

GIT-BRANCHES

* `git branch`: Listet alle Branches in Ihrem Repository auf. Fügen Sie ein `<branch>`-Argument hinzu, um einen neuen Branch mit dem Namen `<branch>` zu erstellen.
* `git checkout -b <branch>`: Erstellt einen neuen Branch namens `<branch>` und wechselt zu ihm. Lassen Sie das Flag `-b` weg, um zu einem vorhandenen Branch zu wechseln.
* `git merge <branch>`: Mergt `<branch>` in den aktuellen Branch.

REMOTE-REPOSITORIES

* `git remote add <name> <url>`: Erstellt eine neue Verbindung zu einem Remote-Repository. Nach dem Hinzufügen eines Remotes können Sie `<name>` als Verknüpfung für `<url>` in anderen Befehlen verwenden.
* `git fetch <remote> <branch>`: Holt einen bestimmten `<branch>` vom Repository. Lassen Sie `<branch>` weg, um alle Remote-Referenzen zu holen.
* `git pull <remote>`: Holt die Kopie des angegebenen Remotes des aktuellen Branches und mergt sie sofort in die lokale Kopie.
* `git push <remote> <branch>`: Pusht den Branch zum `<remote>` zusammen mit den notwendigen Commits und Objekten. Erstellt einen benannten Branch im Remote-Repository, falls er nicht existiert.

GIT-HISTORIE NEU SCHREIBEN

Zusätzliche Optionen

GIT-KONFIGURATION

* `git config --global user.name <name>`: Definiert den Autorennamen, der für alle Commits des aktuellen Benutzers verwendet werden soll.
* `git config --global user.email <email>`: Definiert die Autoren-E-Mail, die für alle Commits des aktuellen Benutzers verwendet werden soll.
* `git config --global alias.<alias-name> <git-command>`: Erstellt eine Verknüpfung für einen Git-Befehl. Z.B. `alias.glog "log --graph --oneline"` setzt `"git glog"` gleich `"git log --graph --oneline"`.
* `git config --system core.editor <editor>`: Legt den von Befehlen verwendeten Texteditor für alle Benutzer auf dem Rechner fest. Das Argument `<editor>` sollte der Befehl sein, der den gewünschten Editor startet (z.B. `vi`).
* `git config --global -edit`: Öffnet die globale Konfigurationsdatei in einem Texteditor zur manuellen Bearbeitung.

GIT-LOG

* `git log <limit>`: Begrenzt die Anzahl der Commits auf `<limit>`. Z.B. `git log -5` begrenzt auf 5 Commits.
* `git log --oneline`: Fasst jeden Commit auf eine einzige Zeile zusammen.
* `git log -p`: Zeigt den vollständigen Diff jedes Commits an.
* `git log --stat`: Zeigt an, welche Dateien geändert wurden und die relative Anzahl der hinzugefügten oder gelöschten Zeilen von jeder Datei.
* `git log --author="<pattern>"`: Sucht nach Commits eines bestimmten Autors.
* `git log --grep="<pattern>"`: Sucht nach Commits mit einer Commit-Nachricht, die `<pattern>` entspricht.
* `git log <since>..<until>`: Zeigt Commits an, die zwischen `<since>` und `<until>` liegen. Argumente können eine Commit-ID, ein Branch-Name, HEAD oder jede andere Art von Revisionsreferenz sein.
* `git log <file>`: Zeigt nur Commits an, die die angegebene Datei enthalten.
* `git log --graph --decorate`: Das Flag `--graph` zeichnet eine textbasierte Grafik der Commits auf der linken Seite der Commit-Nachrichten. `--decorate` fügt Namen von Branches oder Tags der angezeigten Commits hinzu.

GIT-DIFF

* `git diff HEAD`: Zeigt den Unterschied zwischen dem Arbeitsverzeichnis und dem letzten Commit.
* `git diff --cached`: Zeigt den Unterschied zwischen den gestageten Änderungen und dem letzten Commit.

GIT-RESET

* `git reset`: Setzt den Staging-Bereich auf den letzten Commit zurück, lässt aber das Arbeitsverzeichnis unverändert.
* `git reset --hard`: Setzt den Staging-Bereich und das Arbeitsverzeichnis auf den letzten Commit zurück und überschreibt alle Änderungen im Arbeitsverzeichnis.
* `git reset <commit>`: Verschiebt die aktuelle Branch-Spitze zurück auf `<commit>`, setzt den Staging-Bereich entsprechend zurück, lässt aber das Arbeitsverzeichnis in Ruhe.
* `git reset --hard <commit>`: Wie oben, aber setzt sowohl den Staging-Bereich als auch das Arbeitsverzeichnis entsprechend zurück. Löscht uncommitted Änderungen und alle Commits nach `<commit>`.

GIT-REBASE

* `git rebase -i <base>`: Rebasiert den aktuellen Branch interaktiv auf `<base>`. Startet einen Editor, um Befehle einzugeben, wie jeder Commit auf die neue Basis übertragen werden soll.

GIT-PULL

* `git pull --rebase <remote>`: Holt die Kopie des Remote-Repositorys des aktuellen Branches und rebasiert sie in die lokale Kopie. Verwendet `git rebase` anstelle von merge, um die Branches zu integrieren.

GIT-PUSH

* `git push <remote> --force`: Erzwingt den Git-Push, auch wenn er zu einem Nicht-Fast-Forward-Merge führt. Verwenden Sie das Flag `--force` nicht, es sei denn, Sie sind absolut sicher, was Sie tun.
* `git push <remote> --all`: Pusht alle Ihre lokalen Branches zum angegebenen Remote.
* `git push <remote> --tags`: Tags werden nicht automatisch gepusht, wenn Sie einen Branch pushen oder das Flag `--all` verwenden. Das Flag `--tags` sendet alle Ihre lokalen Tags an das Remote-Repository.