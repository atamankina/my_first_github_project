# Git & Python Lernprojekt: Dein Kundenmanagement-System (CRM) - Mit Code-Lücken

Willkommen zu deinem nächsten kombinierten Lernprojekt! In diesem Szenario wirst du ein einfaches Kundenmanagement-System (CRM) in Python programmieren und dabei Git und GitHub nutzen, um deine Arbeit zu versionieren und jeden Entwicklungsschritt sauber zu dokumentieren.

Das Projekt ist in einzelne "Tickets" unterteilt. Jedes Ticket repräsentiert eine Aufgabe, die du implementieren und dann mit Git in einem eigenen Branch verwalten wirst. So lernst du, wie man inkrementell arbeitet und sinnvolle Commits erstellt.

## Projektübersicht: Das Kundenmanagement-System

Du wirst ein Python-Programm erstellen, das dir erlaubt, Kunden zu deiner Datenbank hinzuzufügen, sie anzuzeigen, zu suchen, zu aktualisieren und zu löschen. Die Kundendaten werden lokal gespeichert und geladen.

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
    mkdir CRMProjekt
    cd CRMProjekt
    
    ```
    
5. **Initialisiere ein Git-Repository:**
    
    ```bash
    git init
    
    ```
    
6. **Erstelle die Hauptdatei für dein Programm:**
    - Klicke im VS Code Explorer auf "New File" und nenne die Datei `crm.py`.
    - Füge einen Kommentar hinzu: `# Dein Kundenmanagement-System`
    - Speichere die Datei.
7. **Füge die Datei zum Staging hinzu und mache den ersten Commit:**
    
    ```bash
    git add crm.py
    git commit -m "Initialer Commit: Leere crm.py erstellt"
    
    ```
    
