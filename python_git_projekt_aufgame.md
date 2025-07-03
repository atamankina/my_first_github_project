# Git & Python Lernprojekt: Dein Filmkatalog (Detaillierte Implementierung)

Willkommen zu deinem ersten kombinierten Lernprojekt! In diesem Szenario wirst du einen einfachen Filmkatalog in Python programmieren und dabei Git und GitHub nutzen, um deine Arbeit zu versionieren und jeden Entwicklungsschritt sauber zu dokumentieren.

Das Projekt ist in einzelne "Tickets" unterteilt. Jedes Ticket repräsentiert eine Aufgabe, die du implementieren und dann mit Git in einem eigenen Branch verwalten wirst. So lernst du, wie man inkrementell arbeitet und sinnvolle Commits erstellt.

## Projektübersicht: Der Filmkatalog

Du wirst ein Python-Programm erstellen, das dir erlaubt, Filme zu deiner Sammlung hinzuzufügen, sie anzuzeigen, zu suchen und zu löschen.

## Vorbereitung: Projekt initialisieren (Einmalig)

Bevor du mit den Tickets beginnst, musst du dein Projekt initialisieren und auf GitHub vorbereiten.

1. **Öffne VS Code.**
2. **Öffne das Terminal:** `Terminal > New Terminal`.
3. **Navigiere zum gewünschten Speicherort:**
    
    ```bash
    cd ~ # Oder ein anderer Projektordner
    ```
    
4. **Erstelle einen neuen Projektordner:**
    
    ```bash
    mkdir FilmkatalogProjekt
    cd FilmkatalogProjekt
    ```
    
5. **Initialisiere ein Git-Repository:**
    
    ```bash
    git init
    ```
    
6. **Erstelle die Hauptdatei für dein Programm:**
    - Klicke im VS Code Explorer auf "New File" und nenne die Datei `filmkatalog.py`.
    - Füge einen Kommentar hinzu: `# Dein Filmkatalog-Programm`
    - Speichere die Datei.
7. **Füge die Datei zum Staging hinzu und mache den ersten Commit:**
    
    ```bash
    git add filmkatalog.py
    git commit -m "Initialer Commit: Leere filmkatalog.py erstellt"
    ```
    