8. **Erstelle ein neues Repository auf GitHub:**
    - Gehe zu [github.com](https://github.com/) und melde dich an.
    - Klicke auf "+" > "New repository".
    - Nenne es `CRMProjekt`.
    - Wähle "Public" oder "Private".
    - **WICHTIG:** Wähle **NICHT** die Optionen zum Initialisieren des Repositories mit einer README, .gitignore oder Lizenz.
    - Klicke auf "Create repository".
9. **Verbinde dein lokales Repo mit GitHub und pushe:**
    - Kopiere die URL von GitHub (z.B. `https://github.com/DeinBenutzername/CRMProjekt.git`).
    - Im VS Code Terminal:
        
        ```bash
        git remote add origin https://github.com/DeinBenutzername/CRMProjekt.git
        git branch -M main
        git push -u origin main
        
        ```
        
    - Überprüfe auf GitHub, ob deine `crm.py`Datei hochgeladen wurde.

## Die Tickets: Schritt für Schritt zum CRM

Arbeite jedes Ticket einzeln ab. Für jedes Ticket wirst du einen neuen Git-Branch erstellen, deine Änderungen committen und den Branch dann in den `main`-Branch mergen.

### TICKET-001: Grundgerüst und Kundenliste anzeigen

**Beschreibung:**
Implementiere ein leeres Python-Dictionary, das als Speicher für deine Kunden dient. Füge eine Funktion hinzu, die alle aktuell im CRM vorhandenen Kunden anzeigt.

**Python-Grundlagen (Fokus):**

- Variablen, Dictionaries
- Funktionsdefinition (`def`)
- `print()`Anweisungen

**Akzeptanzkriterien:**

- Das Programm startet ohne Fehler.
- Die Funktion `kunden_anzeigen()` gibt die Meldung "Der Katalog ist leer." aus, wenn noch keine Kunden vorhanden sind.
- Die Funktion `kunden_anzeigen()` kann später die Details von hinzugefügten Kunden korrekt formatieren und anzeigen.

**Git-Schritte:**

1. **Branch erstellen:** Erstelle einen neuen Branch für dieses Ticket.
    
    ```bash
    git checkout -b feature/kunden-liste
    
    ```
    
2. **Code implementieren (`crm.py`):**
    - Öffne die Datei `crm.py` in VS Code.
    - **Füge die globale Variable `kunden` hinzu:** Direkt unter dem Kommentar `# Dein Kundenmanagement-System` füge diese Zeile ein:
        
        ```python
        # TODO: Definiere hier ein leeres Dictionary namens 'kunden'
        # Es soll als Speicher für deine Kunden dienen.
        # Beispiel: kunden = {}
        
        ```
        
    - **Definiere die Funktion `kunden_anzeigen()`:** Füge die folgenden Zeilen unter der `kunden`Definition ein:
        
        ```python
        def kunden_anzeigen():
            # TODO: Überprüfe, ob das 'kunden'-Dictionary leer ist.
            # Wenn es leer ist, gib eine entsprechende Nachricht aus und beende die Funktion.
            # Beispiel: if not kunden: print("Der Katalog ist leer."); return
        
            print("\n--- Deine Kundenliste ---")
            # TODO: Iteriere über alle Kunden im 'kunden'-Dictionary.
            # Für jeden Kunden sollst du den Namen und die Details ausgeben.
            # Verwende die .items()-Methode, um Schlüssel (Name) und Wert (Details-Dictionary) zu erhalten.
            # Beispiel: for name, details in kunden.items():
            #   print(f"Name: {name}")
            #   print(f"  E-Mail: {details.get('email', 'N/A')}")
            #   print(f"  Telefon: {details.get('telefon', 'N/A')}")
            #   print("-------------------------")
        
        # Test der Funktion (diese Zeile wird später durch ein Menü ersetzt)
        # kunden_anzeigen()
        
        ```
        
    - **Dein `crm.py` sollte jetzt so aussehen (mit deinen Implementierungen):**
        
        ```python
        # Dein Kundenmanagement-System
        
        kunden = {} # Ein Dictionary zum Speichern der Kunden. Schlüssel: Kundenname, Wert: Dictionary mit Details
        
        def kunden_anzeigen():
            if not kunden:
                print("Der Katalog ist leer.")
                return
        
            print("\n--- Deine Kundenliste ---")
            for name, details in kunden.items():
                print(f"Name: {name}")
                print(f"  E-Mail: {details.get('email', 'N/A')}")
                print(f"  Telefon: {details.get('telefon', 'N/A')}")
                print("-------------------------")
        
        # Test der Funktion (wird später durch ein Menü ersetzt)
        # kunden_anzeigen()
        
        ```
        
3. **Testen (im Terminal):**
    - Füge am Ende der Datei `crm.py` vorübergehend die Zeile `kunden_anzeigen()` hinzu (entferne das `#` davor).
    - Führe das Skript aus: `python crm.py`
    - Erwarte die Ausgabe "Der Katalog ist leer.".
    - **Wichtig:** Entferne die Testzeile `kunden_anzeigen()` wieder (oder kommentiere sie aus), bevor du committest.
4. **Änderungen zum Staging hinzufügen:**
    
    ```bash
    git add crm.py
    
    ```
    
5. **Commit erstellen:**
    
    ```bash
    git commit -m "FEAT: Funktion zum Anzeigen aller Kunden hinzugefügt"
    
    ```
    
6. **Branch pushen:**
    
    ```bash
    git push -u origin feature/kunden-liste
    
    ```
    
7. **Merge in `main` (nach Absprache mit Lehrer/Mitschülern):**
    - Wechsle zum `main`Branch: `git checkout main`
    - Hole die neuesten Änderungen: `git pull`
    - Merge den Feature-Branch: `git merge feature/kunden-liste`
    - Pushe den `main`Branch: `git push`
    - Lösche den lokalen Feature-Branch: `git branch -d feature/kunden-liste`
    - (Optional) Lösche den Remote-Branch: `git push origin --delete feature/kunden-liste`

### TICKET-002: Kunden hinzufügen

**Beschreibung:**
Implementiere eine Funktion, die es dem Benutzer erlaubt, einen neuen Kunden mit Namen, E-Mail und Telefonnummer zum Katalog hinzuzufügen.

**Python-Grundlagen (Fokus):**

- Funktionsparameter
- `input()` für Benutzereingaben
- Dictionary-Manipulation (Hinzufügen von Einträgen)
- Bedingte Anweisungen (`if`)

**Akzeptanzkriterien:**

- Ein neuer Kunde kann mit Name, E-Mail und Telefonnummer erfolgreich hinzugefügt werden.
- Wenn versucht wird, einen Kunden mit einem bereits existierenden Namen hinzuzufügen, wird eine Fehlermeldung ausgegeben und der Kunde nicht hinzugefügt.
- Nach dem Hinzufügen wird eine Bestätigungsnachricht angezeigt.

**Git-Schritte:**

1. **Branch erstellen:**
    
    ```bash
    git checkout -b feature/kunde-hinzufuegen
    
    ```
    
2. **Code implementieren (`crm.py`):**
    - Öffne die Datei `crm.py` in VS Code.
    - **Füge die Funktion `kunde_hinzufuegen()` hinzu:** Füge die folgenden Zeilen **nach** der `kunden_anzeigen()` Funktion ein:
        
        ```python
        def kunde_hinzufuegen():
            print("\n--- Kunden hinzufügen ---")
            # TODO: Frage den Benutzer nach dem Namen des Kunden und speichere ihn in einer Variable 'name'.
            # Beispiel: name = input("Name des Kunden: ")
        
            # TODO: Frage den Benutzer nach der E-Mail des Kunden und speichere sie in einer Variable 'email'.
        
            # TODO: Frage den Benutzer nach der Telefonnummer des Kunden und speichere sie in einer Variable 'telefon'.
        
            # TODO: Überprüfe, ob der 'name' bereits als Schlüssel im 'kunden'-Dictionary existiert.
            # Wenn ja, gib eine Fehlermeldung aus und beende die Funktion (`return`).
            # Beispiel: if name in kunden: print(f"Fehler: Kunde '{name}' existiert bereits im Katalog."); return
        
            # TODO: Füge den neuen Kunden zum 'kunden'-Dictionary hinzu.
            # Der Schlüssel soll der 'name' sein. Der Wert soll ein neues Dictionary sein,
            # das 'email' und 'telefon' als Schlüssel-Wert-Paare enthält.
            # Beispiel: kunden[name] = {"email": email, "telefon": telefon}
        
            # TODO: Gib eine Bestätigungsnachricht aus, dass der Kunde hinzugefügt wurde.
            # Beispiel: print(f"Kunde '{name}' wurde hinzugefügt.")
        
        # Test der Funktion (wird später durch ein Menü ersetzt)
        # kunde_hinzufuegen()
        # kunden_anzeigen()
        
        ```
        
    - **Dein `crm.py` sollte jetzt so aussehen (mit deinen Implementierungen):**
        
        ```python
        # Dein Kundenmanagement-System
        
        kunden = {} # Ein Dictionary zum Speichern der Kunden. Schlüssel: Kundenname, Wert: Dictionary mit Details
        
        def kunden_anzeigen():
            if not kunden:
                print("Der Katalog ist leer.")
                return
        
            print("\n--- Deine Kundenliste ---")
            for name, details in kunden.items():
                print(f"Name: {name}")
                print(f"  E-Mail: {details.get('email', 'N/A')}")
                print(f"  Telefon: {details.get('telefon', 'N/A')}")
                print("-------------------------")
        
        def kunde_hinzufuegen():
            print("\n--- Kunden hinzufügen ---")
            name = input("Name des Kunden: ")
            email = input("E-Mail des Kunden: ")
            telefon = input("Telefonnummer des Kunden: ")
        
            if name in kunden:
                print(f"Fehler: Kunde '{name}' existiert bereits im Katalog.")
                return
        
            kunden[name] = {
                "email": email,
                "telefon": telefon
            }
            print(f"Kunde '{name}' wurde hinzugefügt.")
        
        # Test der Funktionen (werden später durch ein Menü ersetzt)
        # kunde_hinzufuegen()
        # kunden_anzeigen()
        
        ```
        
3. **Testen (im Terminal):**
    - Füge am Ende der Datei vorübergehend die Zeilen `kunde_hinzufuegen()` und danach `kunden_anzeigen()` hinzu (entferne die `#` davor).
    - Führe das Skript aus: `python crm.py`
    - Gib Kundendaten ein (z.B. Name: "Max Mustermann", E-Mail: "max@example.com", Telefon: "0123456789") und überprüfe, ob der Kunde korrekt angezeigt wird.
    - Versuche, denselben Kunden noch einmal hinzuzufügen, um die Fehlerbehandlung zu testen.
    - **Wichtig:** Entferne die Testzeilen wieder (oder kommentiere sie aus), bevor du committest.
4. **Änderungen zum Staging hinzufügen:**
    
    ```bash
    git add crm.py
    
    ```
    
5. **Commit erstellen:**
    
    ```bash
    git commit -m "FEAT: Funktion zum Hinzufügen von Kunden implementiert"
    
    ```
    
6. **Branch pushen:**
    
    ```bash
    git push -u origin feature/kunde-hinzufuegen
    
    ```
    
7. **Merge in `main` (nach Absprache):**
    - `git checkout main`
    - `git pull`
    - `git merge feature/kunde-hinzufuegen`
    - `git push`
    - `git branch -d feature/kunde-hinzufuegen`
    - `git push origin --delete feature/kunde-hinzufuegen`

### TICKET-003: Interaktives Menü

**Beschreibung:**
Erstelle ein einfaches Textmenü, das dem Benutzer erlaubt, zwischen den Funktionen "Kunden hinzufügen" und "Kunden anzeigen" zu wählen. Das Menü soll in einer Schleife laufen, bis der Benutzer das Programm beendet.

**Python-Grundlagen (Fokus):**

- `while`Schleifen
- `if`/`elif`/`else`Anweisungen
- Endlosschleifen mit `break`
- Funktionsaufrufe
- `if __name__ == "__main__":` Block

**Akzeptanzkriterien:**

- Beim Start des Programms wird das Menü angezeigt.
- Der Benutzer kann eine Zahl eingeben, um eine Funktion auszuwählen.
- Die Funktionen "Kunden hinzufügen" und "Kunden anzeigen" werden korrekt aufgerufen.
- Die Option zum Beenden des Programms funktioniert.
- Ungültige Menüeinträge führen zu einer Fehlermeldung und das Menü wird erneut angezeigt.

**Git-Schritte:**

1. **Branch erstellen:**
    
    ```bash
    git checkout -b feature/interaktives-menue
    
    ```
    
2. **Code implementieren (`crm.py`):**
    - Öffne die Datei `crm.py` in VS Code.
    - **Füge die Funktion `zeige_menue()` hinzu:** Füge diese Funktion **nach** `kunde_hinzufuegen()` ein:
        
        ```python
        def zeige_menue():
            # TODO: Gib die Menüoptionen aus.
            # Beispiel: print("\n--- CRM Menü ---")
            #           print("1. Kunde hinzufügen")
            #           print("2. Kunden anzeigen")
            #           print("3. Beenden")
            #           print("----------------")
            pass # Platzhalter, entfernen, wenn implementiert
        
        ```
        
    - **Füge die Hauptfunktion `main()` hinzu:** Diese Funktion wird die Menü-Logik enthalten. Füge sie **nach** `zeige_menue()` ein:
        
        ```python
        def main():
            # TODO: Erstelle eine Endlosschleife (while True).
            # Innerhalb der Schleife:
            # 1. Rufe zeige_menue() auf.
            # 2. Frage den Benutzer nach seiner Wahl (input()).
            # 3. Verwende if/elif/else, um die Wahl zu verarbeiten:
            #    - '1' soll kunde_hinzufuegen() aufrufen.
            #    - '2' soll kunden_anzeigen() aufrufen.
            #    - '3' soll eine Abschiedsnachricht ausgeben und die Schleife beenden (break).
            #    - Bei ungültiger Eingabe eine Fehlermeldung ausgeben.
            pass # Platzhalter, entfernen, wenn implementiert
        
        ```
        
    - **Füge den Startpunkt des Programms hinzu:** Ersetze alle vorhandenen Testzeilen am Ende der Datei (wie `# kunde_hinzufuegen()`) durch diesen Standard-Python-Block. Dieser Block stellt sicher, dass `main()` nur aufgerufen wird, wenn das Skript direkt ausgeführt wird.
        
        ```python
        # Startet das Hauptprogramm, wenn die Datei direkt ausgeführt wird
        if __name__ == "__main__":
            # TODO: Rufe hier die main() Funktion auf.
            pass # Platzhalter, entfernen, wenn implementiert
        
        ```
        
    - **Dein `crm.py` sollte jetzt so aussehen (mit deinen Implementierungen):**
        
        ```python
        # Dein Kundenmanagement-System
        
        kunden = {} # Ein Dictionary zum Speichern der Kunden. Schlüssel: Kundenname, Wert: Dictionary mit Details
        
        def kunden_anzeigen():
            if not kunden:
                print("Der Katalog ist leer.")
                return
        
            print("\n--- Deine Kundenliste ---")
            for name, details in kunden.items():
                print(f"Name: {name}")
                print(f"  E-Mail: {details.get('email', 'N/A')}")
                print(f"  Telefon: {details.get('telefon', 'N/A')}")
                print("-------------------------")
        
        def kunde_hinzufuegen():
            print("\n--- Kunden hinzufügen ---")
            name = input("Name des Kunden: ")
            email = input("E-Mail des Kunden: ")
            telefon = input("Telefonnummer des Kunden: ")
        
            if name in kunden:
                print(f"Fehler: Kunde '{name}' existiert bereits im Katalog.")
                return
        
            kunden[name] = {
                "email": email,
                "telefon": telefon
            }
            print(f"Kunde '{name}' wurde hinzugefügt.")
        
        def zeige_menue():
            print("\n--- CRM Menü ---")
            print("1. Kunde hinzufügen")
            print("2. Kunden anzeigen")
            print("3. Beenden")
            print("----------------")
        
        def main():
            while True:
                zeige_menue()
                wahl = input("Ihre Wahl: ")
        
                if wahl == '1':
                    kunde_hinzufuegen()
                elif wahl == '2':
                    kunden_anzeigen()
                elif wahl == '3':
                    print("Programm wird beendet. Auf Wiedersehen!")
                    break
                else:
                    print("Ungültige Eingabe. Bitte versuchen Sie es erneut.")
        
        if __name__ == "__main__":
            main()
        
        ```
        
3. **Testen (im Terminal):**
    - Führe das Skript aus: `python crm.py`
    - Teste alle Menüpunkte: Kunden hinzufügen, anzeigen, beenden. Überprüfe auch ungültige Eingaben.
4. **Änderungen zum Staging hinzufügen:**
    
    ```bash
    git add crm.py
    
    ```
    
5. **Commit erstellen:**
    
    ```bash
    git commit -m "FEAT: Interaktives Menü für das CRM hinzugefügt"
    
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

### TICKET-004: Kunden suchen

**Beschreibung:**
Füge eine Funktion hinzu, die es dem Benutzer erlaubt, Kunden nach einem Teil des Namens oder der E-Mail-Adresse zu suchen. Die Suche soll alle passenden Kunden anzeigen.

**Python-Grundlagen (Fokus):**

- String-Methoden (`.lower()`, `in`)
- Schleifen zum Iterieren über Dictionaries
- Bedingte Anweisungen (`or` für mehrere Suchkriterien)

**Akzeptanzkriterien:**

- Eine neue Menüoption "Kunden suchen" ist verfügbar.
- Der Benutzer kann einen Suchbegriff eingeben.
- Die Suche findet Kunden, deren Name oder E-Mail den Suchbegriff (case-insensitiv) enthält.
- Alle passenden Kundendetails werden angezeigt.
- Wenn keine Kunden gefunden werden, wird eine entsprechende Meldung ausgegeben.

**Git-Schritte:**

1. **Branch erstellen:**
    
    ```bash
    git checkout -b feature/kunde-suchen
    
    ```
    
2. **Code implementieren (`crm.py`):**
    - Öffne die Datei `crm.py` in VS Code.
    - **Füge die Funktion `kunde_suchen()` hinzu:** Füge diese Funktion **nach** der `kunde_hinzufuegen()` Funktion ein (oder an einer logischen Stelle vor `zeige_menue()`):
        
        ```python
        def kunde_suchen():
            print("\n--- Kunden suchen ---")
            # TODO: Frage den Benutzer nach einem Suchbegriff und wandle ihn in Kleinbuchstaben um.
            # Beispiel: suchbegriff = input("Geben Sie einen Suchbegriff (Name oder E-Mail) ein: ").lower()
        
            # TODO: Erstelle ein leeres Dictionary namens 'gefundene_kunden', um die Ergebnisse zu speichern.
        
            # TODO: Iteriere über alle Kunden im globalen 'kunden'-Dictionary (name, details).
            # Innerhalb der Schleife:
            #   TODO: Überprüfe, ob der 'suchbegriff' im 'name' (kleingeschrieben) ODER in der 'email' (kleingeschrieben) des Kunden enthalten ist.
            #   Tipp: details.get('email', '') stellt sicher, dass es keinen Fehler gibt, wenn 'email' fehlt.
            #   Wenn eine Übereinstimmung gefunden wird, füge den Kunden zum 'gefundene_kunden'-Dictionary hinzu.
        
            # TODO: Wenn 'gefundene_kunden' leer ist, gib eine Nachricht aus, dass keine Kunden gefunden wurden, und beende die Funktion.
        
            # TODO: Gib eine Überschrift für die gefundenen Kunden aus.
        
            # TODO: Iteriere über die 'gefundene_kunden' und gib deren Details aus, ähnlich wie in 'kunden_anzeigen()'.
            pass # Platzhalter, entfernen, wenn implementiert
        
        ```
        
    - **Aktualisiere die `zeige_menue()` Funktion:** Füge eine neue Option "3. Kunde suchen" hinzu und passe die Nummern der folgenden Optionen an.
        
        ```python
        def zeige_menue():
            print("\n--- CRM Menü ---")
            print("1. Kunde hinzufügen")
            print("2. Kunden anzeigen")
            print("3. Kunde suchen") # NEU
            print("4. Beenden")    # NUMMER GEÄNDERT
            print("----------------")
        
        ```
        
    - **Aktualisiere die `main()` Funktion:** Füge einen `elif`Block hinzu, um die neue Option "3" zu verarbeiten, und passe die Nummer für "Beenden" an.
        
        ```python
        def main():
            while True:
                zeige_menue()
                wahl = input("Ihre Wahl: ")
        
                if wahl == '1':
                    kunde_hinzufuegen()
                elif wahl == '2':
                    kunden_anzeigen()
                elif wahl == '3': # NEU
                    kunde_suchen()
                elif wahl == '4': # NUMMER GEÄNDERT
                    print("Programm wird beendet. Auf Wiedersehen!")
                    break
                else:
                    print("Ungültige Eingabe. Bitte versuchen Sie es erneut.")
        
        ```
        
    - **Dein `crm.py` sollte jetzt so aussehen (mit deinen Implementierungen):**
        
        ```python
        # Dein Kundenmanagement-System
        
        kunden = {} # Ein Dictionary zum Speichern der Kunden. Schlüssel: Kundenname, Wert: Dictionary mit Details
        
        def kunden_anzeigen():
            if not kunden:
                print("Der Katalog ist leer.")
                return
        
            print("\n--- Deine Kundenliste ---")
            for name, details in kunden.items():
                print(f"Name: {name}")
                print(f"  E-Mail: {details.get('email', 'N/A')}")
                print(f"  Telefon: {details.get('telefon', 'N/A')}")
                print("-------------------------")
        
        def kunde_hinzufuegen():
            print("\n--- Kunden hinzufügen ---")
            name = input("Name des Kunden: ")
            email = input("E-Mail des Kunden: ")
            telefon = input("Telefonnummer des Kunden: ")
        
            if name in kunden:
                print(f"Fehler: Kunde '{name}' existiert bereits im Katalog.")
                return
        
            kunden[name] = {
                "email": email,
                "telefon": telefon
            }
            print(f"Kunde '{name}' wurde hinzugefügt.")
        
        def kunde_suchen():
            print("\n--- Kunden suchen ---")
            suchbegriff = input("Geben Sie einen Suchbegriff (Name oder E-Mail) ein: ").lower()
            gefundene_kunden = {}
        
            for name, details in kunden.items():
                if suchbegriff in name.lower() or suchbegriff in details.get('email', '').lower():
                    gefundene_kunden[name] = details
        
            if not gefundene_kunden:
                print(f"Keine Kunden gefunden, die '{suchbegriff}' im Namen oder in der E-Mail enthalten.")
                return
        
            print(f"\n--- Gefundene Kunden für '{suchbegriff}' ---")
            for name, details in gefundene_kunden.items():
                print(f"Name: {name}")
                print(f"  E-Mail: {details.get('email', 'N/A')}")
                print(f"  Telefon: {details.get('telefon', 'N/A')}")
                print("-------------------------")
        
        def zeige_menue():
            print("\n--- CRM Menü ---")
            print("1. Kunde hinzufügen")
            print("2. Kunden anzeigen")
            print("3. Kunde suchen")
            print("4. Beenden")
            print("----------------")
        
        def main():
            while True:
                zeige_menue()
                wahl = input("Ihre Wahl: ")
        
                if wahl == '1':
                    kunde_hinzufuegen()
                elif wahl == '2':
                    kunden_anzeigen()
                elif wahl == '3':
                    kunde_suchen()
                elif wahl == '4':
                    print("Programm wird beendet. Auf Wiedersehen!")
                    break
                else:
                    print("Ungültige Eingabe. Bitte versuchen Sie es erneut.")
        
        if __name__ == "__main__":
            main()
        
        ```
        
3. **Testen (im Terminal):**
    - Führe das Skript aus: `python crm.py`
    - Füge einige Kunden hinzu (z.B. "Alice Smith", "Bob Johnson").
    - Wähle die neue Suchfunktion im Menü und teste verschiedene Suchbegriffe (z.B. "ali", "john", "example.com", "nichtexistent").
4. **Änderungen zum Staging hinzufügen:**
    
    ```bash
    git add crm.py
    
    ```
    
5. **Commit erstellen:**
    
    ```bash
    git commit -m "FEAT: Funktion zum Suchen von Kunden implementiert"
    
    ```
    
6. **Branch pushen:**
    
    ```bash
    git push -u origin feature/kunde-suchen
    
    ```
    
7. **Merge in `main` (nach Absprache):**
    - `git checkout main`
    - `git pull`
    - `git merge feature/kunde-suchen`
    - `git push`
    - `git branch -d feature/kunde-suchen`
    - `git push origin --delete feature/kunde-suchen`

### TICKET-005: Kunden aktualisieren

**Beschreibung:**
Füge eine Funktion hinzu, die es dem Benutzer erlaubt, die E-Mail-Adresse und/oder die Telefonnummer eines bestehenden Kunden anhand seines Namens zu aktualisieren.

**Python-Grundlagen (Fokus):**

- Dictionary-Zugriff und -Aktualisierung
- Bedingte Anweisungen
- `input()` für optionale Eingaben

**Akzeptanzkriterien:**

- Eine neue Menüoption "Kunden aktualisieren" ist verfügbar.
- Der Benutzer kann den Namen eines bestehenden Kunden eingeben.
- Wenn der Kunde gefunden wird, kann der Benutzer neue E-Mail und/oder Telefonnummer eingeben (leere Eingabe bedeutet keine Änderung).
- Die Kundendaten werden korrekt aktualisiert.
- Wenn der Kunde nicht gefunden wird, wird eine Fehlermeldung ausgegeben.

**Git-Schritte:**

1. **Branch erstellen:**
    
    ```bash
    git checkout -b feature/kunde-aktualisieren
    
    ```
    
2. **Code implementieren (`crm.py`):**
    - Öffne die Datei `crm.py` in VS Code.
    - **Füge die Funktion `kunde_aktualisieren()` hinzu:** Füge diese Funktion **nach** der `kunde_suchen()` Funktion ein:
        
        ```python
        def kunde_aktualisieren():
            print("\n--- Kunden aktualisieren ---")
            # TODO: Frage den Benutzer nach dem Namen des zu aktualisierenden Kunden.
        
            # TODO: Überprüfe, ob der Kunde im 'kunden'-Dictionary existiert.
            # Wenn nicht, gib eine Fehlermeldung aus und beende die Funktion.
        
            # TODO: Zeige die aktuellen Daten des Kunden an (E-Mail und Telefon).
        
            # TODO: Frage nach der neuen E-Mail. Wenn die Eingabe nicht leer ist, aktualisiere die E-Mail des Kunden.
            # Beispiel: neue_email = input("Neue E-Mail (leer lassen für keine Änderung): ")
            # if neue_email: kunden[name_zu_aktualisieren]['email'] = neue_email
        
            # TODO: Frage nach der neuen Telefonnummer. Wenn die Eingabe nicht leer ist, aktualisiere die Telefonnummer des Kunden.
        
            # TODO: Gib eine Bestätigungsnachricht aus, dass der Kunde aktualisiert wurde.
            pass # Platzhalter, entfernen, wenn implementiert
        
        ```
        
    - **Aktualisiere die `zeige_menue()` Funktion:** Füge eine neue Option "4. Kunde aktualisieren" hinzu und passe die Nummer der "Beenden"-Option an.
        
        ```python
        def zeige_menue():
            print("\n--- CRM Menü ---")
            print("1. Kunde hinzufügen")
            print("2. Kunden anzeigen")
            print("3. Kunde suchen")
            print("4. Kunde aktualisieren") # NEU
            print("5. Beenden")           # NUMMER GEÄNDERT
            print("----------------")
        
        ```
        
    - **Aktualisiere die `main()` Funktion:** Füge einen `elif`Block hinzu, um die neue Option "4" zu verarbeiten, und passe die Nummer für "Beenden" an.
        
        ```python
        def main():
            while True:
                zeige_menue()
                wahl = input("Ihre Wahl: ")
        
                if wahl == '1':
                    kunde_hinzufuegen()
                elif wahl == '2':
                    kunden_anzeigen()
                elif wahl == '3':
                    kunde_suchen()
                elif wahl == '4': # NEU
                    kunde_aktualisieren()
                elif wahl == '5': # NUMMER GEÄNDERT
                    print("Programm wird beendet. Auf Wiedersehen!")
                    break
                else:
                    print("Ungültige Eingabe. Bitte versuchen Sie es erneut.")
        
        ```
        
    - **Dein `crm.py` sollte jetzt so aussehen (mit deinen Implementierungen):**
        
        ```python
        # Dein Kundenmanagement-System
        
        kunden = {} # Ein Dictionary zum Speichern der Kunden. Schlüssel: Kundenname, Wert: Dictionary mit Details
        
        def kunden_anzeigen():
            if not kunden:
                print("Der Katalog ist leer.")
                return
        
            print("\n--- Deine Kundenliste ---")
            for name, details in kunden.items():
                print(f"Name: {name}")
                print(f"  E-Mail: {details.get('email', 'N/A')}")
                print(f"  Telefon: {details.get('telefon', 'N/A')}")
                print("-------------------------")
        
        def kunde_hinzufuegen():
            print("\n--- Kunden hinzufügen ---")
            name = input("Name des Kunden: ")
            email = input("E-Mail des Kunden: ")
            telefon = input("Telefonnummer des Kunden: ")
        
            if name in kunden:
                print(f"Fehler: Kunde '{name}' existiert bereits im Katalog.")
                return
        
            kunden[name] = {
                "email": email,
                "telefon": telefon
            }
            print(f"Kunde '{name}' wurde hinzugefügt.")
        
        def kunde_suchen():
            print("\n--- Kunden suchen ---")
            suchbegriff = input("Geben Sie einen Suchbegriff (Name oder E-Mail) ein: ").lower()
            gefundene_kunden = {}
        
            for name, details in kunden.items():
                if suchbegriff in name.lower() or suchbegriff in details.get('email', '').lower():
                    gefundene_kunden[name] = details
        
            if not gefundene_kunden:
                print(f"Keine Kunden gefunden, die '{suchbegriff}' im Namen oder in der E-Mail enthalten.")
                return
        
            print(f"\n--- Gefundene Kunden für '{suchbegriff}' ---")
            for name, details in gefundene_kunden.items():
                print(f"Name: {name}")
                print(f"  E-Mail: {details.get('email', 'N/A')}")
                print(f"  Telefon: {details.get('telefon', 'N/A')}")
                print("-------------------------")
        
        def kunde_aktualisieren():
            print("\n--- Kunden aktualisieren ---")
            name_zu_aktualisieren = input("Name des zu aktualisierenden Kunden: ")
        
            if name_zu_aktualisieren not in kunden:
                print(f"Fehler: Kunde '{name_zu_aktualisieren}' nicht im Katalog gefunden.")
                return
        
            print(f"Aktuelle Daten für {name_zu_aktualisieren}:")
            print(f"  E-Mail: {kunden[name_zu_aktualisieren]['email']}")
            print(f"  Telefon: {kunden[name_zu_aktualisieren]['telefon']}")
        
            neue_email = input("Neue E-Mail (leer lassen für keine Änderung): ")
            neue_telefon = input("Neue Telefonnummer (leer lassen für keine Änderung): ")
        
            if neue_email:
                kunden[name_zu_aktualisieren]['email'] = neue_email
            if neue_telefon:
                kunden[name_zu_aktualisieren]['telefon'] = neue_telefon
        
            print(f"Kunde '{name_zu_aktualisieren}' wurde aktualisiert.")
        
        def zeige_menue():
            print("\n--- CRM Menü ---")
            print("1. Kunde hinzufügen")
            print("2. Kunden anzeigen")
            print("3. Kunde suchen")
            print("4. Kunde aktualisieren")
            print("5. Beenden")
            print("----------------")
        
        def main():
            while True:
                zeige_menue()
                wahl = input("Ihre Wahl: ")
        
                if wahl == '1':
                    kunde_hinzufuegen()
                elif wahl == '2':
                    kunden_anzeigen()
                elif wahl == '3':
                    kunde_suchen()
                elif wahl == '4':
                    kunde_aktualisieren()
                elif wahl == '5':
                    print("Programm wird beendet. Auf Wiedersehen!")
                    break
                else:
                    print("Ungültige Eingabe. Bitte versuchen Sie es erneut.")
        
        if __name__ == "__main__":
            main()
        
        ```
        
3. **Testen (im Terminal):**
    - Führe das Skript aus: `python crm.py`
    - Füge einen Kunden hinzu.
    - Wähle "Kunden aktualisieren", gib den Namen des Kunden ein.
    - Aktualisiere nur die E-Mail, dann nur die Telefonnummer, dann beides.
    - Überprüfe die Änderungen mit "Kunden anzeigen".
    - Versuche, einen nicht existierenden Kunden zu aktualisieren.
4. **Änderungen zum Staging hinzufügen:**
    
    ```bash
    git add crm.py
    
    ```
    
5. **Commit erstellen:**
    
    ```bash
    git commit -m "FEAT: Funktion zum Aktualisieren von Kundendaten implementiert"
    
    ```
    
6. **Branch pushen:**
    
    ```bash
    git push -u origin feature/kunde-aktualisieren
    
    ```
    
7. **Merge in `main` (nach Absprache):**
    - `git checkout main`
    - `git pull`
    - `git merge feature/kunde-aktualisieren`
    - `git push`
    - `git branch -d feature/kunde-aktualisieren`
    - `git push origin --delete feature/kunde-aktualisieren`

### TICKET-006: Kunden löschen

**Beschreibung:**
Implementiere eine Funktion, die es dem Benutzer erlaubt, einen Kunden anhand seines Namens aus dem CRM zu entfernen.

**Python-Grundlagen (Fokus):**

- Dictionary-Methoden (`del`)
- Fehlerbehandlung (Kunde nicht gefunden)

**Akzeptanzkriterien:**

- Eine neue Menüoption "Kunden löschen" ist verfügbar.
- Der Benutzer kann den Namen eines Kunden eingeben.
- Der Kunde wird erfolgreich aus dem Katalog entfernt.
- Wenn der Kunde nicht gefunden wird, wird eine Fehlermeldung ausgegeben.

**Git-Schritte:**

1. **Branch erstellen:**
    
    ```bash
    git checkout -b feature/kunde-loeschen
    
    ```
    
2. **Code implementieren (`crm.py`):**
    - Öffne die Datei `crm.py` in VS Code.
    - **Füge die Funktion `kunde_loeschen()` hinzu:** Füge diese Funktion **nach** der `kunde_aktualisieren()` Funktion ein:
        
        ```python
        def kunde_loeschen():
            print("\n--- Kunden löschen ---")
            # TODO: Frage den Benutzer nach dem Namen des zu löschenden Kunden.
        
            # TODO: Überprüfe, ob der Kunde im 'kunden'-Dictionary existiert.
            # Wenn ja, entferne den Kunden aus dem Dictionary und gib eine Bestätigung aus.
            # Tipp: Verwende 'del kunden[name_zu_loeschen]'
        
            # Wenn nein, gib eine Fehlermeldung aus.
            pass # Platzhalter, entfernen, wenn implementiert
        
        ```
        
    - **Aktualisiere die `zeige_menue()` Funktion:** Füge eine neue Option "5. Kunde löschen" hinzu und passe die Nummer der "Beenden"-Option an.
        
        ```python
        def zeige_menue():
            print("\n--- CRM Menü ---")
            print("1. Kunde hinzufügen")
            print("2. Kunden anzeigen")
            print("3. Kunde suchen")
            print("4. Kunde aktualisieren")
            print("5. Kunde löschen") # NEU
            print("6. Beenden")      # NUMMER GEÄNDERT
            print("----------------")
        
        ```
        
    - **Aktualisiere die `main()` Funktion:** Füge einen `elif`Block hinzu, um die neue Option "5" zu verarbeiten, und passe die Nummer für "Beenden" an.
        
        ```python
        def main():
            while True:
                zeige_menue()
                wahl = input("Ihre Wahl: ")
        
                if wahl == '1':
                    kunde_hinzufuegen()
                elif wahl == '2':
                    kunden_anzeigen()
                elif wahl == '3':
                    kunde_suchen()
                elif wahl == '4':
                    kunde_aktualisieren()
                elif wahl == '5': # NEU
                    kunde_loeschen()
                elif wahl == '6': # NUMMER GEÄNDERT
                    print("Programm wird beendet. Auf Wiedersehen!")
                    break
                else:
                    print("Ungültige Eingabe. Bitte versuchen Sie es erneut.")
        
        ```
        
    - **Dein `crm.py` sollte jetzt so aussehen (mit deinen Implementierungen):**
        
        ```python
        # Dein Kundenmanagement-System
        
        kunden = {} # Ein Dictionary zum Speichern der Kunden. Schlüssel: Kundenname, Wert: Dictionary mit Details
        
        def kunden_anzeigen():
            if not kunden:
                print("Der Katalog ist leer.")
                return
        
            print("\n--- Deine Kundenliste ---")
            for name, details in kunden.items():
                print(f"Name: {name}")
                print(f"  E-Mail: {details.get('email', 'N/A')}")
                print(f"  Telefon: {details.get('telefon', 'N/A')}")
                print("-------------------------")
        
        def kunde_hinzufuegen():
            print("\n--- Kunden hinzufügen ---")
            name = input("Name des Kunden: ")
            email = input("E-Mail des Kunden: ")
            telefon = input("Telefonnummer des Kunden: ")
        
            if name in kunden:
                print(f"Fehler: Kunde '{name}' existiert bereits im Katalog.")
                return
        
            kunden[name] = {
                "email": email,
                "telefon": telefon
            }
            print(f"Kunde '{name}' wurde hinzugefügt.")
        
        def kunde_suchen():
            print("\n--- Kunden suchen ---")
            suchbegriff = input("Geben Sie einen Suchbegriff (Name oder E-Mail) ein: ").lower()
            gefundene_kunden = {}
        
            for name, details in kunden.items():
                if suchbegriff in name.lower() or suchbegriff in details.get('email', '').lower():
                    gefundene_kunden[name] = details
        
            if not gefundene_kunden:
                print(f"Keine Kunden gefunden, die '{suchbegriff}' im Namen oder in der E-Mail enthalten.")
                return
        
            print(f"\n--- Gefundene Kunden für '{suchbegriff}' ---")
            for name, details in gefundene_kunden.items():
                print(f"Name: {name}")
                print(f"  E-Mail: {details.get('email', 'N/A')}")
                print(f"  Telefon: {details.get('telefon', 'N/A')}")
                print("-------------------------")
        
        def kunde_aktualisieren():
            print("\n--- Kunden aktualisieren ---")
            name_zu_aktualisieren = input("Name des zu aktualisierenden Kunden: ")
        
            if name_zu_aktualisieren not in kunden:
                print(f"Fehler: Kunde '{name_zu_aktualisieren}' nicht im Katalog gefunden.")
                return
        
            print(f"Aktuelle Daten für {name_zu_aktualisieren}:")
            print(f"  E-Mail: {kunden[name_zu_aktualisieren]['email']}")
            print(f"  Telefon: {kunden[name_zu_aktualisieren]['telefon']}")
        
            neue_email = input("Neue E-Mail (leer lassen für keine Änderung): ")
            neue_telefon = input("Neue Telefonnummer (leer lassen für keine Änderung): ")
        
            if neue_email:
                kunden[name_zu_aktualisieren]['email'] = neue_email
            if neue_telefon:
                kunden[name_zu_aktualisieren]['telefon'] = neue_telefon
        
            print(f"Kunde '{name_zu_aktualisieren}' wurde aktualisiert.")
        
        def kunde_loeschen():
            print("\n--- Kunden löschen ---")
            name_zu_loeschen = input("Name des zu löschenden Kunden: ")
            if name_zu_loeschen in kunden:
                del kunden[name_zu_loeschen]
                print(f"Kunde '{name_zu_loeschen}' wurde aus dem Katalog entfernt.")
            else:
                print(f"Fehler: Kunde '{name_zu_loeschen}' nicht im Katalog gefunden.")
        
        def zeige_menue():
            print("\n--- CRM Menü ---")
            print("1. Kunde hinzufügen")
            print("2. Kunden anzeigen")
            print("3. Kunde suchen")
            print("4. Kunde aktualisieren")
            print("5. Kunde löschen")
            print("6. Beenden")
            print("----------------")
        
        def main():
            while True:
                zeige_menue()
                wahl = input("Ihre Wahl: ")
        
                if wahl == '1':
                    kunde_hinzufuegen()
                elif wahl == '2':
                    kunden_anzeigen()
                elif wahl == '3':
                    kunde_suchen()
                elif wahl == '4':
                    kunde_aktualisieren()
                elif wahl == '5':
                    kunde_loeschen()
                elif wahl == '6':
                    print("Programm wird beendet. Auf Wiedersehen!")
                    break
                else:
                    print("Ungültige Eingabe. Bitte versuchen Sie es erneut.")
        
        if __name__ == "__main__":
            main()
        
        ```
        
3. **Testen (im Terminal):**
    - Führe das Skript aus: `python crm.py`
    - Füge einen Kunden hinzu, lösche ihn dann und überprüfe mit "Kunden anzeigen", ob er weg ist.
    - Versuche, einen nicht existierenden Kunden zu löschen, um die Fehlermeldung zu sehen.
4. **Änderungen zum Staging hinzufügen:**
    
    ```bash
    git add crm.py
    
    ```
    
5. **Commit erstellen:**
    
    ```bash
    git commit -m "FEAT: Funktion zum Löschen von Kunden implementiert"
    
    ```
    
6. **Branch pushen:**
    
    ```bash
    git push -u origin feature/kunde-loeschen
    
    ```
    
7. **Merge in `main` (nach Absprache):**
    - `git checkout main`
    - `git pull`
    - `git merge feature/kunde-loeschen`
    - `git push`
    - `git branch -d feature/kunde-loeschen`
    - `git push origin --delete feature/kunde-loeschen`

### TICKET-007: Daten speichern und laden (JSON)

**Beschreibung:**
Implementiere Funktionen, um die Kundendatenbank in einer JSON-Datei zu speichern und beim Start des Programms zu laden.

**Python-Grundlagen (Fokus):**

- Dateihandling (`open()`, `with`)
- JSON-Modul (`json.dump()`, `json.load()`)
- Fehlerbehandlung (`try`/`except` für `FileNotFoundError`, `json.JSONDecodeError`)

**Akzeptanzkriterien:**

- Beim Start des Programms werden vorhandene Kundendaten aus `kunden.json` geladen.
- Wenn `kunden.json` nicht existiert, startet das Programm mit einem leeren Katalog und gibt eine entsprechende Meldung aus.
- Wenn `kunden.json` existiert, aber ungültiges JSON enthält, startet das Programm mit einem leeren Katalog und gibt eine Fehlermeldung aus.
- Beim Beenden des Programms werden alle aktuellen Kundendaten in `kunden.json` gespeichert.
- Die gespeicherten Daten sind korrekt formatiert und lesbar.

**Git-Schritte:**

1. **Branch erstellen:**
    
    ```bash
    git checkout -b feature/speichern-laden
    
    ```
    
2. **Code implementieren (`crm.py`):**
    - Öffne die Datei `crm.py` in VS Code.
    - **Importiere das `json`Modul:** Füge diese Zeile ganz am Anfang der Datei ein:
        
        ```bash
        import json
        
        ```
        
    - **Definiere den Dateinamen als Konstante:** Füge diese Zeile direkt unter der `kunden = {}` Definition ein:
        
        ```python
        DATEINAME = "kunden.json" # Dateiname für die Speicherung des Katalogs
        
        ```
        
    - **Füge die Funktion `katalog_speichern()` hinzu:** Füge diese Funktion **nach** `kunde_loeschen()` ein:
        
        ```python
        def katalog_speichern():
            # TODO: Implementiere das Speichern des 'kunden'-Dictionarys in die Datei 'DATEINAME'.
            # Verwende einen 'try-except'-Block, um IOError abzufangen.
            # Öffne die Datei im Schreibmodus ('w') mit 'encoding='utf-8''.
            # Verwende json.dump(kunden, f, indent=4, ensure_ascii=False) zum Speichern.
            # Gib eine Erfolgs- oder Fehlermeldung aus.
            pass # Platzhalter, entfernen, wenn implementiert
        
        ```
        
    - **Füge die Funktion `katalog_laden()` hinzu:** Füge diese Funktion **nach** `katalog_speichern()` ein:
        
        ```python
        def katalog_laden():
            global kunden # Wichtig, um die globale Variable 'kunden' zu aktualisieren
            # TODO: Implementiere das Laden des 'kunden'-Dictionarys aus der Datei 'DATEINAME'.
            # Verwende einen 'try-except'-Block, um FileNotFoundError, json.JSONDecodeError und allgemeine Exceptions abzufangen.
            # Wenn die Datei nicht gefunden wird oder ungültig ist, initialisiere 'kunden' als leeres Dictionary.
            # Verwende 'with open(DATEINAME, 'r', encoding='utf-8') as f:' zum Öffnen.
            # Verwende 'kunden.update(json.load(f))' zum Laden.
            # Gib entsprechende Erfolgs- oder Fehlermeldungen aus.
            pass # Platzhalter, entfernen, wenn implementiert
        
        ```
        
    - **Aktualisiere die `main()` Funktion:**
        - Rufe `katalog_laden()` ganz am Anfang der `main()` Funktion auf, bevor die `while True`Schleife beginnt.
        - Rufe `katalog_speichern()` auf, bevor das Programm beendet wird (innerhalb des `elif wahl == '6':` Blocks, vor dem `break`).
        
        ```python
        def main():
            # TODO: Rufe hier die Funktion zum Laden des Katalogs auf.
            while True:
                zeige_menue()
                wahl = input("Ihre Wahl: ")
        
                if wahl == '1':
                    kunde_hinzufuegen()
                elif wahl == '2':
                    kunden_anzeigen()
                elif wahl == '3':
                    kunde_suchen()
                elif wahl == '4':
                    kunde_aktualisieren()
                elif wahl == '5':
                    kunde_loeschen()
                elif wahl == '6':
                    # TODO: Rufe hier die Funktion zum Speichern des Katalogs auf.
                    print("Programm wird beendet. Auf Wiedersehen!")
                    break
                else:
                    print("Ungültige Eingabe. Bitte versuchen Sie es erneut.")
        
        ```
        
    - **Dein `crm.py` sollte jetzt so aussehen (mit deinen Implementierungen):**
        
        ```python
        import json # NEU
        
        # Dein Kundenmanagement-System
        
        kunden = {} # Ein Dictionary zum Speichern der Kunden. Schlüssel: Kundenname, Wert: Dictionary mit Details
        DATEINAME = "kunden.json" # NEU: Dateiname für die Speicherung des Katalogs
        
        def kunden_anzeigen():
            if not kunden:
                print("Der Katalog ist leer.")
                return
        
            print("\n--- Deine Kundenliste ---")
            for name, details in kunden.items():
                print(f"Name: {name}")
                print(f"  E-Mail: {details.get('email', 'N/A')}")
                print(f"  Telefon: {details.get('telefon', 'N/A')}")
                print("-------------------------")
        
        def kunde_hinzufuegen():
            print("\n--- Kunden hinzufügen ---")
            name = input("Name des Kunden: ")
            email = input("E-Mail des Kunden: ")
            telefon = input("Telefonnummer des Kunden: ")
        
            if name in kunden:
                print(f"Fehler: Kunde '{name}' existiert bereits im Katalog.")
                return
        
            kunden[name] = {
                "email": email,
                "telefon": telefon
            }
            print(f"Kunde '{name}' wurde hinzugefügt.")
        
        def kunde_suchen():
            print("\n--- Kunden suchen ---")
            suchbegriff = input("Geben Sie einen Suchbegriff (Name oder E-Mail) ein: ").lower()
            gefundene_kunden = {}
        
            for name, details in kunden.items():
                if suchbegriff in name.lower() or suchbegriff in details.get('email', '').lower():
                    gefundene_kunden[name] = details
        
            if not gefundene_kunden:
                print(f"Keine Kunden gefunden, die '{suchbegriff}' im Namen oder in der E-Mail enthalten.")
                return
        
            print(f"\n--- Gefundene Kunden für '{suchbegriff}' ---")
            for name, details in gefundene_kunden.items():
                print(f"Name: {name}")
                print(f"  E-Mail: {details.get('email', 'N/A')}")
                print(f"  Telefon: {details.get('telefon', 'N/A')}")
                print("-------------------------")
        
        def kunde_aktualisieren():
            print("\n--- Kunden aktualisieren ---")
            name_zu_aktualisieren = input("Name des zu aktualisierenden Kunden: ")
        
            if name_zu_aktualisieren not in kunden:
                print(f"Fehler: Kunde '{name_zu_aktualisieren}' nicht im Katalog gefunden.")
                return
        
            print(f"Aktuelle Daten für {name_zu_aktualisieren}:")
            print(f"  E-Mail: {kunden[name_zu_aktualisieren]['email']}")
            print(f"  Telefon: {kunden[name_zu_aktualisieren]['telefon']}")
        
            neue_email = input("Neue E-Mail (leer lassen für keine Änderung): ")
            neue_telefon = input("Neue Telefonnummer (leer lassen für keine Änderung): ")
        
            if neue_email:
                kunden[name_zu_aktualisieren]['email'] = neue_email
            if neue_telefon:
                kunden[name_zu_aktualisieren]['telefon'] = neue_telefon
        
            print(f"Kunde '{name_zu_aktualisieren}' wurde aktualisiert.")
        
        def kunde_loeschen():
            print("\n--- Kunden löschen ---")
            name_zu_loeschen = input("Name des zu löschenden Kunden: ")
            if name_zu_loeschen in kunden:
                del kunden[name_zu_loeschen]
                print(f"Kunde '{name_zu_loeschen}' wurde aus dem Katalog entfernt.")
            else:
                print(f"Fehler: Kunde '{name_zu_loeschen}' nicht im Katalog gefunden.")
        
        def katalog_speichern():
            try:
                with open(DATEINAME, 'w', encoding='utf-8') as f:
                    json.dump(kunden, f, indent=4, ensure_ascii=False)
                print(f"Katalog erfolgreich in '{DATEINAME}' gespeichert.")
            except IOError as e:
                print(f"Fehler beim Speichern des Katalogs: {e}")
        
        def katalog_laden():
            global kunden
            try:
                with open(DATEINAME, 'r', encoding='utf-8') as f:
                    kunden.update(json.load(f))
                print(f"Katalog erfolgreich aus '{DATEINAME}' geladen.")
            except FileNotFoundError:
                print("Keine vorhandene Katalogdatei gefunden. Starte mit leerem Katalog.")
                kunden.clear()
            except json.JSONDecodeError as e:
                print(f"Fehler beim Laden des Katalogs (ungültiges JSON): {e}. Starte mit leerem Katalog.")
                kunden.clear()
            except Exception as e:
                print(f"Ein unerwarteter Fehler beim Laden ist aufgetreten: {e}. Starte mit leerem Katalog.")
                kunden.clear()
        
        def zeige_menue():
            print("\n--- CRM Menü ---")
            print("1. Kunde hinzufügen")
            print("2. Kunden anzeigen")
            print("3. Kunde suchen")
            print("4. Kunde aktualisieren")
            print("5. Kunde löschen")
            print("6. Beenden")
            print("----------------")
        
        def main():
            katalog_laden()
            while True:
                zeige_menue()
                wahl = input("Ihre Wahl: ")
        
                if wahl == '1':
                    kunde_hinzufuegen()
                elif wahl == '2':
                    kunden_anzeigen()
                elif wahl == '3':
                    kunde_suchen()
                elif wahl == '4':
                    kunde_aktualisieren()
                elif wahl == '5':
                    kunde_loeschen()
                elif wahl == '6':
                    katalog_speichern()
                    print("Programm wird beendet. Auf Wiedersehen!")
                    break
                else:
                    print("Ungültige Eingabe. Bitte versuchen Sie es erneut.")
        
        if __name__ == "__main__":
            main()
        
        ```
        
3. **Testen (im Terminal):**
    - Führe das Skript aus. Füge einige Kunden hinzu. Beende das Programm (Option 6).
    - Starte das Programm erneut. Sind die Kunden noch da? (Sie sollten aus `kunden.json` geladen werden).
    - Öffne die Datei `kunden.json` in VS Code, um den gespeicherten JSON-Inhalt zu sehen.
    - Lösche die `kunden.json`Datei manuell im Explorer und starte das Programm. Es sollte mit einem leeren Katalog starten und die Meldung "Keine vorhandene Katalogdatei gefunden." anzeigen.
4. **Änderungen zum Staging hinzufügen:**
    
    ```bash
    git add crm.py
    git add kunden.json # Füge auch die neue JSON-Datei hinzu, wenn sie erstellt wurde
    
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

### TICKET-008: Eingabevalidierung

**Beschreibung:**
Verbessere die Robustheit deines Programms, indem du Benutzereingaben validierst (z.B. E-Mail-Format, Telefonnummer nur Ziffern) und geeignete Fehlermeldungen ausgibst.

**Python-Grundlagen (Fokus):**

- Reguläre Ausdrücke (`re` Modul) für E-Mail-Validierung (optional, kann auch einfacher gelöst werden)
- String-Methoden (`.isdigit()`) für Telefonnummer
- `try`/`except` Blöcke
- Schleifen für wiederholte Eingabe bei Fehlern

**Akzeptanzkriterien:**

- Beim Hinzufügen oder Aktualisieren eines Kunden:
    - E-Mail-Adressen müssen ein gültiges Format haben (z.B. `name@domain.com`).
    - Telefonnummern dürfen nur Ziffern enthalten (optional: und ein `+` am Anfang).
- Ungültige Eingaben führen zu einer Fehlermeldung und der Benutzer wird zur erneuten Eingabe aufgefordert, bis die Eingabe gültig ist.

**Git-Schritte:**

1. **Branch erstellen:**
    
    ```bash
    git checkout -b chore/eingabe-validierung
    
    ```
    
2. **Code implementieren (`crm.py`):**
    - Öffne die Datei `crm.py` in VS Code.
    - **Importiere das `re`Modul (für E-Mail-Validierung):** Füge diese Zeile ganz am Anfang der Datei, unter `import json`, ein:
        
        ```python
        import re # NEU: Für E-Mail-Validierung
        
        ```
        
    - **Passe `kunde_hinzufuegen()` an:** Füge `while True`Schleifen mit Validierungslogik für E-Mail und Telefonnummer hinzu.
        
        ```python
        def kunde_hinzufuegen():
            print("\n--- Kunden hinzufügen ---")
            name = input("Name des Kunden: ")
        
            # TODO: Implementiere eine Schleife für die E-Mail-Eingabe.
            # Frage nach der E-Mail.
            # Verwende 're.match(r"[^@]+@[^@]+\.[^@]+", email)' zur Validierung des Formats.
            # Wenn ungültig, gib eine Fehlermeldung aus und frage erneut.
            # Beispiel: while True: email = input(...); if re.match(...): break; else: print(...)
            email = "" # Platzhalter, ersetzen
        
            # TODO: Implementiere eine Schleife für die Telefonnummer-Eingabe.
            # Frage nach der Telefonnummer.
            # Verwende 'telefon.replace('+', '').isdigit()' zur Überprüfung, ob es nur Ziffern sind (und optional '+').
            # Wenn ungültig, gib eine Fehlermeldung aus und frage erneut.
            telefon = "" # Platzhalter, ersetzen
        
            if name in kunden:
                print(f"Fehler: Kunde '{name}' existiert bereits im Katalog.")
                return
        
            kunden[name] = {
                "email": email,
                "telefon": telefon
            }
            print(f"Kunde '{name}' wurde hinzugefügt.")
        
        ```
        
    - **Passe `kunde_aktualisieren()` an:** Füge ähnliche Validierungslogik für die neue E-Mail und Telefonnummer hinzu, aber nur, wenn der Benutzer eine Eingabe macht (nicht leer lässt).
        
        ```bash
        def kunde_aktualisieren():
            print("\n--- Kunden aktualisieren ---")
            name_zu_aktualisieren = input("Name des zu aktualisierenden Kunden: ")
        
            if name_zu_aktualisieren not in kunden:
                print(f"Fehler: Kunde '{name_zu_aktualisieren}' nicht im Katalog gefunden.")
                return
        
            print(f"Aktuelle Daten für {name_zu_aktualisieren}:")
            print(f"  E-Mail: {kunden[name_zu_aktualisieren]['email']}")
            print(f"  Telefon: {kunden[name_zu_aktualisieren]['telefon']}")
        
            neue_email = input("Neue E-Mail (leer lassen für keine Änderung): ")
            # TODO: Wenn 'neue_email' nicht leer ist, validiere sie.
            # Wenn ungültig, frage erneut, bis gültig oder leer gelassen.
            # Aktualisiere dann 'kunden[name_zu_aktualisieren]['email']'.
        
            neue_telefon = input("Neue Telefonnummer (leer lassen für keine Änderung): ")
            # TODO: Wenn 'neue_telefon' nicht leer ist, validiere sie.
            # Wenn ungültig, frage erneut, bis gültig oder leer gelassen.
            # Aktualisiere dann 'kunden[name_zu_aktualisieren]['telefon']'.
        
            print(f"Kunde '{name_zu_aktualisieren}' wurde aktualisiert.")
        
        ```
        
    - **Dein `crm.py` sollte jetzt so aussehen (mit deinen Implementierungen):**
        
        ```bash
        import json
        import re # NEU: Für E-Mail-Validierung
        
        # Dein Kundenmanagement-System
        
        kunden = {} # Ein Dictionary zum Speichern der Kunden. Schlüssel: Kundenname, Wert: Dictionary mit Details
        DATEINAME = "kunden.json" # Dateiname für die Speicherung des Katalogs
        
        def kunden_anzeigen():
            if not kunden:
                print("Der Katalog ist leer.")
                return
        
            print("\n--- Deine Kundenliste ---")
            for name, details in kunden.items():
                print(f"Name: {name}")
                print(f"  E-Mail: {details.get('email', 'N/A')}")
                print(f"  Telefon: {details.get('telefon', 'N/A')}")
                print("-------------------------")
        
        def kunde_hinzufuegen():
            print("\n--- Kunden hinzufügen ---")
            name = input("Name des Kunden: ")
        
            # Validierung für E-Mail
            while True:
                email = input("E-Mail des Kunden: ")
                if re.match(r"[^@]+@[^@]+\.[^@]+", email):
                    break
                else:
                    print("Ungültiges E-Mail-Format. Bitte versuchen Sie es erneut.")
        
            # Validierung für Telefonnummer
            while True:
                telefon = input("Telefonnummer des Kunden: ")
                if telefon.replace('+', '').isdigit() and (telefon.startswith('+') or not telefon.startswith('+')):
                    break
                else:
                    print("Ungültige Telefonnummer. Bitte geben Sie nur Ziffern ein (optional mit + am Anfang).")
        
            if name in kunden:
                print(f"Fehler: Kunde '{name}' existiert bereits im Katalog.")
                return
        
            kunden[name] = {
                "email": email,
                "telefon": telefon
            }
            print(f"Kunde '{name}' wurde hinzugefügt.")
        
        def kunde_suchen():
            print("\n--- Kunden suchen ---")
            suchbegriff = input("Geben Sie einen Suchbegriff (Name oder E-Mail) ein: ").lower()
            gefundene_kunden = {}
        
            for name, details in kunden.items():
                if suchbegriff in name.lower() or suchbegriff in details.get('email', '').lower():
                    gefundene_kunden[name] = details
        
            if not gefundene_kunden:
                print(f"Keine Kunden gefunden, die '{suchbegriff}' im Namen oder in der E-Mail enthalten.")
                return
        
            print(f"\n--- Gefundene Kunden für '{suchbegriff}' ---")
            for name, details in kunden.items():
                print(f"Name: {name}")
                print(f"  E-Mail: {details.get('email', 'N/A')}")
                print(f"  Telefon: {details.get('telefon', 'N/A')}")
                print("-------------------------")
        
        def kunde_aktualisieren():
            print("\n--- Kunden aktualisieren ---")
            name_zu_aktualisieren = input("Name des zu aktualisierenden Kunden: ")
        
            if name_zu_aktualisieren not in kunden:
                print(f"Fehler: Kunde '{name_zu_aktualisieren}' nicht im Katalog gefunden.")
                return
        
            print(f"Aktuelle Daten für {name_zu_aktualisieren}:")
            print(f"  E-Mail: {kunden[name_zu_aktualisieren]['email']}")
            print(f"  Telefon: {kunden[name_zu_aktualisieren]['telefon']}")
        
            neue_email = input("Neue E-Mail (leer lassen für keine Änderung): ")
            if neue_email:
                while not re.match(r"[^@]+@[^@]+\.[^@]+", neue_email):
                    print("Ungültiges E-Mail-Format. Bitte versuchen Sie es erneut.")
                    neue_email = input("Neue E-Mail (leer lassen für keine Änderung): ")
                kunden[name_zu_aktualisieren]['email'] = neue_email
        
            neue_telefon = input("Neue Telefonnummer (leer lassen für keine Änderung): ")
            if neue_telefon:
                while not (neue_telefon.replace('+', '').isdigit() and (neue_telefon.startswith('+') or not neue_telefon.startswith('+'))):
                    print("Ungültige Telefonnummer. Bitte geben Sie nur Ziffern ein (optional mit + am Anfang).")
                    neue_telefon = input("Neue Telefonnummer (leer lassen für keine Änderung): ")
                kunden[name_zu_aktualisieren]['telefon'] = neue_telefon
        
            print(f"Kunde '{name_zu_aktualisieren}' wurde aktualisiert.")
        
        def kunde_loeschen():
            print("\n--- Kunden löschen ---")
            name_zu_loeschen = input("Name des zu löschenden Kunden: ")
            if name_zu_loeschen in kunden:
                del kunden[name_zu_loeschen]
                print(f"Kunde '{name_zu_loeschen}' wurde aus dem Katalog entfernt.")
            else:
                print(f"Fehler: Kunde '{name_zu_loeschen}' nicht im Katalog gefunden.")
        
        def katalog_speichern():
            try:
                with open(DATEINAME, 'w', encoding='utf-8') as f:
                    json.dump(kunden, f, indent=4, ensure_ascii=False)
                print(f"Katalog erfolgreich in '{DATEINAME}' gespeichert.")
            except IOError as e:
                print(f"Fehler beim Speichern des Katalogs: {e}")
        
        def katalog_laden():
            global kunden
            try:
                with open(DATEINAME, 'r', encoding='utf-8') as f:
                    kunden.update(json.load(f))
                print(f"Katalog erfolgreich aus '{DATEINAME}' geladen.")
            except FileNotFoundError:
                print("Keine vorhandene Katalogdatei gefunden. Starte mit leerem Katalog.")
                kunden.clear()
            except json.JSONDecodeError as e:
                print(f"Fehler beim Laden des Katalogs (ungültiges JSON): {e}. Starte mit leerem Katalog.")
                kunden.clear()
            except Exception as e:
                print(f"Ein unerwarteter Fehler beim Laden ist aufgetreten: {e}. Starte mit leerem Katalog.")
                kunden.clear()
        
        def zeige_menue():
            print("\n--- CRM Menü ---")
            print("1. Kunde hinzufügen")
            print("2. Kunden anzeigen")
            print("3. Kunde suchen")
            print("4. Kunde aktualisieren")
            print("5. Kunde löschen")
            print("6. Beenden")
            print("----------------")
        
        def main():
            katalog_laden()
            while True:
                zeige_menue()
                wahl = input("Ihre Wahl: ")
        
                if wahl == '1':
                    kunde_hinzufuegen()
                elif wahl == '2':
                    kunden_anzeigen()
                elif wahl == '3':
                    kunde_suchen()
                elif wahl == '4':
                    kunde_aktualisieren()
                elif wahl == '5':
                    kunde_loeschen()
                elif wahl == '6':
                    katalog_speichern()
                    print("Programm wird beendet. Auf Wiedersehen!")
                    break
                else:
                    print("Ungültige Eingabe. Bitte versuchen Sie es erneut.")
        
        if __name__ == "__main__":
            main()
        
        ```
        
3. **Testen (im Terminal):**
    - Führe das Skript aus: `python crm.py`
    - Versuche, einen Kunden hinzuzufügen. Gib ungültige E-Mail-Formate (z.B. "test", "test@") und Telefonnummern (z.B. "abc", "123a") ein. Beobachte die Fehlermeldungen und die Aufforderung zur erneuten Eingabe.
    - Teste auch die Aktualisierungsfunktion mit ungültigen Eingaben.
4. **Änderungen zum Staging hinzufügen:**
    
    ```bash
    git add crm.py
    
    ```
    
5. **Commit erstellen:**
    
    ```bash
    git commit -m "CHORE: Eingabevalidierung für E-Mail und Telefonnummer implementiert"
    
    ```
    
6. **Branch pushen:**
    
    ```bash
    git push -u origin chore/eingabe-validierung
    
    ```
    
7. **Merge in `main` (nach Absprache):**
    - `git checkout main`
    - `git pull`
    - `git merge chore/eingabe-validierung`
    - `git push`
    - `git branch -d chore/eingabe-validierung`
    - `git push origin --delete chore/eingabe-validierung`

### TICKET-009: Code-Dokumentation (Docstrings & Kommentare)

**Beschreibung:**
Füge Docstrings zu allen Funktionen und Modulen hinzu, die deren Zweck, Parameter und Rückgabewerte beschreiben. Ergänze außerdem sinnvolle Inline-Kommentare, um komplexe Logik zu erklären und die Lesbarkeit des Codes zu verbessern.

**Python-Grundlagen (Fokus):**

- Docstrings (PEP 257)
- Inline-Kommentare
- Code-Lesbarkeit und Best Practices

**Akzeptanzkriterien:**

- Das Modul hat einen Docstring, der seinen Zweck beschreibt.
- Jede Funktion hat einen Docstring, der ihren Zweck, ihre Parameter (falls vorhanden) und ihren Rückgabewert (falls vorhanden) erklärt.
- Komplexe oder nicht sofort ersichtliche Code-Blöcke sind mit Inline-Kommentaren versehen.
- Der Code ist gut lesbar und die Kommentare sind prägnant und hilfreich.

**Git-Schritte:**

1. **Branch erstellen:**
    
    ```bash
    git checkout -b chore/code-dokumentation
    
    ```
    
2. **Code implementieren (`crm.py`):**
    - Öffne die Datei `crm.py` in VS Code.
    - **Modul-Docstring:** Füge am Anfang der Datei `crm.py` (direkt unter den `import`Anweisungen) einen Docstring hinzu, der den allgemeinen Zweck des Skripts beschreibt.
        
        ```python
        """
        # TODO: Füge hier einen Modul-Docstring hinzu, der den Zweck des crm.py-Skripts beschreibt.
        # Beispiel:
        # Ein einfaches Python-Programm zur Verwaltung eines Kundenmanagement-Systems (CRM).
        # Es ermöglicht das Hinzufügen, Anzeigen, Suchen, Aktualisieren und Löschen von Kunden
        # sowie das Speichern und Laden der Kundendaten in/aus einer JSON-Datei.
        """
        
        ```
        
    - **Funktions-Docstrings:** Füge für jede Funktion (`kunden_anzeigen`, `kunde_hinzufuegen`, `kunde_suchen`, `kunde_aktualisieren`, `kunde_loeschen`, `katalog_speichern`, `katalog_laden`, `zeige_menue`, `main`) einen Docstring hinzu. Platziere den Docstring direkt unter der `def`Zeile der Funktion.
        - **Beispiel für `kunden_anzeigen()`:**
            
            ```python
            def kunden_anzeigen():
                """
                # TODO: Füge hier einen Docstring für diese Funktion hinzu.
                # Beschreibe, was die Funktion tut (z.B. "Zeigt alle Kunden im aktuellen CRM-Katalog an.").
                # Erwähne, wenn sie eine Meldung ausgibt (z.B. "Gibt eine Meldung aus, wenn der Katalog leer ist.").
                """
                # ... (restlicher Code der Funktion) ...
            
            ```
            
        - **Gehe jede Funktion durch und füge einen passenden Docstring hinzu.**
    - **Inline-Kommentare:** Füge kurze, erklärende Kommentare an komplexen oder nicht sofort ersichtlichen Code-Stellen hinzu.
        - **Beispiel in `kunde_hinzufuegen()`:**
            
            ```python
            # Validierung für E-Mail: Schleife, bis ein gültiges Format eingegeben wird
            while True:
                email = input("E-Mail des Kunden: ")
                if re.match(r"[^@]+@[^@]+\.[^@]+", email): # Prüft auf @ und .
                    break
                else:
                    print("Ungültiges E-Mail-Format. Bitte versuchen Sie es erneut.")
            
            ```
            
        - **Gehe den gesamten Code durch und füge Kommentare hinzu, wo du denkst, dass sie die Lesbarkeit oder das Verständnis verbessern.**
    - **Dein `crm.py` sollte jetzt so aussehen (mit deinen Implementierungen):**
        
        ```python
        import json
        import re
        
        """
        Ein einfaches Python-Programm zur Verwaltung eines Kundenmanagement-Systems (CRM).
        Es ermöglicht das Hinzufügen, Anzeigen, Suchen, Aktualisieren und Löschen von Kunden
        sowie das Speichern und Laden der Kundendaten in/aus einer JSON-Datei.
        """
        
        # Globale Variable zum Speichern der Kundendaten
        # Schlüssel: Kundenname (String), Wert: Dictionary mit Kundendetails
        kunden = {}
        DATEINAME = "kunden.json" # Dateiname für die Speicherung des Katalogs
        
        def kunden_anzeigen():
            """
            Zeigt alle Kunden im aktuellen CRM-Katalog an.
            Gibt eine Meldung aus, wenn der Katalog leer ist.
            """
            if not kunden:
                print("Der Katalog ist leer.")
                return
        
            print("\n--- Deine Kundenliste ---")
            # Iteriere durch das Kunden-Dictionary und zeige Details an
            for name, details in kunden.items():
                print(f"Name: {name}")
                # Verwende .get() mit Standardwert 'N/A', falls ein Detail fehlt
                print(f"  E-Mail: {details.get('email', 'N/A')}")
                print(f"  Telefon: {details.get('telefon', 'N/A')}")
                print("-------------------------")
        
        def kunde_hinzufuegen():
            """
            Fügt einen neuen Kunden zum CRM-Katalog hinzu.
            Fragt den Benutzer nach Name, E-Mail und Telefonnummer.
            Validiert die Eingaben für E-Mail und Telefonnummer.
            Verhindert das Hinzufügen von Kunden mit bereits existierendem Namen.
            """
            print("\n--- Kunden hinzufügen ---")
            name = input("Name des Kunden: ")
        
            # Validierung für E-Mail: Schleife, bis ein gültiges Format eingegeben wird
            while True:
                email = input("E-Mail des Kunden: ")
                if re.match(r"[^@]+@[^@]+\.[^@]+", email): # Einfache E-Mail-Validierung
                    break
                else:
                    print("Ungültiges E-Mail-Format. Bitte versuchen Sie es erneut.")
        
            # Validierung für Telefonnummer: Schleife, bis nur Ziffern (optional mit +) eingegeben werden
            while True:
                telefon = input("Telefonnummer des Kunden: ")
                # Prüft, ob die Telefonnummer nur Ziffern enthält (optional: + am Anfang erlauben)
                if telefon.replace('+', '').isdigit() and (telefon.startswith('+') or not telefon.startswith('+')):
                    break
                else:
                    print("Ungültige Telefonnummer. Bitte geben Sie nur Ziffern ein (optional mit + am Anfang).")
        
            # Überprüfe, ob der Name bereits existiert, um Duplikate zu vermeiden
            if name in kunden:
                print(f"Fehler: Kunde '{name}' existiert bereits im Katalog.")
                return
        
            # Speichere die Kundendetails als verschachteltes Dictionary
            kunden[name] = {
                "email": email,
                "telefon": telefon
            }
            print(f"Kunde '{name}' wurde hinzugefügt.")
        
        def kunde_suchen():
            """
            Sucht Kunden im Katalog basierend auf einem Teil des Namens oder der E-Mail-Adresse.
            Zeigt alle passenden Kunden mit ihren Details an.
            """
            print("\n--- Kunden suchen ---")
            # Suchbegriff in Kleinbuchstaben umwandeln für case-insensitive Suche
            suchbegriff = input("Geben Sie einen Suchbegriff (Name oder E-Mail) ein: ").lower()
            gefundene_kunden = {}
        
            # Iteriere durch alle Kunden im Katalog
            for name, details in kunden.items():
                # Überprüfe, ob der Suchbegriff im Namen oder in der E-Mail enthalten ist
                if suchbegriff in name.lower() or suchbegriff in details.get('email', '').lower():
                    gefundene_kunden[name] = details
        
            # Wenn keine Kunden gefunden wurden
            if not gefundene_kunden:
                print(f"Keine Kunden gefunden, die '{suchbegriff}' im Namen oder in der E-Mail enthalten.")
                return
        
            print(f"\n--- Gefundene Kunden für '{suchbegriff}' ---")
            # Zeige die Details der gefundenen Kunden an
            for name, details in gefundene_kunden.items():
                print(f"Name: {name}")
                print(f"  E-Mail: {details.get('email', 'N/A')}")
                print(f"  Telefon: {details.get('telefon', 'N/A')}")
                print("-------------------------")
        
        def kunde_aktualisieren():
            """
            Aktualisiert die E-Mail-Adresse und/oder Telefonnummer eines bestehenden Kunden.
            Fragt den Benutzer nach dem Kundennamen und dann nach den neuen Daten.
            Leere Eingaben für E-Mail/Telefon lassen die bestehenden Werte unverändert.
            """
            print("\n--- Kunden aktualisieren ---")
            name_zu_aktualisieren = input("Name des zu aktualisierenden Kunden: ")
        
            if name_zu_aktualisieren not in kunden:
                print(f"Fehler: Kunde '{name_zu_aktualisieren}' nicht im Katalog gefunden.")
                return
        
            print(f"Aktuelle Daten für {name_zu_aktualisieren}:")
            print(f"  E-Mail: {kunden[name_zu_aktualisieren]['email']}")
            print(f"  Telefon: {kunden[name_zu_aktualisieren]['telefon']}")
        
            neue_email = input("Neue E-Mail (leer lassen für keine Änderung): ")
            if neue_email: # Nur validieren und aktualisieren, wenn eine Eingabe gemacht wurde
                while not re.match(r"[^@]+@[^@]+\.[^@]+", neue_email):
                    print("Ungültiges E-Mail-Format. Bitte versuchen Sie es erneut.")
                    neue_email = input("Neue E-Mail (leer lassen für keine Änderung): ")
                kunden[name_zu_aktualisieren]['email'] = neue_email
        
            neue_telefon = input("Neue Telefonnummer (leer lassen für keine Änderung): ")
            if neue_telefon: # Nur validieren und aktualisieren, wenn eine Eingabe gemacht wurde
                while not (neue_telefon.replace('+', '').isdigit() and (neue_telefon.startswith('+') or not neue_telefon.startswith('+'))):
                    print("Ungültige Telefonnummer. Bitte geben Sie nur Ziffern ein (optional mit + am Anfang).")
                    neue_telefon = input("Neue Telefonnummer (leer lassen für keine Änderung): ")
                kunden[name_zu_aktualisieren]['telefon'] = neue_telefon
        
            print(f"Kunde '{name_zu_aktualisieren}' wurde aktualisiert.")
        
        def kunde_loeschen():
            """
            Löscht einen Kunden aus dem Katalog anhand seines Namens.
            Gibt eine Fehlermeldung aus, wenn der Kunde nicht gefunden wird.
            """
            print("\n--- Kunden löschen ---")
            titel_zu_loeschen = input("Name des zu löschenden Kunden: ")
            if titel_zu_loeschen in kunden:
                del kunden[titel_zu_loeschen]
                print(f"Kunde '{titel_zu_loeschen}' wurde aus dem Katalog entfernt.")
            else:
                print(f"Fehler: Kunde '{titel_zu_loeschen}' nicht im Katalog gefunden.")
        
        def katalog_speichern():
            """
            Speichert den aktuellen Kundenkatalog in einer JSON-Datei.
            Der Dateiname wird durch die globale Variable DATEINAME definiert.
            Behandelt IOError bei Problemen mit der Dateispeicherung.
            """
            try:
                with open(DATEINAME, 'w', encoding='utf-8') as f:
                    json.dump(kunden, f, indent=4, ensure_ascii=False)
                print(f"Katalog erfolgreich in '{DATEINAME}' gespeichert.")
            except IOError as e:
                print(f"Fehler beim Speichern des Katalogs: {e}")
        
        def katalog_laden():
            """
            Lädt den Kundenkatalog aus einer JSON-Datei.
            Der Dateiname wird durch die globale Variable DATEINAME definiert.
            Initialisiert den Katalog neu, wenn die Datei nicht gefunden wird
            oder ungültiges JSON enthält.
            """
            global kunden
            try:
                with open(DATEINAME, 'r', encoding='utf-8') as f:
                    kunden.update(json.load(f))
                print(f"Katalog erfolgreich aus '{DATEINAME}' geladen.")
            except FileNotFoundError:
                print("Keine vorhandene Katalogdatei gefunden. Starte mit leerem Katalog.")
                kunden.clear()
            except json.JSONDecodeError as e:
                print(f"Fehler beim Laden des Katalogs (ungültiges JSON): {e}. Starte mit leerem Katalog.")
                kunden.clear()
            except Exception as e:
                print(f"Ein unerwarteter Fehler beim Laden ist aufgetreten: {e}. Starte mit leerem Katalog.")
                kunden.clear()
        
        def zeige_menue():
            """
            Zeigt das Hauptmenü des CRM-Systems an.
            """
            print("\n--- CRM Menü ---")
            print("1. Kunde hinzufügen")
            print("2. Kunden anzeigen")
            print("3. Kunde suchen")
            print("4. Kunde aktualisieren")
            print("5. Kunde löschen")
            print("6. Beenden")
            print("----------------")
        
        def main():
            """
            Die Hauptfunktion des Programms.
            Lädt den Katalog beim Start, zeigt das Menü an und verarbeitet Benutzereingaben.
            Speichert den Katalog beim Beenden.
            """
            katalog_laden()
            while True:
                zeige_menue()
                wahl = input("Ihre Wahl: ")
        
                if wahl == '1':
                    kunde_hinzufuegen()
                elif wahl == '2':
                    kunden_anzeigen()
                elif wahl == '3':
                    kunde_suchen()
                elif wahl == '4':
                    kunde_aktualisieren()
                elif wahl == '5':
                    kunde_loeschen()
                elif wahl == '6':
                    katalog_speichern()
                    print("Programm wird beendet. Auf Wiedersehen!")
                    break
                else:
                    print("Ungültige Eingabe. Bitte versuchen Sie es erneut.")
        
        if __name__ == "__main__":
            main()
        
        ```
        
3. **Testen (im Terminal):**
    - Führe das Skript aus: `python crm.py`
    - Überprüfe, ob das Programm weiterhin korrekt funktioniert.
    - Die Hauptaufgabe des Tests ist hier die Überprüfung der **Lesbarkeit** des Codes. Lies den Code durch und versuche, die Logik nur anhand der Kommentare und Docstrings zu verstehen.
4. **Änderungen zum Staging hinzufügen:**
    
    ```bash
    git add crm.py
    
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

Nachdem du alle Tickets bearbeitet hast, solltest du ein funktionsfähiges Kundenmanagement-System haben.

- **Überprüfe deinen Git-Verlauf:** `git log --oneline --graph --all`
    - Siehst du, wie die Branches erstellt, bearbeitet und dann wieder in `main` gemergt wurden?
    - Sind deine Commit-Nachrichten aussagekräftig?
- **Reflektiere:**
    - Was war die größte Herausforderung bei Git?
    - Wie hat dir die Arbeit mit Branches geholfen, den Überblick zu behalten?
    - Welche Vorteile siehst du jetzt in der Versionskontrolle?

Viel Erfolg und Spaß beim Programmieren und Versionieren!