8. **Erstelle ein neues Repository auf GitHub:**
    - Gehe zu [github.com](https://github.com/) und melde dich an.
    - Klicke auf "+" > "New repository".
    - Nenne es `FilmkatalogProjekt`.
    - Wähle "Public" oder "Private".
    - **WICHTIG:** Wähle **NICHT** die Optionen zum Initialisieren des Repositories mit einer README, .gitignore oder Lizenz.
    - Klicke auf "Create repository".
9. **Verbinde dein lokales Repo mit GitHub und pushe:**
    - Kopiere die URL von GitHub (z.B. `https://github.com/DeinBenutzername/FilmkatalogProjekt.git`).
    - Im VS Code Terminal:
        
        ```bash
        git remote add origin https://github.com/DeinBenutzername/FilmkatalogProjekt.git
        git branch -M main
        git push -u origin main
        ```
        
    - Überprüfe auf GitHub, ob deine `filmkatalog.py`Datei hochgeladen wurde.

## Die Tickets: Schritt für Schritt zum Filmkatalog

Arbeite jedes Ticket einzeln ab. Für jedes Ticket wirst du einen neuen Git-Branch erstellen, deine Änderungen committen und den Branch dann in den `main`-Branch mergen.

### TICKET-001: Grundgerüst und Film-Liste

**Beschreibung:**
Implementiere ein leeres Python-Dictionary, das als Speicher für deine Filme dient. Füge eine Funktion hinzu, die alle aktuell im Katalog vorhandenen Filme anzeigt.

**Python-Grundlagen (Fokus):**

- Variablen, Listen, Dictionaries
- Funktionsdefinition (`def`)
- `print()`Anweisungen

**Git-Schritte:**

1. **Branch erstellen:** Erstelle einen neuen Branch für dieses Ticket.
    
    ```bash
    git checkout -b feature/film-liste
    ```
    
2. **Code implementieren (`filmkatalog.py`):**
    - Öffne die Datei `filmkatalog.py` in VS Code.
    - **Füge die globale Variable `filme` hinzu:** Direkt unter dem Kommentar `# Dein Filmkatalog-Programm` füge diese Zeile ein:
        
        ```python
        filme = {} # Ein Dictionary zum Speichern der Filme. Schlüssel: Filmtitel, Wert: Dictionary mit Details
        
        ```
        
    - **Definiere die Funktion `filme_anzeigen()`:** Füge die folgenden Zeilen unter der `filme = {}` Definition ein:
        
        ```python
        def filme_anzeigen():
            # Überprüfe, ob das 'filme'-Dictionary leer ist
            if not filme:
                print("Der Katalog ist leer.")
                return # Beende die Funktion hier, wenn keine Filme vorhanden sind
        
            print("\n--- Dein Filmkatalog ---")
            # Iteriere über alle Filme im Dictionary
            for titel, details in filme.items():
                print(f"Titel: {titel}")
                # Verwende .get(), um 'N/A' anzuzeigen, falls ein Detail fehlt
                print(f"  Regisseur: {details.get('regisseur', 'N/A')}")
                print(f"  Jahr: {details.get('jahr', 'N/A')}")
                print("-----------------------")
        
        # Test der Funktion (diese Zeile wird später durch ein Menü ersetzt)
        # filme_anzeigen()
        
        ```
        
    - **Dein `filmkatalog.py` sollte jetzt so aussehen:**
        
        ```python
        # Dein Filmkatalog-Programm
        
        filme = {} # Ein Dictionary zum Speichern der Filme. Schlüssel: Filmtitel, Wert: Dictionary mit Details
        
        def filme_anzeigen():
            if not filme:
                print("Der Katalog ist leer.")
                return
        
            print("\n--- Dein Filmkatalog ---")
            for titel, details in filme.items():
                print(f"Titel: {titel}")
                print(f"  Regisseur: {details.get('regisseur', 'N/A')}")
                print(f"  Jahr: {details.get('jahr', 'N/A')}")
                print("-----------------------")
        
        # Test der Funktion (wird später durch ein Menü ersetzt)
        # filme_anzeigen()
        
        ```
        
3. **Testen (im Terminal):**
    - Füge am Ende der Datei `filmkatalog.py` vorübergehend die Zeile `filme_anzeigen()` hinzu (entferne das `#` davor).
    - Führe das Skript aus: `python filmkatalog.py`
    - Erwarte die Ausgabe "Der Katalog ist leer.".
    - **Wichtig:** Entferne die Testzeile `filme_anzeigen()` wieder (oder kommentiere sie aus), bevor du committest.
4. **Änderungen zum Staging hinzufügen:**
    
    ```bash
    git add filmkatalog.py
    ```
    
5. **Commit erstellen:**
    
    ```bash
    git commit -m "FEAT: Funktion zum Anzeigen aller Filme hinzugefügt"
    ```
    
6. **Branch pushen:**
    
    ```bash
    git push -u origin feature/film-liste
    ```
    
7. **Merge in `main` (nach Absprache mit Lehrer/Mitschülern):**
    - Wechsle zum `main`Branch: `git checkout main`
    - Hole die neuesten Änderungen: `git pull`
    - Merge den Feature-Branch: `git merge feature/film-liste`
    - Pushe den `main`Branch: `git push`
    - Lösche den lokalen Feature-Branch: `git branch -d feature/film-liste`
    - (Optional) Lösche den Remote-Branch: `git push origin --delete feature/film-liste`

### TICKET-002: Film hinzufügen

**Beschreibung:**
Implementiere eine Funktion, die es dem Benutzer erlaubt, einen neuen Film mit Titel, Regisseur und Erscheinungsjahr zum Katalog hinzuzufügen.

**Python-Grundlagen (Fokus):**

- Funktionsparameter
- `input()` für Benutzereingaben
- Dictionary-Manipulation (Hinzufügen von Einträgen)

**Git-Schritte:**

1. **Branch erstellen:**
    
    ```bash
    git checkout -b feature/film-hinzufuegen
    ```
    
2. **Code implementieren (`filmkatalog.py`):**
    - Öffne die Datei `filmkatalog.py` in VS Code.
    - **Füge die Funktion `film_hinzufuegen()` hinzu:** Füge die folgenden Zeilen **nach** der `filme_anzeigen()` Funktion ein:
        
        ```python
        def film_hinzufuegen():
            print("\n--- Film hinzufügen ---")
            titel = input("Titel des Films: ")
            regisseur = input("Regisseur des Films: ")
            jahr = input("Erscheinungsjahr des Films: ")
        
            # Überprüfe, ob der Film bereits existiert
            if titel in filme:
                print(f"Fehler: Film '{titel}' existiert bereits im Katalog.")
                return # Beende die Funktion, wenn der Film schon da ist
        
            # Füge den neuen Film zum 'filme'-Dictionary hinzu
            filme[titel] = {
                "regisseur": regisseur,
                "jahr": jahr
            }
            print(f"Film '{titel}' wurde hinzugefügt.")
        
        # Test der Funktion (wird später durch ein Menü ersetzt)
        # film_hinzufuegen()
        # filme_anzeigen()
        
        ```
        
    - **Dein `filmkatalog.py` sollte jetzt so aussehen:**
        
        ```python
        # Dein Filmkatalog-Programm
        
        filme = {} # Ein Dictionary zum Speichern der Filme. Schlüssel: Filmtitel, Wert: Dictionary mit Details
        
        def filme_anzeigen():
            if not filme:
                print("Der Katalog ist leer.")
                return
        
            print("\n--- Dein Filmkatalog ---")
            for titel, details in filme.items():
                print(f"Titel: {titel}")
                print(f"  Regisseur: {details.get('regisseur', 'N/A')}")
                print(f"  Jahr: {details.get('jahr', 'N/A')}")
                print("-----------------------")
        
        def film_hinzufuegen():
            print("\n--- Film hinzufügen ---")
            titel = input("Titel des Films: ")
            regisseur = input("Regisseur des Films: ")
            jahr = input("Erscheinungsjahr des Films: ")
        
            if titel in filme:
                print(f"Fehler: Film '{titel}' existiert bereits im Katalog.")
                return
        
            filme[titel] = {
                "regisseur": regisseur,
                "jahr": jahr
            }
            print(f"Film '{titel}' wurde hinzugefügt.")
        
        # Test der Funktionen (werden später durch ein Menü ersetzt)
        # film_hinzufuegen()
        # filme_anzeigen()
        
        ```
        
3. **Testen (im Terminal):**
    - Füge am Ende der Datei vorübergehend die Zeilen `film_hinzufuegen()` und danach `filme_anzeigen()` hinzu (entferne die `#` davor).
    - Führe das Skript aus: `python filmkatalog.py`
    - Gib Filminformationen ein (z.B. Titel: "Inception", Regisseur: "Christopher Nolan", Jahr: "2010") und überprüfe, ob der Film korrekt angezeigt wird.
    - Versuche, denselben Film noch einmal hinzuzufügen, um die Fehlerbehandlung zu testen.
    - **Wichtig:** Entferne die Testzeilen wieder (oder kommentiere sie aus), bevor du committest.
4. **Änderungen zum Staging hinzufügen:**
    
    ```bash
    git add filmkatalog.py
    ```
    
5. **Commit erstellen:**
    
    ```bash
    git commit -m "FEAT: Funktion zum Hinzufügen von Filmen implementiert"
    ```
    
6. **Branch pushen:**
    
    ```bash
    git push -u origin feature/film-hinzufuegen
    ```
    
7. **Merge in `main` (nach Absprache):**
    - `git checkout main`
    - `git pull`
    - `git merge feature/film-hinzufuegen`
    - `git push`
    - `git branch -d feature/film-hinzufuegen`
    - `git push origin --delete feature/film-hinzufuegen`

### TICKET-003: Interaktives Menü

**Beschreibung:**
Erstelle ein einfaches Textmenü, das dem Benutzer erlaubt, zwischen den Funktionen "Film hinzufügen" und "Filme anzeigen" zu wählen. Das Menü soll in einer Schleife laufen, bis der Benutzer das Programm beendet.

**Python-Grundlagen (Fokus):**

- `while`Schleifen
- `if`/`elif`/`else`Anweisungen
- Endlosschleifen mit `break`
- Funktionsaufrufe
- `if __name__ == "__main__":` Block

**Git-Schritte:**

1. **Branch erstellen:**
    
    ```bash
    git checkout -b feature/interaktives-menue
    ```
    
2. **Code implementieren (`filmkatalog.py`):**
    - Öffne die Datei `filmkatalog.py` in VS Code.
    - **Füge die Funktion `zeige_menue()` hinzu:** Füge diese Funktion **nach** `film_hinzufuegen()` ein:
        
        ```python
        def zeige_menue():
            print("\n--- Filmkatalog Menü ---")
            print("1. Film hinzufügen")
            print("2. Filme anzeigen")
            print("3. Beenden")
            print("------------------------")
        ```
        
    - **Füge die Hauptfunktion `main()` hinzu:** Diese Funktion wird die Menü-Logik enthalten. Füge sie **nach** `zeige_menue()` ein:
        
        ```python
        def main():
            while True: # Eine Endlosschleife für das Menü
                zeige_menue() # Zeige das Menü an
                wahl = input("Ihre Wahl: ") # Erfasse die Benutzereingabe
        
                if wahl == '1':
                    film_hinzufuegen()
                elif wahl == '2':
                    filme_anzeigen()
                elif wahl == '3':
                    print("Programm wird beendet. Auf Wiedersehen!")
                    break # Beende die Schleife und damit das Programm
                else:
                    print("Ungültige Eingabe. Bitte versuchen Sie es erneut.")
        ```
        
    - **Füge den Startpunkt des Programms hinzu:** Ersetze alle vorhandenen Testzeilen am Ende der Datei (wie `# film_hinzufuegen()`) durch diesen Standard-Python-Block. Dieser Block stellt sicher, dass `main()` nur aufgerufen wird, wenn das Skript direkt ausgeführt wird.
        
        ```python
        # Startet das Hauptprogramm, wenn die Datei direkt ausgeführt wird
        if __name__ == "__main__":
            main()
        ```
        
    - **Dein `filmkatalog.py` sollte jetzt so aussehen:**
        
        ```python
        # Dein Filmkatalog-Programm
        
        filme = {} # Ein Dictionary zum Speichern der Filme. Schlüssel: Filmtitel, Wert: Dictionary mit Details
        
        def filme_anzeigen():
            if not filme:
                print("Der Katalog ist leer.")
                return
        
            print("\n--- Dein Filmkatalog ---")
            for titel, details in filme.items():
                print(f"Titel: {titel}")
                print(f"  Regisseur: {details.get('regisseur', 'N/A')}")
                print(f"  Jahr: {details.get('jahr', 'N/A')}")
                print("-----------------------")
        
        def film_hinzufuegen():
            print("\n--- Film hinzufügen ---")
            titel = input("Titel des Films: ")
            regisseur = input("Regisseur des Films: ")
            jahr = input("Erscheinungsjahr des Films: ")
        
            if titel in filme:
                print(f"Fehler: Film '{titel}' existiert bereits im Katalog.")
                return
        
            filme[titel] = {
                "regisseur": regisseur,
                "jahr": jahr
            }
            print(f"Film '{titel}' wurde hinzugefügt.")
        
        def zeige_menue():
            print("\n--- Filmkatalog Menü ---")
            print("1. Film hinzufügen")
            print("2. Filme anzeigen")
            print("3. Beenden")
            print("------------------------")
        
        def main():
            while True:
                zeige_menue()
                wahl = input("Ihre Wahl: ")
        
                if wahl == '1':
                    film_hinzufuegen()
                elif wahl == '2':
                    filme_anzeigen()
                elif wahl == '3':
                    print("Programm wird beendet. Auf Wiedersehen!")
                    break
                else:
                    print("Ungültige Eingabe. Bitte versuchen Sie es erneut.")
        
        # Startet das Hauptprogramm, wenn die Datei direkt ausgeführt wird
        if __name__ == "__main__":
            main()
        
        ```
        
3. **Testen (im Terminal):**
    - Führe das Skript aus: `python filmkatalog.py`
    - Teste alle Menüpunkte: Filme hinzufügen, anzeigen, beenden. Überprüfe auch ungültige Eingaben.
4. **Änderungen zum Staging hinzufügen:**
    
    ```bash
    git add filmkatalog.py
    ```
    
5. **Commit erstellen:**
    
    ```bash
    git commit -m "FEAT: Interaktives Menü für den Filmkatalog hinzugefügt"
    ```
    
6. **Branch pushen:**
    
    ```bash
    git push -u origin feature/interaktives-menue
    ```
    
7. **Merge in `main` (nach Absprache):**
    - `git checkout main`
    - `git pull`
    - `git merge feature/interaktives-menue`
    - `git push`
    - `git branch -d feature/interaktives-menue`
    - `git push origin --delete feature/interaktives-menue`

### TICKET-004: Film suchen

**Beschreibung:**
Füge eine Funktion hinzu, die es dem Benutzer erlaubt, Filme nach einem Teil des Titels zu suchen. Die Suche soll alle passenden Filme anzeigen.

**Python-Grundlagen (Fokus):**

- String-Methoden (`.lower()`, `in`)
- Schleifen zum Iterieren über Dictionaries
- Bedingte Anweisungen

**Git-Schritte:**

1. **Branch erstellen:**
    
    ```bash
    git checkout -b feature/film-suchen
    ```
    
2. **Code implementieren (`filmkatalog.py`):**
    - Öffne die Datei `filmkatalog.py` in VS Code.
    - **Füge die Funktion `film_suchen()` hinzu:** Füge diese Funktion **nach** der `film_hinzufuegen()` Funktion ein (oder an einer logischen Stelle vor `zeige_menue()`):
        
        ```python
        def film_suchen():
            print("\n--- Film suchen ---")
            suchbegriff = input("Geben Sie einen Suchbegriff für den Titel ein: ").lower()
            gefundene_filme = {} # Dictionary, um die gefundenen Filme zu speichern
        
            # Iteriere durch alle Filme im Katalog
            for titel, details in filme.items():
                # Überprüfe, ob der Suchbegriff im Titel (kleingeschrieben) enthalten ist
                if suchbegriff in titel.lower():
                    gefundene_filme[titel] = details # Füge den gefundenen Film hinzu
        
            # Wenn keine Filme gefunden wurden
            if not gefundene_filme:
                print(f"Keine Filme gefunden, die '{suchbegriff}' im Titel enthalten.")
                return
        
            print(f"\n--- Gefundene Filme für '{suchbegriff}' ---")
            # Zeige die Details der gefundenen Filme an (ähnlich wie filme_anzeigen)
            for titel, details in gefundene_filme.items():
                print(f"Titel: {titel}")
                print(f"  Regisseur: {details.get('regisseur', 'N/A')}")
                print(f"  Jahr: {details.get('jahr', 'N/A')}")
                print("-----------------------")
        
        ```
        
    - **Aktualisiere die `zeige_menue()` Funktion:** Füge eine neue Option "3. Film suchen" hinzu und passe die Nummern der folgenden Optionen an.
        
        ```python
        def zeige_menue():
            print("\n--- Filmkatalog Menü ---")
            print("1. Film hinzufügen")
            print("2. Filme anzeigen")
            print("3. Film suchen") # NEU
            print("4. Beenden")    # NUMMER GEÄNDERT
            print("------------------------")
        ```
        
    - **Aktualisiere die `main()` Funktion:** Füge einen `elif`Block hinzu, um die neue Option "3" zu verarbeiten, und passe die Nummer für "Beenden" an.
        
        ```python
        def main():
            while True:
                zeige_menue()
                wahl = input("Ihre Wahl: ")
        
                if wahl == '1':
                    film_hinzufuegen()
                elif wahl == '2':
                    filme_anzeigen()
                elif wahl == '3': # NEU
                    film_suchen()
                elif wahl == '4': # NUMMER GEÄNDERT
                    print("Programm wird beendet. Auf Wiedersehen!")
                    break
                else:
                    print("Ungültige Eingabe. Bitte versuchen Sie es erneut.")
        ```
        
    - **Dein `filmkatalog.py` sollte jetzt so aussehen:**
        
        ```python
        # Dein Filmkatalog-Programm
        
        filme = {} # Ein Dictionary zum Speichern der Filme. Schlüssel: Filmtitel, Wert: Dictionary mit Details
        
        def filme_anzeigen():
            if not filme:
                print("Der Katalog ist leer.")
                return
        
            print("\n--- Dein Filmkatalog ---")
            for titel, details in filme.items():
                print(f"Titel: {titel}")
                print(f"  Regisseur: {details.get('regisseur', 'N/A')}")
                print(f"  Jahr: {details.get('jahr', 'N/A')}")
                print("-----------------------")
        
        def film_hinzufuegen():
            print("\n--- Film hinzufügen ---")
            titel = input("Titel des Films: ")
            regisseur = input("Regisseur des Films: ")
            jahr = input("Erscheinungsjahr des Films: ")
        
            if titel in filme:
                print(f"Fehler: Film '{titel}' existiert bereits im Katalog.")
                return
        
            filme[titel] = {
                "regisseur": regisseur,
                "jahr": jahr
            }
            print(f"Film '{titel}' wurde hinzugefügt.")
        
        def film_suchen(): # NEU
            print("\n--- Film suchen ---")
            suchbegriff = input("Geben Sie einen Suchbegriff für den Titel ein: ").lower()
            gefundene_filme = {}
        
            for titel, details in filme.items():
                if suchbegriff in titel.lower():
                    gefundene_filme[titel] = details
        
            if not gefundene_filme:
                print(f"Keine Filme gefunden, die '{suchbegriff}' im Titel enthalten.")
                return
        
            print(f"\n--- Gefundene Filme für '{suchbegriff}' ---")
            for titel, details in gefundene_filme.items():
                print(f"Titel: {titel}")
                print(f"  Regisseur: {details.get('regisseur', 'N/A')}")
                print(f"  Jahr: {details.get('jahr', 'N/A')}")
                print("-----------------------")
        
        def zeige_menue():
            print("\n--- Filmkatalog Menü ---")
            print("1. Film hinzufügen")
            print("2. Filme anzeigen")
            print("3. Film suchen") # GEÄNDERT
            print("4. Beenden")    # GEÄNDERT
            print("------------------------")
        
        def main():
            while True:
                zeige_menue()
                wahl = input("Ihre Wahl: ")
        
                if wahl == '1':
                    film_hinzufuegen()
                elif wahl == '2':
                    filme_anzeigen()
                elif wahl == '3': # GEÄNDERT
                    film_suchen()
                elif wahl == '4': # GEÄNDERT
                    print("Programm wird beendet. Auf Wiedersehen!")
                    break
                else:
                    print("Ungültige Eingabe. Bitte versuchen Sie es erneut.")
        
        if __name__ == "__main__":
            main()
        
        ```
        
3. **Testen (im Terminal):**
    - Führe das Skript aus: `python filmkatalog.py`
    - Füge einige Filme hinzu (z.B. "Matrix", "Der Herr der Ringe", "Star Wars").
    - Wähle die neue Suchfunktion im Menü und teste verschiedene Suchbegriffe (z.B. "mat", "ringe", "star", "existiertnicht").
4. **Änderungen zum Staging hinzufügen:**
    
    ```bash
    git add filmkatalog.py
    ```
    
5. **Commit erstellen:**
    
    ```bash
    git commit -m "FEAT: Funktion zum Suchen von Filmen nach Titel implementiert"
    ```
    
6. **Branch pushen:**
    
    ```bash
    git push -u origin feature/film-suchen
    ```
    
7. **Merge in `main` (nach Absprache):**
    - `git checkout main`
    - `git pull`
    - `git merge feature/film-suchen`
    - `git push`
    - `git branch -d feature/film-suchen`
    - `git push origin --delete feature/film-suchen`

### TICKET-005: Film löschen

**Beschreibung:**
Implementiere eine Funktion, die es dem Benutzer erlaubt, einen Film anhand seines Titels aus dem Katalog zu entfernen.

**Python-Grundlagen (Fokus):**

- Dictionary-Methoden (`.pop()`, `del`)
- Fehlerbehandlung (Film nicht gefunden)

**Git-Schritte:**

1. **Branch erstellen:**
    
    ```bash
    git checkout -b feature/film-loeschen
    ```
    
2. **Code implementieren (`filmkatalog.py`):**
    - Öffne die Datei `filmkatalog.py` in VS Code.
    - **Füge die Funktion `film_loeschen()` hinzu:** Füge diese Funktion **nach** der `film_suchen()` Funktion ein:
        
        ```python
        def film_loeschen():
            print("\n--- Film löschen ---")
            titel_zu_loeschen = input("Titel des zu löschenden Films: ")
            # Überprüfe, ob der Film im Katalog existiert
            if titel_zu_loeschen in filme:
                del filme[titel_zu_loeschen] # Entferne den Film aus dem Dictionary
                print(f"Film '{titel_zu_loeschen}' wurde aus dem Katalog entfernt.")
            else:
                print(f"Fehler: Film '{titel_zu_loeschen}' nicht im Katalog gefunden.")
        
        ```
        
    - **Aktualisiere die `zeige_menue()` Funktion:** Füge eine neue Option "4. Film löschen" hinzu und passe die Nummer der "Beenden"-Option an.
        
        ```bash
        def zeige_menue():
            print("\n--- Filmkatalog Menü ---")
            print("1. Film hinzufügen")
            print("2. Filme anzeigen")
            print("3. Film suchen")
            print("4. Film löschen") # NEU
            print("5. Beenden")     # NUMMER GEÄNDERT
            print("------------------------")
        
        ```
        
    - **Aktualisiere die `main()` Funktion:** Füge einen `elif`Block hinzu, um die neue Option "4" zu verarbeiten, und passe die Nummer für "Beenden" an.
        
        ```python
        def main():
            while True:
                zeige_menue()
                wahl = input("Ihre Wahl: ")
        
                if wahl == '1':
                    film_hinzufuegen()
                elif wahl == '2':
                    filme_anzeigen()
                elif wahl == '3':
                    film_suchen()
                elif wahl == '4': # NEU
                    film_loeschen()
                elif wahl == '5': # NUMMER GEÄNDERT
                    print("Programm wird beendet. Auf Wiedersehen!")
                    break
                else:
                    print("Ungültige Eingabe. Bitte versuchen Sie es erneut.")
        
        ```
        
    - **Dein `filmkatalog.py` sollte jetzt so aussehen:**
        
        ```python
        # Dein Filmkatalog-Programm
        
        filme = {} # Ein Dictionary zum Speichern der Filme. Schlüssel: Filmtitel, Wert: Dictionary mit Details
        
        def filme_anzeigen():
            if not filme:
                print("Der Katalog ist leer.")
                return
        
            print("\n--- Dein Filmkatalog ---")
            for titel, details in filme.items():
                print(f"Titel: {titel}")
                print(f"  Regisseur: {details.get('regisseur', 'N/A')}")
                print(f"  Jahr: {details.get('jahr', 'N/A')}")
                print("-----------------------")
        
        def film_hinzufuegen():
            print("\n--- Film hinzufügen ---")
            titel = input("Titel des Films: ")
            regisseur = input("Regisseur des Films: ")
            jahr = input("Erscheinungsjahr des Films: ")
        
            if titel in filme:
                print(f"Fehler: Film '{titel}' existiert bereits im Katalog.")
                return
        
            filme[titel] = {
                "regisseur": regisseur,
                "jahr": jahr
            }
            print(f"Film '{titel}' wurde hinzugefügt.")
        
        def film_suchen():
            print("\n--- Film suchen ---")
            suchbegriff = input("Geben Sie einen Suchbegriff für den Titel ein: ").lower()
            gefundene_filme = {}
        
            for titel, details in filme.items():
                if suchbegriff in titel.lower():
                    gefundene_filme[titel] = details
        
            if not gefundene_filme:
                print(f"Keine Filme gefunden, die '{suchbegriff}' im Titel enthalten.")
                return
        
            print(f"\n--- Gefundene Filme für '{suchbegriff}' ---")
            for titel, details in gefundene_filme.items():
                print(f"Titel: {titel}")
                print(f"  Regisseur: {details.get('regisseur', 'N/A')}")
                print(f"  Jahr: {details.get('jahr', 'N/A')}")
                print("-----------------------")
        
        def film_loeschen(): # NEU
            print("\n--- Film löschen ---")
            titel_zu_loeschen = input("Titel des zu löschenden Films: ")
            if titel_zu_loeschen in filme:
                del filme[titel_zu_loeschen]
                print(f"Film '{titel_zu_loeschen}' wurde aus dem Katalog entfernt.")
            else:
                print(f"Fehler: Film '{titel_zu_loeschen}' nicht im Katalog gefunden.")
        
        def zeige_menue():
            print("\n--- Filmkatalog Menü ---")
            print("1. Film hinzufügen")
            print("2. Filme anzeigen")
            print("3. Film suchen")
            print("4. Film löschen") # GEÄNDERT
            print("5. Beenden")     # GEÄNDERT
            print("------------------------")
        
        def main():
            while True:
                zeige_menue()
                wahl = input("Ihre Wahl: ")
        
                if wahl == '1':
                    film_hinzufuegen()
                elif wahl == '2':
                    filme_anzeigen()
                elif wahl == '3':
                    film_suchen()
                elif wahl == '4': # GEÄNDERT
                    film_loeschen()
                elif wahl == '5': # GEÄNDERT
                    print("Programm wird beendet. Auf Wiedersehen!")
                    break
                else:
                    print("Ungültige Eingabe. Bitte versuchen Sie es erneut.")
        
        if __name__ == "__main__":
            main()
        
        ```
        
3. **Testen (im Terminal):**
    - Führe das Skript aus: `python filmkatalog.py`
    - Füge einen Film hinzu, lösche ihn dann und überprüfe mit "Filme anzeigen", ob er weg ist.
    - Versuche, einen nicht existierenden Film zu löschen, um die Fehlermeldung zu sehen.
4. **Änderungen zum Staging hinzufügen:**
    
    ```bash
    git add filmkatalog.py
    ```
    
5. **Commit erstellen:**
    
    ```bash
    git commit -m "FEAT: Funktion zum Löschen von Filmen implementiert"
    ```
    
6. **Branch pushen:**
    
    ```bash
    git push -u origin feature/film-loeschen
    ```
    
7. **Merge in `main` (nach Absprache):**
    - `git checkout main`
    - `git pull`
    - `git merge feature/film-loeschen`
    - `git push`
    - `git branch -d feature/film-loeschen`
    - `git push origin --delete feature/film-loeschen`

### TICKET-006: Katalog speichern und laden (JSON)

**Beschreibung:**
Implementiere Funktionen, um den Filmkatalog in einer JSON-Datei zu speichern und beim Start des Programms zu laden.

**Python-Grundlagen (Fokus):**

- Dateihandling (`open()`, `with`)
- JSON-Modul (`json.dump()`, `json.load()`)
- Fehlerbehandlung (`try`/`except` für `FileNotFoundError`, `json.JSONDecodeError`)

**Git-Schritte:**

1. **Branch erstellen:**
    
    ```bash
    git checkout -b feature/speichern-laden
    ```
    
2. **Code implementieren (`filmkatalog.py`):**
    - Öffne die Datei `filmkatalog.py` in VS Code.
    - **Importiere das `json`Modul:** Füge diese Zeile ganz am Anfang der Datei ein:
        
        ```python
        import json
        ```
        
    - **Definiere den Dateinamen als Konstante:** Füge diese Zeile direkt unter der `filme = {}` Definition ein:
        
        ```python
        DATEINAME = "filme.json" # Dateiname für die Speicherung des Katalogs
        ```
        
    - **Füge die Funktion `katalog_speichern()` hinzu:** Füge diese Funktion **nach** `film_loeschen()` ein:
        
        ```python
        def katalog_speichern():
            try:
                # Öffne die Datei im Schreibmodus ('w') mit UTF-8-Kodierung
                with open(DATEINAME, 'w', encoding='utf-8') as f:
                    # Speichere das 'filme'-Dictionary als JSON in der Datei
                    # indent=4 für schöne Formatierung, ensure_ascii=False für Umlaute
                    json.dump(filme, f, indent=4, ensure_ascii=False)
                print(f"Katalog erfolgreich in '{DATEINAME}' gespeichert.")
            except IOError as e:
                print(f"Fehler beim Speichern des Katalogs: {e}")
        
        ```
        
    - **Füge die Funktion `katalog_laden()` hinzu:** Füge diese Funktion **nach** `katalog_speichern()` ein:
        
        ```python
        def katalog_laden():
            global filme # Erlaube den Zugriff auf die globale 'filme'-Variable
            try:
                # Versuche, die Datei im Lesemodus ('r') zu öffnen
                with open(DATEINAME, 'r', encoding='utf-8') as f:
                    filme = json.load(f) # Lade die JSON-Daten in das 'filme'-Dictionary
                print(f"Katalog erfolgreich aus '{DATEINAME}' geladen.")
            except FileNotFoundError:
                # Wenn die Datei nicht existiert, ist das normal beim ersten Start
                print("Keine vorhandene Katalogdatei gefunden. Starte mit leerem Katalog.")
                filme = {} # Stelle sicher, dass 'filme' initialisiert ist
            except json.JSONDecodeError as e:
                # Wenn die Datei existiert, aber kein gültiges JSON enthält
                print(f"Fehler beim Laden des Katalogs (ungültiges JSON): {e}. Starte mit leerem Katalog.")
                filme = {}
            except Exception as e:
                # Fange alle anderen unerwarteten Fehler ab
                print(f"Ein unerwarteter Fehler beim Laden ist aufgetreten: {e}. Starte mit leerem Katalog.")
                filme = {}
        
        ```
        
    - **Aktualisiere die `main()` Funktion:**
        - Rufe `katalog_laden()` ganz am Anfang der `main()` Funktion auf, bevor die `while True`Schleife beginnt.
        - Rufe `katalog_speichern()` auf, bevor das Programm beendet wird (innerhalb des `elif wahl == '5':` Blocks, vor dem `break`).
        
        ```python
        def main():
            katalog_laden() # Hier am Anfang aufrufen, um den Katalog zu laden
            while True:
                zeige_menue()
                wahl = input("Ihre Wahl: ")
        
                if wahl == '1':
                    film_hinzufuegen()
                elif wahl == '2':
                    filme_anzeigen()
                elif wahl == '3':
                    film_suchen()
                elif wahl == '4':
                    film_loeschen()
                elif wahl == '5':
                    katalog_speichern() # Hier vor dem Beenden aufrufen
                    print("Programm wird beendet. Auf Wiedersehen!")
                    break
                else:
                    print("Ungültige Eingabe. Bitte versuchen Sie es erneut.")
        
        ```
        
    - **Dein `filmkatalog.py` sollte jetzt so aussehen:**
        
        ```python
        import json # NEU
        
        # Dein Filmkatalog-Programm
        
        filme = {} # Ein Dictionary zum Speichern der Filme. Schlüssel: Filmtitel, Wert: Dictionary mit Details
        DATEINAME = "filme.json" # NEU: Dateiname für die Speicherung des Katalogs
        
        def filme_anzeigen():
            if not filme:
                print("Der Katalog ist leer.")
                return
        
            print("\n--- Dein Filmkatalog ---")
            for titel, details in filme.items():
                print(f"Titel: {titel}")
                print(f"  Regisseur: {details.get('regisseur', 'N/A')}")
                print(f"  Jahr: {details.get('jahr', 'N/A')}")
                print("-----------------------")
        
        def film_hinzufuegen():
            print("\n--- Film hinzufügen ---")
            titel = input("Titel des Films: ")
            regisseur = input("Regisseur des Films: ")
            jahr = input("Erscheinungsjahr des Films: ")
        
            if titel in filme:
                print(f"Fehler: Film '{titel}' existiert bereits im Katalog.")
                return
        
            filme[titel] = {
                "regisseur": regisseur,
                "jahr": jahr
            }
            print(f"Film '{titel}' wurde hinzugefügt.")
        
        def film_suchen():
            print("\n--- Film suchen ---")
            suchbegriff = input("Geben Sie einen Suchbegriff für den Titel ein: ").lower()
            gefundene_filme = {}
        
            for titel, details in filme.items():
                if suchbegriff in titel.lower():
                    gefundene_filme[titel] = details
        
            if not gefundene_filme:
                print(f"Keine Filme gefunden, die '{suchbegriff}' im Titel enthalten.")
                return
        
            print(f"\n--- Gefundene Filme für '{suchbegriff}' ---")
            for titel, details in gefundene_filme.items():
                print(f"Titel: {titel}")
                print(f"  Regisseur: {details.get('regisseur', 'N/A')}")
                print(f"  Jahr: {details.get('jahr', 'N/A')}")
                print("-----------------------")
        
        def film_loeschen():
            print("\n--- Film löschen ---")
            titel_zu_loeschen = input("Titel des zu löschenden Films: ")
            if titel_zu_loeschen in filme:
                del filme[titel_zu_loeschen]
                print(f"Film '{titel_zu_loeschen}' wurde aus dem Katalog entfernt.")
            else:
                print(f"Fehler: Film '{titel_zu_loeschen}' nicht im Katalog gefunden.")
        
        def katalog_speichern(): # NEU
            try:
                with open(DATEINAME, 'w', encoding='utf-8') as f:
                    json.dump(filme, f, indent=4, ensure_ascii=False)
                print(f"Katalog erfolgreich in '{DATEINAME}' gespeichert.")
            except IOError as e:
                print(f"Fehler beim Speichern des Katalogs: {e}")
        
        def katalog_laden(): # NEU
            global filme
            try:
                with open(DATEINAME, 'r', encoding='utf-8') as f:
                    filme = json.load(f)
                print(f"Katalog erfolgreich aus '{DATEINAME}' geladen.")
            except FileNotFoundError:
                print("Keine vorhandene Katalogdatei gefunden. Starte mit leerem Katalog.")
                filme = {}
            except json.JSONDecodeError as e:
                print(f"Fehler beim Laden des Katalogs (ungültiges JSON): {e}. Starte mit leerem Katalog.")
                filme = {}
            except Exception as e:
                print(f"Ein unerwarteter Fehler beim Laden ist aufgetreten: {e}. Starte mit leerem Katalog.")
                filme = {}
        
        def zeige_menue():
            print("\n--- Filmkatalog Menü ---")
            print("1. Film hinzufügen")
            print("2. Filme anzeigen")
            print("3. Film suchen")
            print("4. Film löschen")
            print("5. Beenden")
            print("------------------------")
        
        def main():
            katalog_laden() # GEÄNDERT: Laden beim Start
            while True:
                zeige_menue()
                wahl = input("Ihre Wahl: ")
        
                if wahl == '1':
                    film_hinzufuegen()
                elif wahl == '2':
                    filme_anzeigen()
                elif wahl == '3':
                    film_suchen()
                elif wahl == '4':
                    film_loeschen()
                elif wahl == '5':
                    katalog_speichern() # GEÄNDERT: Speichern vor dem Beenden
                    print("Programm wird beendet. Auf Wiedersehen!")
                    break
                else:
                    print("Ungültige Eingabe. Bitte versuchen Sie es erneut.")
        
        if __name__ == "__main__":
            main()
        
        ```
        
3. **Testen (im Terminal):**
    - Führe das Skript aus. Füge einige Filme hinzu. Beende das Programm (Option 5).
    - Starte das Programm erneut. Sind die Filme noch da? (Sie sollten aus `filme.json` geladen werden).
    - Öffne die Datei `filme.json` in VS Code, um den gespeicherten JSON-Inhalt zu sehen.
    - Lösche die `filme.json`Datei manuell im Explorer und starte das Programm. Es sollte mit einem leeren Katalog starten und die Meldung "Keine vorhandene Katalogdatei gefunden." anzeigen.
4. **Änderungen zum Staging hinzufügen:**
    
    ```bash
    git add filmkatalog.py
    git add filme.json # Füge auch die neue JSON-Datei hinzu, wenn sie erstellt wurde
    ```
    
5. **Commit erstellen:**
    
    ```bash
    git commit -m "FEAT: Katalog speichern und laden mit JSON implementiert"
    ```
    
6. **Branch pushen:**
    
    ```bash
    git push -u origin feature/speichern-laden
    ```
    
7. **Merge in `main` (nach Absprache):**
    - `git checkout main`
    - `git pull`
    - `git merge feature/speichern-laden`
    - `git push`
    - `git branch -d feature/speichern-laden`
    - `git push origin --delete feature/speichern-laden`

### TICKET-007: Zusätzliche Filmdetails (Genre & Bewertung)

**Beschreibung:**
Erweitere die Film-Struktur um die Felder "Genre" und "Bewertung" (z.B. 1-5 Sterne). Passe die Funktionen zum Hinzufügen, Anzeigen und Suchen entsprechend an.

**Python-Grundlagen (Fokus):**

- Dictionary-Strukturierung
- Erweiterung bestehender Funktionen
- (Optional) Eingabevalidierung für Bewertung (z.B. nur Zahlen 1-5)

**Git-Schritte:**

1. **Branch erstellen:**
    
    ```bash
    git checkout -b feature/mehr-filmdetails
    ```
    
2. **Code implementieren (`filmkatalog.py`):**
    - Öffne die Datei `filmkatalog.py` in VS Code.
    - **Passe `film_hinzufuegen()` an:** Füge nach der Abfrage des Jahres neue `input()`Zeilen für Genre und Bewertung hinzu.
        
        ```python
        def film_hinzufuegen():
            print("\n--- Film hinzufügen ---")
            titel = input("Titel des Films: ")
            regisseur = input("Regisseur des Films: ")
            jahr = input("Erscheinungsjahr des Films: ")
            genre = input("Genre des Films: ") # NEU
            bewertung = input("Bewertung (1-5 Sterne): ") # NEU
        
            if titel in filme:
                print(f"Fehler: Film '{titel}' existiert bereits im Katalog.")
                return
        
            filme[titel] = {
                "regisseur": regisseur,
                "jahr": jahr,
                "genre": genre,       # NEU
                "bewertung": bewertung # NEU
            }
            print(f"Film '{titel}' wurde hinzugefügt.")
        
        ```
        
    - **Passe `filme_anzeigen()` an:** Füge die Anzeige für Genre und Bewertung hinzu. Verwende `.get()` für Kompatibilität mit älteren Filmen, die diese Felder noch nicht haben.
        
        ```python
        def filme_anzeigen():
            if not filme:
                print("Der Katalog ist leer.")
                return
        
            print("\n--- Dein Filmkatalog ---")
            for titel, details in filme.items():
                print(f"Titel: {titel}")
                print(f"  Regisseur: {details.get('regisseur', 'N/A')}")
                print(f"  Jahr: {details.get('jahr', 'N/A')}")
                print(f"  Genre: {details.get('genre', 'N/A')}")       # NEU
                print(f"  Bewertung: {details.get('bewertung', 'N/A')}") # NEU
                print("-----------------------")
        
        ```
        
    - **Passe `film_suchen()` an:** Füge die Anzeige für Genre und Bewertung hinzu. (Die Suchlogik selbst muss nicht unbedingt geändert werden, es sei denn, du willst auch nach Genre suchen können).
        
        ```python
        def film_suchen():
            print("\n--- Film suchen ---")
            suchbegriff = input("Geben Sie einen Suchbegriff für den Titel ein: ").lower()
            gefundene_filme = {}
        
            for titel, details in filme.items():
                if suchbegriff in titel.lower():
                    gefundene_filme[titel] = details
        
            if not gefundene_filme:
                print(f"Keine Filme gefunden, die '{suchbegriff}' im Titel enthalten.")
                return
        
            print(f"\n--- Gefundene Filme für '{suchbegriff}' ---")
            for titel, details in gefundene_filme.items():
                print(f"Titel: {titel}")
                print(f"  Regisseur: {details.get('regisseur', 'N/A')}")
                print(f"  Jahr: {details.get('jahr', 'N/A')}")
                print(f"  Genre: {details.get('genre', 'N/A')}")       # NEU
                print(f"  Bewertung: {details.get('bewertung', 'N/A')}") # NEU
                print("-----------------------")
        
        ```
        
    - **Dein `filmkatalog.py` sollte jetzt so aussehen:**
        
        ```python
        import json
        
        # Dein Filmkatalog-Programm
        
        filme = {} # Ein Dictionary zum Speichern der Filme. Schlüssel: Filmtitel, Wert: Dictionary mit Details
        DATEINAME = "filme.json" # Dateiname für die Speicherung des Katalogs
        
        def filme_anzeigen():
            if not filme:
                print("Der Katalog ist leer.")
                return
        
            print("\n--- Dein Filmkatalog ---")
            for titel, details in filme.items():
                print(f"Titel: {titel}")
                print(f"  Regisseur: {details.get('regisseur', 'N/A')}")
                print(f"  Jahr: {details.get('jahr', 'N/A')}")
                print(f"  Genre: {details.get('genre', 'N/A')}")       # GEÄNDERT
                print(f"  Bewertung: {details.get('bewertung', 'N/A')}") # GEÄNDERT
                print("-----------------------")
        
        def film_hinzufuegen():
            print("\n--- Film hinzufügen ---")
            titel = input("Titel des Films: ")
            regisseur = input("Regisseur des Films: ")
            jahr = input("Erscheinungsjahr des Films: ")
            genre = input("Genre des Films: ") # NEU
            bewertung = input("Bewertung (1-5 Sterne): ") # NEU
        
            if titel in filme:
                print(f"Fehler: Film '{titel}' existiert bereits im Katalog.")
                return
        
            filme[titel] = {
                "regisseur": regisseur,
                "jahr": jahr,
                "genre": genre,       # NEU
                "bewertung": bewertung # NEU
            }
            print(f"Film '{titel}' wurde hinzugefügt.")
        
        def film_suchen():
            print("\n--- Film suchen ---")
            suchbegriff = input("Geben Sie einen Suchbegriff für den Titel ein: ").lower()
            gefundene_filme = {}
        
            for titel, details in filme.items():
                if suchbegriff in titel.lower():
                    gefundene_filme[titel] = details
        
            if not gefundene_filme:
                print(f"Keine Filme gefunden, die '{suchbegriff}' im Titel enthalten.")
                return
        
            print(f"\n--- Gefundene Filme für '{suchbegriff}' ---")
            for titel, details in gefundene_filme.items():
                print(f"Titel: {titel}")
                print(f"  Regisseur: {details.get('regisseur', 'N/A')}")
                print(f"  Jahr: {details.get('jahr', 'N/A')}")
                print(f"  Genre: {details.get('genre', 'N/A')}")       # GEÄNDERT
                print(f"  Bewertung: {details.get('bewertung', 'N/A')}") # GEÄNDERT
                print("-----------------------")
        
        def film_loeschen():
            print("\n--- Film löschen ---")
            titel_zu_loeschen = input("Titel des zu löschenden Films: ")
            if titel_zu_loeschen in filme:
                del filme[titel_zu_loeschen]
                print(f"Film '{titel_zu_loeschen}' wurde aus dem Katalog entfernt.")
            else:
                print(f"Fehler: Film '{titel_zu_loeschen}' nicht im Katalog gefunden.")
        
        def katalog_speichern():
            try:
                with open(DATEINAME, 'w', encoding='utf-8') as f:
                    json.dump(filme, f, indent=4, ensure_ascii=False)
                print(f"Katalog erfolgreich in '{DATEINAME}' gespeichert.")
            except IOError as e:
                print(f"Fehler beim Speichern des Katalogs: {e}")
        
        def katalog_laden():
            global filme
            try:
                with open(DATEINAME, 'r', encoding='utf-8') as f:
                    filme = json.load(f)
                print(f"Katalog erfolgreich aus '{DATEINAME}' geladen.")
            except FileNotFoundError:
                print("Keine vorhandene Katalogdatei gefunden. Starte mit leerem Katalog.")
                filme = {}
            except json.JSONDecodeError as e:
                print(f"Fehler beim Laden des Katalogs (ungültiges JSON): {e}. Starte mit leerem Katalog.")
                filme = {}
            except Exception as e:
                print(f"Ein unerwarteter Fehler beim Laden ist aufgetreten: {e}. Starte mit leerem Katalog.")
                filme = {}
        
        def zeige_menue():
            print("\n--- Filmkatalog Menü ---")
            print("1. Film hinzufügen")
            print("2. Filme anzeigen")
            print("3. Film suchen")
            print("4. Film löschen")
            print("5. Beenden")
            print("------------------------")
        
        def main():
            katalog_laden()
            while True:
                zeige_menue()
                wahl = input("Ihre Wahl: ")
        
                if wahl == '1':
                    film_hinzufuegen()
                elif wahl == '2':
                    filme_anzeigen()
                elif wahl == '3':
                    film_suchen()
                elif wahl == '4':
                    film_loeschen()
                elif wahl == '5':
                    katalog_speichern()
                    print("Programm wird beendet. Auf Wiedersehen!")
                    break
                else:
                    print("Ungültige Eingabe. Bitte versuchen Sie es erneut.")
        
        if __name__ == "__main__":
            main()
        
        ```
        
3. **Testen (im Terminal):**
    - Führe das Skript aus. Füge neue Filme mit allen Details (Genre, Bewertung) hinzu.
    - Lade alte Filme (die vor dieser Änderung gespeichert wurden) und überprüfe, wie sie angezeigt werden. Sie sollten `N/A` für Genre und Bewertung anzeigen, was korrekt ist, da diese Felder noch nicht existierten.
    - Teste die Anzeige und Suche.
4. **Änderungen zum Staging hinzufügen:**
    
    ```bash
    git add filmkatalog.py
    
    ```
    
5. **Commit erstellen:**
    
    ```bash
    git commit -m "FEAT: Zusätzliche Filmdetails (Genre, Bewertung) hinzugefügt"
    
    ```
    
6. **Branch pushen:**
    
    ```bash
    git push -u origin feature/mehr-filmdetails
    
    ```
    
7. **Merge in `main` (nach Absprache):**
    - `git checkout main`
    - `git pull`
    - `git merge feature/mehr-filmdetails`
    - `git push`
    - `git branch -d feature/mehr-filmdetails`
    - `git push origin --delete feature/mehr-filmdetails`

### TICKET-008: Eingabevalidierung und Fehlerbehandlung

**Beschreibung:**
Verbessere die Robustheit deines Programms, indem du Benutzereingaben validierst (z.B. Jahr muss eine Zahl sein, Bewertung im Bereich 1-5) und geeignete Fehlermeldungen ausgibst.

**Python-Grundlagen (Fokus):**

- `try`/`except` Blöcke
- `int()`Konvertierung
- Bedingte Logik für Wertebereiche
- Schleifen für wiederholte Eingabe bei Fehlern

**Git-Schritte:**

1. **Branch erstellen:**
    
    ```bash
    git checkout -b chore/validierung-fehlerbehandlung
    
    ```
    
2. **Code implementieren (`filmkatalog.py`):**
    - Öffne die Datei `filmkatalog.py` in VS Code.
    - **Passe `film_hinzufuegen()` an:** Füge `try-except`Blöcke und `while`Schleifen hinzu, um die Eingabe für Jahr und Bewertung zu validieren.
        
        ```python
        def film_hinzufuegen():
            print("\n--- Film hinzufügen ---")
            titel = input("Titel des Films: ")
            regisseur = input("Regisseur des Films: ")
        
            # Validierung für das Jahr
            while True:
                jahr_str = input("Erscheinungsjahr des Films: ")
                try:
                    jahr = int(jahr_str) # Versuche, die Eingabe in eine Ganzzahl umzuwandeln
                    break # Wenn erfolgreich, beende die Schleife
                except ValueError:
                    print("Ungültige Eingabe. Das Jahr muss eine Zahl sein.")
        
            genre = input("Genre des Films: ")
        
            # Validierung für die Bewertung
            while True:
                bewertung_str = input("Bewertung (1-5 Sterne): ")
                try:
                    bewertung = int(bewertung_str)
                    if 1 <= bewertung <= 5: # Überprüfe, ob die Bewertung im gültigen Bereich liegt
                        break # Wenn erfolgreich, beende die Schleife
                    else:
                        print("Ungültige Bewertung. Bitte geben Sie eine Zahl zwischen 1 und 5 ein.")
                except ValueError:
                    print("Ungültige Eingabe. Die Bewertung muss eine Zahl sein.")
        
            if titel in filme:
                print(f"Fehler: Film '{titel}' existiert bereits im Katalog.")
                return
        
            filme[titel] = {
                "regisseur": regisseur,
                "jahr": jahr,
                "genre": genre,
                "bewertung": bewertung
            }
            print(f"Film '{titel}' wurde hinzugefügt.")
        
        ```
        
    - **Dein `filmkatalog.py` sollte jetzt so aussehen:**
        
        ```python
        import json
        
        # Dein Filmkatalog-Programm
        
        filme = {} # Ein Dictionary zum Speichern der Filme. Schlüssel: Filmtitel, Wert: Dictionary mit Details
        DATEINAME = "filme.json" # Dateiname für die Speicherung des Katalogs
        
        def filme_anzeigen():
            if not filme:
                print("Der Katalog ist leer.")
                return
        
            print("\n--- Dein Filmkatalog ---")
            for titel, details in filme.items():
                print(f"Titel: {titel}")
                print(f"  Regisseur: {details.get('regisseur', 'N/A')}")
                print(f"  Jahr: {details.get('jahr', 'N/A')}")
                print(f"  Genre: {details.get('genre', 'N/A')}")
                print(f"  Bewertung: {details.get('bewertung', 'N/A')}")
                print("-----------------------")
        
        def film_hinzufuegen(): # GEÄNDERT: Mit Validierung
            print("\n--- Film hinzufügen ---")
            titel = input("Titel des Films: ")
            regisseur = input("Regisseur des Films: ")
        
            # Validierung für das Jahr
            while True:
                jahr_str = input("Erscheinungsjahr des Films: ")
                try:
                    jahr = int(jahr_str)
                    break
                except ValueError:
                    print("Ungültige Eingabe. Das Jahr muss eine Zahl sein.")
        
            genre = input("Genre des Films: ")
        
            # Validierung für die Bewertung
            while True:
                bewertung_str = input("Bewertung (1-5 Sterne): ")
                try:
                    bewertung = int(bewertung_str)
                    if 1 <= bewertung <= 5:
                        break
                    else:
                        print("Ungültige Bewertung. Bitte geben Sie eine Zahl zwischen 1 und 5 ein.")
                except ValueError:
                    print("Ungültige Eingabe. Die Bewertung muss eine Zahl sein.")
        
            if titel in filme:
                print(f"Fehler: Film '{titel}' existiert bereits im Katalog.")
                return
        
            filme[titel] = {
                "regisseur": regisseur,
                "jahr": jahr,
                "genre": genre,
                "bewertung": bewertung
            }
            print(f"Film '{titel}' wurde hinzugefügt.")
        
        def film_suchen():
            print("\n--- Film suchen ---")
            suchbegriff = input("Geben Sie einen Suchbegriff für den Titel ein: ").lower()
            gefundene_filme = {}
        
            for titel, details in filme.items():
                if suchbegriff in titel.lower():
                    gefundene_filme[titel] = details
        
            if not gefundene_filme:
                print(f"Keine Filme gefunden, die '{suchbegriff}' im Titel enthalten.")
                return
        
            print(f"\n--- Gefundene Filme für '{suchbegriff}' ---")
            for titel, details in gefundene_filme.items():
                print(f"Titel: {titel}")
                print(f"  Regisseur: {details.get('regisseur', 'N/A')}")
                print(f"  Jahr: {details.get('jahr', 'N/A')}")
                print(f"  Genre: {details.get('genre', 'N/A')}")
                print(f"  Bewertung: {details.get('bewertung', 'N/A')}")
                print("-----------------------")
        
        def film_loeschen():
            print("\n--- Film löschen ---")
            titel_zu_loeschen = input("Titel des zu löschenden Films: ")
            if titel_zu_loeschen in filme:
                del filme[titel_zu_loeschen]
                print(f"Film '{titel_zu_loeschen}' wurde aus dem Katalog entfernt.")
            else:
                print(f"Fehler: Film '{titel_zu_loeschen}' nicht im Katalog gefunden.")
        
        def katalog_speichern():
            try:
                with open(DATEINAME, 'w', encoding='utf-8') as f:
                    json.dump(filme, f, indent=4, ensure_ascii=False)
                print(f"Katalog erfolgreich in '{DATEINAME}' gespeichert.")
            except IOError as e:
                print(f"Fehler beim Speichern des Katalogs: {e}")
        
        def katalog_laden():
            global filme
            try:
                with open(DATEINAME, 'r', encoding='utf-8') as f:
                    filme = json.load(f)
                print(f"Katalog erfolgreich aus '{DATEINAME}' geladen.")
            except FileNotFoundError:
                print("Keine vorhandene Katalogdatei gefunden. Starte mit leerem Katalog.")
                filme = {}
            except json.JSONDecodeError as e:
                print(f"Fehler beim Laden des Katalogs (ungültiges JSON): {e}. Starte mit leerem Katalog.")
                filme = {}
            except Exception as e:
                print(f"Ein unerwarteter Fehler beim Laden ist aufgetreten: {e}. Starte mit leerem Katalog.")
                filme = {}
        
        def zeige_menue():
            print("\n--- Filmkatalog Menü ---")
            print("1. Film hinzufügen")
            print("2. Filme anzeigen")
            print("3. Film suchen")
            print("4. Film löschen")
            print("5. Beenden")
            print("------------------------")
        
        def main():
            katalog_laden()
            while True:
                zeige_menue()
                wahl = input("Ihre Wahl: ")
        
                if wahl == '1':
                    film_hinzufuegen()
                elif wahl == '2':
                    filme_anzeigen()
                elif wahl == '3':
                    film_suchen()
                elif wahl == '4':
                    film_loeschen()
                elif wahl == '5':
                    katalog_speichern()
                    print("Programm wird beendet. Auf Wiedersehen!")
                    break
                else:
                    print("Ungültige Eingabe. Bitte versuchen Sie es erneut.")
        
        if __name__ == "__main__":
            main()
        
        ```
        
3. **Testen (im Terminal):**
    - Führe das Skript aus: `python filmkatalog.py`
    - Versuche, einen Film hinzuzufügen. Gib für das Jahr Text ein (z.B. "abc") und beobachte die Fehlermeldung. Gib dann eine gültige Zahl ein.
    - Gib für die Bewertung eine Zahl außerhalb des Bereichs (z.B. "0" oder "6") oder Text ein. Beobachte die Fehlermeldung. Gib dann eine gültige Zahl ein.
4. **Änderungen zum Staging hinzufügen:**
    
    ```bash
    git add filmkatalog.py
    
    ```
    
5. **Commit erstellen:**
    
    ```bash
    git commit -m "CHORE: Eingabevalidierung und Fehlerbehandlung verbessert"
    
    ```
    
6. **Branch pushen:**
    
    ```bash
    git push -u origin chore/validierung-fehlerbehandlung
    
    ```
    
7. **Merge in `main` (nach Absprache):**
    - `git checkout main`
    - `git pull`
    - `git merge chore/validierung-fehlerbehandlung`
    - `git push`
    - `git branch -d chore/validierung-fehlerbehandlung`
    - `git push origin --delete chore/validierung-fehlerbehandlung`

### TICKET-009: Code-Dokumentation (Docstrings & Kommentare)

**Beschreibung:**
Füge Docstrings zu allen Funktionen und Modulen hinzu, die deren Zweck, Parameter und Rückgabewerte beschreiben. Ergänze außerdem sinnvolle Inline-Kommentare, um komplexe Logik zu erklären und die Lesbarkeit des Codes zu verbessern.

**Python-Grundlagen (Fokus):**

- Docstrings (PEP 257)
- Inline-Kommentare
- Code-Lesbarkeit und Best Practices

**Git-Schritte:**

1. **Branch erstellen:**
    
    ```bash
    git checkout -b chore/code-dokumentation
    
    ```
    
2. **Code implementieren (`filmkatalog.py`):**
    - Öffne die Datei `filmkatalog.py` in VS Code.
    - **Modul-Docstring:** Füge am Anfang der Datei `filmkatalog.py` (direkt unter `import json`) einen Docstring hinzu, der den allgemeinen Zweck des Skripts beschreibt.
        
        ```python
        """
        Ein einfaches Python-Programm zur Verwaltung eines Filmkatalogs.
        Es ermöglicht das Hinzufügen, Anzeigen, Suchen und Löschen von Filmen
        sowie das Speichern und Laden des Katalogs in/aus einer JSON-Datei.
        """
        
        ```
        
    - **Funktions-Docstrings:** Füge für jede Funktion (`filme_anzeigen`, `film_hinzufuegen`, `film_suchen`, `film_loeschen`, `katalog_speichern`, `katalog_laden`, `zeige_menue`, `main`) einen Docstring hinzu. Platziere den Docstring direkt unter der `def`Zeile der Funktion.
        - **Beispiel für `filme_anzeigen()`:**
            
            ```python
            def filme_anzeigen():
                """
                Zeigt alle Filme im aktuellen Katalog an.
                Gibt eine Meldung aus, wenn der Katalog leer ist.
                """
                if not filme:
                    print("Der Katalog ist leer.")
                    return
                # ... (restlicher Code der Funktion) ...
            
            ```
            
        - **Beispiel für `film_hinzufuegen()` (mit Parametern/Rückgabe, auch wenn implizit):**
            
            ```python
            def film_hinzufuegen():
                """
                Fügt einen neuen Film zum Katalog hinzu.
                Fragt den Benutzer nach Titel, Regisseur, Jahr, Genre und Bewertung.
                Validiert die Eingaben für Jahr und Bewertung.
                Verhindert das Hinzufügen von Filmen mit bereits existierendem Titel.
                """
                # ... (restlicher Code der Funktion) ...
            
            ```
            
        - Gehe jede Funktion durch und füge einen passenden Docstring hinzu.
    - **Inline-Kommentare:** Füge kurze, erklärende Kommentare an komplexen oder nicht sofort ersichtlichen Code-Stellen hinzu.
        - **Beispiel in `film_hinzufuegen()`:**
            
            ```python
            # Validierung für das Jahr: Schleife, bis eine gültige Zahl eingegeben wird
            while True:
                jahr_str = input("Erscheinungsjahr des Films: ")
                try:
                    jahr = int(jahr_str) # Versuche, die Eingabe in eine Ganzzahl umzuwandeln
                    break # Wenn erfolgreich, beende die Schleife
                except ValueError:
                    print("Ungültige Eingabe. Das Jahr muss eine Zahl sein.")
            
            ```
            
        - Füge ähnliche Kommentare an anderen Stellen hinzu, wo die Logik komplexer ist (z.B. in `katalog_laden()` bei den `try-except`Blöcken).
    - **Dein `filmkatalog.py` sollte jetzt so aussehen (Beachte die Docstrings und Kommentare):**
        
        ```python
        import json
        
        """
        Ein einfaches Python-Programm zur Verwaltung eines Filmkatalogs.
        Es ermöglicht das Hinzufügen, Anzeigen, Suchen und Löschen von Filmen
        sowie das Speichern und Laden des Katalogs in/aus einer JSON-Datei.
        """
        
        # Globale Variable zum Speichern der Filmdaten
        # Schlüssel: Filmtitel (String), Wert: Dictionary mit Filmdetails
        filme = {}
        DATEINAME = "filme.json" # Dateiname für die Speicherung des Katalogs
        
        def filme_anzeigen():
            """
            Zeigt alle Filme im aktuellen Katalog an.
            Gibt eine Meldung aus, wenn der Katalog leer ist.
            """
            if not filme:
                print("Der Katalog ist leer.")
                return
        
            print("\n--- Dein Filmkatalog ---")
            # Iteriere durch das Filme-Dictionary und zeige Details an
            for titel, details in filme.items():
                print(f"Titel: {titel}")
                # Verwende .get() mit Standardwert 'N/A', falls ein Detail fehlt (für ältere Einträge)
                print(f"  Regisseur: {details.get('regisseur', 'N/A')}")
                print(f"  Jahr: {details.get('jahr', 'N/A')}")
                print(f"  Genre: {details.get('genre', 'N/A')}")
                print(f"  Bewertung: {details.get('bewertung', 'N/A')}")
                print("-----------------------")
        
        def film_hinzufuegen():
            """
            Fügt einen neuen Film zum Katalog hinzu.
            Fragt den Benutzer nach Titel, Regisseur, Jahr, Genre und Bewertung.
            Validiert die Eingaben für Jahr und Bewertung.
            Verhindert das Hinzufügen von Filmen mit bereits existierendem Titel.
            """
            print("\n--- Film hinzufügen ---")
            titel = input("Titel des Films: ")
            regisseur = input("Regisseur des Films: ")
        
            # Validierung für das Jahr: Schleife, bis eine gültige Zahl eingegeben wird
            while True:
                jahr_str = input("Erscheinungsjahr des Films: ")
                try:
                    jahr = int(jahr_str)
                    break
                except ValueError:
                    print("Ungültige Eingabe. Das Jahr muss eine Zahl sein.")
        
            genre = input("Genre des Films: ")
        
            # Validierung für die Bewertung: Schleife, bis eine Zahl zwischen 1 und 5 eingegeben wird
            while True:
                bewertung_str = input("Bewertung (1-5 Sterne): ")
                try:
                    bewertung = int(bewertung_str)
                    if 1 <= bewertung <= 5:
                        break
                    else:
                        print("Ungültige Bewertung. Bitte geben Sie eine Zahl zwischen 1 und 5 ein.")
                except ValueError:
                    print("Ungültige Eingabe. Die Bewertung muss eine Zahl sein.")
        
            # Überprüfe, ob der Titel bereits existiert, um Duplikate zu vermeiden
            if titel in filme:
                print(f"Fehler: Film '{titel}' existiert bereits im Katalog.")
                return
        
            # Speichere die Filmdetails als verschachteltes Dictionary
            filme[titel] = {
                "regisseur": regisseur,
                "jahr": jahr,
                "genre": genre,
                "bewertung": bewertung
            }
            print(f"Film '{titel}' wurde hinzugefügt.")
        
        def film_suchen():
            """
            Sucht Filme im Katalog basierend auf einem Teil des Titels.
            Zeigt alle passenden Filme mit ihren Details an.
            """
            print("\n--- Film suchen ---")
            # Suchbegriff in Kleinbuchstaben umwandeln für case-insensitive Suche
            suchbegriff = input("Geben Sie einen Suchbegriff für den Titel ein: ").lower()
            gefundene_filme = {}
        
            # Iteriere durch alle Filme im Katalog
            for titel, details in filme.items():
                # Überprüfe, ob der Suchbegriff im Titel (kleingeschrieben) enthalten ist
                if suchbegriff in titel.lower():
                    gefundene_filme[titel] = details
        
            # Wenn keine Filme gefunden wurden
            if not gefundene_filme:
                print(f"Keine Filme gefunden, die '{suchbegriff}' im Titel enthalten.")
                return
        
            print(f"\n--- Gefundene Filme für '{suchbegriff}' ---")
            # Zeige die Details der gefundenen Filme an
            for titel, details in gefundene_filme.items():
                print(f"Titel: {titel}")
                print(f"  Regisseur: {details.get('regisseur', 'N/A')}")
                print(f"  Jahr: {details.get('jahr', 'N/A')}")
                print(f"  Genre: {details.get('genre', 'N/A')}")
                print(f"  Bewertung: {details.get('bewertung', 'N/A')}")
                print("-----------------------")
        
        def film_loeschen():
            """
            Löscht einen Film aus dem Katalog anhand seines Titels.
            Gibt eine Fehlermeldung aus, wenn der Film nicht gefunden wird.
            """
            print("\n--- Film löschen ---")
            titel_zu_loeschen = input("Titel des zu löschenden Films: ")
            if titel_zu_loeschen in filme:
                del filme[titel_zu_loeschen] # Entferne den Film aus dem Dictionary
                print(f"Film '{titel_zu_loeschen}' wurde aus dem Katalog entfernt.")
            else:
                print(f"Fehler: Film '{titel_zu_loeschen}' nicht im Katalog gefunden.")
        
        def katalog_speichern():
            """
            Speichert den aktuellen Filmkatalog in einer JSON-Datei.
            Der Dateiname wird durch die globale Variable DATEINAME definiert.
            Behandelt IOError bei Problemen mit der Dateispeicherung.
            """
            try:
                # Öffne die Datei im Schreibmodus ('w') mit UTF-8-Kodierung
                with open(DATEINAME, 'w', encoding='utf-8') as f:
                    # Speichere das 'filme'-Dictionary als JSON in der Datei
                    # indent=4 für schöne Formatierung, ensure_ascii=False für Umlaute
                    json.dump(filme, f, indent=4, ensure_ascii=False)
                print(f"Katalog erfolgreich in '{DATEINAME}' gespeichert.")
            except IOError as e:
                print(f"Fehler beim Speichern des Katalogs: {e}")
        
        def katalog_laden():
            """
            Lädt den Filmkatalog aus einer JSON-Datei.
            Der Dateiname wird durch die globale Variable DATEINAME definiert.
            Initialisiert den Katalog neu, wenn die Datei nicht gefunden wird
            oder ungültiges JSON enthält.
            """
            global filme # Erlaube den Zugriff auf die globale 'filme'-Variable
            try:
                # Versuche, die Datei im Lesemodus ('r') zu öffnen
                with open(DATEINAME, 'r', encoding='utf-8') as f:
                    filme.update(json.load(f)) # Lade die JSON-Daten in das 'filme'-Dictionary
                print(f"Katalog erfolgreich aus '{DATEINAME}' geladen.")
            except FileNotFoundError:
                # Wenn die Datei nicht existiert, ist das normal beim ersten Start
                print("Keine vorhandene Katalogdatei gefunden. Starte mit leerem Katalog.")
                filme.clear() # Leere das Dictionary, falls es Reste enthält
            except json.JSONDecodeError as e:
                # Wenn die Datei existiert, aber kein gültiges JSON enthält
                print(f"Fehler beim Laden des Katalogs (ungültiges JSON): {e}. Starte mit leerem Katalog.")
                filme.clear()
            except Exception as e:
                # Fange alle anderen unerwarteten Fehler ab
                print(f"Ein unerwarteter Fehler beim Laden ist aufgetreten: {e}. Starte mit leerem Katalog.")
                filme.clear()
        
        def zeige_menue():
            """
            Zeigt das Hauptmenü des Filmkatalogs an.
            """
            print("\n--- Filmkatalog Menü ---")
            print("1. Film hinzufügen")
            print("2. Filme anzeigen")
            print("3. Film suchen")
            print("4. Film löschen")
            print("5. Beenden")
            print("------------------------")
        
        def main():
            """
            Die Hauptfunktion des Programms.
            Lädt den Katalog beim Start, zeigt das Menü an und verarbeitet Benutzereingaben.
            Speichert den Katalog beim Beenden.
            """
            katalog_laden() # Katalog beim Start laden
            while True:
                zeige_menue()
                wahl = input("Ihre Wahl: ")
        
                if wahl == '1':
                    film_hinzufuegen()
                elif wahl == '2':
                    filme_anzeigen()
                elif wahl == '3':
                    film_suchen()
                elif wahl == '4':
                    film_loeschen()
                elif wahl == '5':
                    katalog_speichern() # Katalog vor dem Beenden speichern
                    print("Programm wird beendet. Auf Wiedersehen!")
                    break
                else:
                    print("Ungültige Eingabe. Bitte versuchen Sie es erneut.")
        
        # Startet das Hauptprogramm, wenn die Datei direkt ausgeführt wird
        if __name__ == "__main__":
            main()
        
        ```
        
3. **Testen (im Terminal):**
    - Führe das Skript aus: `python filmkatalog.py`
    - Überprüfe, ob das Programm weiterhin korrekt funktioniert.
    - Die Hauptaufgabe des Tests ist hier die Überprüfung der **Lesbarkeit** des Codes. Lies den Code durch und versuche, die Logik nur anhand der Kommentare und Docstrings zu verstehen.
4. **Änderungen zum Staging hinzufügen:**
    
    ```bash
    git add filmkatalog.py
    
    ```
    
5. **Commit erstellen:**
    
    ```bash
    git commit -m "CHORE: Code mit Docstrings und Kommentaren dokumentiert"
    
    ```
    
6. **Branch pushen:**
    
    ```bash
    git push -u origin chore/code-dokumentation
    
    ```
    
7. **Merge in `main` (nach Absprache):**
    - `git checkout main`
    - `git pull`
    - `git merge chore/code-dokumentation`
    - `git push`
    - `git branch -d chore/code-dokumentation`
    - `git push origin --delete chore/code-dokumentation`

## Abschluss und Reflexion

Nachdem du alle Tickets bearbeitet hast, solltest du einen funktionsfähigen Filmkatalog haben.

- **Überprüfe deinen Git-Verlauf:** `git log --oneline --graph --all`
    - Siehst du, wie die Branches erstellt, bearbeitet und dann wieder in `main` gemergt wurden?
    - Sind deine Commit-Nachrichten aussagekräftig?
- **Reflektiere:**
    - Was war die größte Herausforderung bei Git?
    - Wie hat dir die Arbeit mit Branches geholfen, den Überblick zu behalten?
    - Welche Vorteile siehst du jetzt in der Versionskontrolle?

Viel Erfolg und Spaß beim Programmieren und Versionieren!