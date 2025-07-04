# Git & Python Lernprojekt: Dein Kundenmanagement-System (CRM) - Nur Anweisungen

Willkommen zu deinem nächsten kombinierten Lernprojekt! In diesem Szenario wirst du ein einfaches Kundenmanagement-System (CRM) in Python programmieren und dabei Git und GitHub nutzen, um deine Arbeit zu versionieren und jeden Entwicklungsschritt sauber zu dokumentieren.

Das Projekt ist in einzelne "Tickets" unterteilt. Jedes Ticket repräsentiert eine Aufgabe, die du implementieren und dann mit Git in einem eigenen Branch verwalten wirst. So lernst du, wie man inkrementell arbeitet und sinnvolle Commits erstellt.

## Projektübersicht: Das Kundenmanagement-System

Du wirst ein Python-Programm erstellen, das dir erlaubt, Kunden zu deiner Datenbank hinzuzufügen, sie anzuzeigen, zu suchen, zu aktualisieren und zu löschen. Die Kundendaten werden lokal gespeichert und geladen.

## Vorbereitung: Projekt initialisieren (Einmalig)

Bevor du mit den Tickets beginnst, musst du dein Projekt initialisieren und auf GitHub vorbereiten.

1. **Öffne VS Code.**
2. **Öffne das Terminal:** `Terminal > New Terminal`.
3. **Navigiere zum gewünschten Speicherort:**
    
    ```
    cd ~ # Oder ein anderer Projektordner
    
    ```
    
4. **Erstelle einen neuen Projektordner:**
    
    ```
    mkdir CRMProjekt
    cd CRMProjekt
    
    ```
    
5. **Initialisiere ein Git-Repository:**
    
    ```
    git init
    
    ```
    
6. **Erstelle die Hauptdatei für dein Programm:**
    - Klicke im VS Code Explorer auf "New File" und nenne die Datei `crm.py`.
    - Füge einen Kommentar hinzu: `# Dein Kundenmanagement-System`
    - Speichere die Datei.
7. **Füge die Datei zum Staging hinzu und mache den ersten Commit:**
    
    ```
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
        
        ```
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
    
    ```
    git checkout -b feature/kunden-liste
    
    ```
    
2. **Code implementieren (`crm.py`):**
    - Öffne die Datei `crm.py` in VS Code.
    - **Füge die globale Variable `kunden` hinzu:** Direkt unter dem Kommentar `# Dein Kundenmanagement-System` definiere ein leeres Dictionary namens `kunden`. Dieses Dictionary wird als Hauptspeicher für all deine Kundendaten dienen.
    - **Definiere die Funktion `kunden_anzeigen()`:** Füge eine neue Funktion namens `kunden_anzeigen()` hinzu.
        - Innerhalb dieser Funktion:
            - Überprüfe, ob das `kunden`Dictionary leer ist.
            - Wenn es leer ist, gib die Nachricht "Der Katalog ist leer." aus und beende die Funktion mit `return`.
            - Gib eine Überschrift wie "--- Deine Kundenliste ---" aus.
            - Iteriere über alle Kunden im `kunden`Dictionary. Nutze dafür die `.items()`Methode, um sowohl den Kundennamen (als Schlüssel) als auch die Kundendetails (als Wert, ein weiteres Dictionary) zu erhalten.
            - Für jeden Kunden gib den Namen, die E-Mail und die Telefonnummer aus. Verwende die `.get()`Methode für E-Mail und Telefonnummer mit einem Standardwert von `'N/A'`, falls diese Details noch nicht vorhanden sind.
            - Füge eine Trennlinie nach jedem Kunden hinzu.
    - **Optionaler Testaufruf:** Füge am Ende der Datei einen vorübergehenden Aufruf von `kunden_anzeigen()` hinzu, um deine Implementierung zu testen. Vergiss nicht, diesen Aufruf vor dem Commit wieder zu entfernen oder auszukommentieren.
3. **Testen (im Terminal):**
    - Führe das Skript aus: `python crm.py`
    - Erwarte die Ausgabe "Der Katalog ist leer.".
4. **Änderungen zum Staging hinzufügen:**
    
    ```
    git add crm.py
    
    ```
    
5. **Commit erstellen:**
    
    ```
    git commit -m "FEAT: Funktion zum Anzeigen aller Kunden hinzugefügt"
    
    ```
    
6. **Branch pushen:**
    
    ```
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
    
    ```
    git checkout -b feature/kunde-hinzufuegen
    
    ```
    
2. **Code implementieren (`crm.py`):**
    - Öffne die Datei `crm.py` in VS Code.
    - **Füge die Funktion `kunde_hinzufuegen()` hinzu:** Füge eine neue Funktion namens `kunde_hinzufuegen()` hinzu, die nach der `kunden_anzeigen()` Funktion definiert wird.
        - Innerhalb dieser Funktion:
            - Gib eine Überschrift wie "--- Kunden hinzufügen ---" aus.
            - Frage den Benutzer nach dem Namen des Kunden und speichere ihn in einer Variable `name`.
            - Frage den Benutzer nach der E-Mail des Kunden und speichere sie in einer Variable `email`.
            - Frage den Benutzer nach der Telefonnummer des Kunden und speichere sie in einer Variable `telefon`.
            - Überprüfe, ob der eingegebene `name` bereits als Schlüssel im globalen `kunden`Dictionary existiert. Wenn ja, gib eine Fehlermeldung aus, dass der Kunde bereits existiert, und beende die Funktion mit `return`.
            - Füge den neuen Kunden zum `kunden`Dictionary hinzu. Der Schlüssel soll der `name` sein. Der Wert soll ein neues Dictionary sein, das die erfassten `email` und `telefon` als Schlüssel-Wert-Paare enthält.
            - Gib eine Bestätigungsnachricht aus, dass der Kunde erfolgreich hinzugefügt wurde.
    - **Optionaler Testaufruf:** Füge am Ende der Datei vorübergehende Aufrufe von `kunde_hinzufuegen()` und `kunden_anzeigen()` hinzu, um deine Implementierung zu testen. Kommentiere diese vor dem Commit wieder aus.
3. **Testen (im Terminal):**
    - Führe das Skript aus: `python crm.py`
    - Gib Kundendaten ein und überprüfe, ob der Kunde korrekt angezeigt wird.
    - Versuche, denselben Kunden noch einmal hinzuzufügen, um die Fehlerbehandlung zu testen.
4. **Änderungen zum Staging hinzufügen:**
    
    ```
    git add crm.py
    
    ```
    
5. **Commit erstellen:**
    
    ```
    git commit -m "FEAT: Funktion zum Hinzufügen von Kunden implementiert"
    
    ```
    
6. **Branch pushen:**
    
    ```
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
    
    ```
    git checkout -b feature/interaktives-menue
    
    ```
    
2. **Code implementieren (`crm.py`):**
    - Öffne die Datei `crm.py` in VS Code.
    - **Füge die Funktion `zeige_menue()` hinzu:** Definiere eine neue Funktion namens `zeige_menue()`.
        - Innerhalb dieser Funktion:
            - Gib eine Menüüberschrift aus.
            - Gib die Optionen "1. Kunde hinzufügen", "2. Kunden anzeigen" und "3. Beenden" aus.
            - Füge eine Trennlinie hinzu.
    - **Füge die Hauptfunktion `main()` hinzu:** Definiere eine neue Funktion namens `main()`. Diese Funktion wird die Hauptlogik des Programms enthalten.
        - Innerhalb dieser Funktion:
            - Erstelle eine Endlosschleife (`while True`).
            - Innerhalb der Schleife:
                - Rufe die `zeige_menue()`Funktion auf, um das Menü anzuzeigen.
                - Frage den Benutzer nach seiner Wahl und speichere die Eingabe in einer Variable (`wahl`).
                - Verwende `if`/`elif`/`else`Anweisungen, um die `wahl` des Benutzers zu verarbeiten:
                    - Wenn `wahl` '1' ist, rufe `kunde_hinzufuegen()` auf.
                    - Wenn `wahl` '2' ist, rufe `kunden_anzeigen()` auf.
                    - Wenn `wahl` '3' ist, gib eine Abschiedsnachricht aus und beende die Schleife mit `break`.
                    - Für alle anderen Eingaben gib eine Fehlermeldung für ungültige Eingaben aus.
    - **Füge den Startpunkt des Programms hinzu:** Ersetze alle vorhandenen Testzeilen am Ende der Datei durch den Standard-Python-Block `if __name__ == "__main__":`.
        - Innerhalb dieses Blocks rufe die `main()`Funktion auf, um das Programm zu starten.
3. **Testen (im Terminal):**
    - Führe das Skript aus: `python crm.py`
    - Teste alle Menüpunkte: Kunden hinzufügen, anzeigen, beenden. Überprüfe auch ungültige Eingaben.
4. **Änderungen zum Staging hinzufügen:**
    
    ```
    git add crm.py
    
    ```
    
5. **Commit erstellen:**
    
    ```
    git commit -m "FEAT: Interaktives Menü für das CRM hinzugefügt"
    
    ```
    
6. **Branch pushen:**
    
    ```
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
    
    ```
    git checkout -b feature/kunde-suchen
    
    ```
    
2. **Code implementieren (`crm.py`):**
    - Öffne die Datei `crm.py` in VS Code.
    - **Füge die Funktion `kunde_suchen()` hinzu:** Definiere eine neue Funktion namens `kunde_suchen()` nach der `kunde_hinzufuegen()` Funktion.
        - Innerhalb dieser Funktion:
            - Gib eine Überschrift wie "--- Kunden suchen ---" aus.
            - Frage den Benutzer nach einem Suchbegriff und wandle diesen sofort in Kleinbuchstaben um (`.lower()`) für eine case-insensitive Suche.
            - Erstelle ein leeres Dictionary namens `gefundene_kunden`, um die Suchergebnisse zu speichern.
            - Iteriere über alle Kunden im globalen `kunden`Dictionary (verwende `name, details` für Schlüssel und Wert).
            - Innerhalb der Schleife: Überprüfe, ob der `suchbegriff` im `name` (kleingeschrieben) ODER in der E-Mail-Adresse (kleingeschrieben) des Kunden enthalten ist. Nutze `details.get('email', '')` um sicherzustellen, dass kein Fehler auftritt, falls ein Kunde keine E-Mail-Adresse hat.
            - Wenn eine Übereinstimmung gefunden wird, füge den Kunden zum `gefundene_kunden`Dictionary hinzu.
            - Nach der Schleife: Wenn `gefundene_kunden` leer ist, gib eine Nachricht aus, dass keine Kunden gefunden wurden, und beende die Funktion.
            - Gib eine Überschrift für die gefundenen Kunden aus.
            - Iteriere über die `gefundene_kunden` und gib deren Details aus, ähnlich wie du es in der `kunden_anzeigen()`Funktion getan hast.
    - **Aktualisiere die `zeige_menue()` Funktion:** Füge eine neue Option "3. Kunde suchen" im Menü hinzu. Passe die Nummer der "Beenden"-Option auf "4" an.
    - **Aktualisiere die `main()` Funktion:** Füge einen `elif`Block hinzu, um die neue Option "3" zu verarbeiten und `kunde_suchen()` aufzurufen. Passe auch hier die Nummer für die "Beenden"-Option auf "4" an.
3. **Testen (im Terminal):**
    - Führe das Skript aus: `python crm.py`
    - Füge einige Kunden hinzu.
    - Wähle die neue Suchfunktion im Menü und teste verschiedene Suchbegriffe (z.B. Teile von Namen, Teile von E-Mail-Adressen, existierende und nicht-existierende Begriffe).
4. **Änderungen zum Staging hinzufügen:**
    
    ```
    git add crm.py
    
    ```
    
5. **Commit erstellen:**
    
    ```
    git commit -m "FEAT: Funktion zum Suchen von Kunden implementiert"
    
    ```
    
6. **Branch pushen:**
    
    ```
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
    
    ```
    git checkout -b feature/kunde-aktualisieren
    
    ```
    
2. **Code implementieren (`crm.py`):**
    - Öffne die Datei `crm.py` in VS Code.
    - **Füge die Funktion `kunde_aktualisieren()` hinzu:** Definiere eine neue Funktion namens `kunde_aktualisieren()` nach der `kunde_suchen()` Funktion.
        - Innerhalb dieser Funktion:
            - Gib eine Überschrift wie "--- Kunden aktualisieren ---" aus.
            - Frage den Benutzer nach dem Namen des zu aktualisierenden Kunden.
            - Überprüfe, ob der Kunde mit diesem Namen im `kunden`Dictionary existiert. Wenn nicht, gib eine Fehlermeldung aus und beende die Funktion.
            - Zeige die *aktuellen* E-Mail- und Telefonnummer-Daten des gefundenen Kunden an.
            - Frage nach der neuen E-Mail-Adresse. Der Benutzer soll die Eingabe leer lassen können, wenn er die E-Mail nicht ändern möchte. Wenn eine Eingabe gemacht wird, aktualisiere die E-Mail des Kunden im Dictionary.
            - Frage nach der neuen Telefonnummer. Der Benutzer soll die Eingabe leer lassen können, wenn er die Telefonnummer nicht ändern möchte. Wenn eine Eingabe gemacht wird, aktualisiere die Telefonnummer des Kunden im Dictionary.
            - Gib eine Bestätigungsnachricht aus, dass der Kunde aktualisiert wurde.
    - **Aktualisiere die `zeige_menue()` Funktion:** Füge eine neue Option "4. Kunde aktualisieren" im Menü hinzu. Passe die Nummer der "Beenden"-Option auf "5" an.
    - **Aktualisiere die `main()` Funktion:** Füge einen `elif`Block hinzu, um die neue Option "4" zu verarbeiten und `kunde_aktualisieren()` aufzurufen. Passe auch hier die Nummer für die "Beenden"-Option auf "5" an.
3. **Testen (im Terminal):**
    - Führe das Skript aus: `python crm.py`
    - Füge einen Kunden hinzu.
    - Wähle "Kunden aktualisieren", gib den Namen des Kunden ein.
    - Teste das Aktualisieren nur der E-Mail, dann nur der Telefonnummer, dann beides.
    - Überprüfe die Änderungen mit "Kunden anzeigen".
    - Versuche, einen nicht existierenden Kunden zu aktualisieren.
4. **Änderungen zum Staging hinzufügen:**
    
    ```
    git add crm.py
    
    ```
    
5. **Commit erstellen:**
    
    ```
    git commit -m "FEAT: Funktion zum Aktualisieren von Kundendaten implementiert"
    
    ```
    
6. **Branch pushen:**
    
    ```
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
    
    ```
    git checkout -b feature/kunde-loeschen
    
    ```
    
2. **Code implementieren (`crm.py`):**
    - Öffne die Datei `crm.py` in VS Code.
    - **Füge die Funktion `kunde_loeschen()` hinzu:** Definiere eine neue Funktion namens `kunde_loeschen()` nach der `kunde_aktualisieren()` Funktion.
        - Innerhalb dieser Funktion:
            - Gib eine Überschrift wie "--- Kunden löschen ---" aus.
            - Frage den Benutzer nach dem Namen des zu löschenden Kunden.
            - Überprüfe, ob der Kunde mit diesem Namen im `kunden`Dictionary existiert.
            - Wenn der Kunde existiert, entferne ihn aus dem Dictionary (verwende `del kunden[name_zu_loeschen]`) und gib eine Bestätigungsnachricht aus.
            - Wenn der Kunde nicht existiert, gib eine Fehlermeldung aus.
    - **Aktualisiere die `zeige_menue()` Funktion:** Füge eine neue Option "5. Kunde löschen" im Menü hinzu. Passe die Nummer der "Beenden"-Option auf "6" an.
    - **Aktualisiere die `main()` Funktion:** Füge einen `elif`Block hinzu, um die neue Option "5" zu verarbeiten und `kunde_loeschen()` aufzurufen. Passe auch hier die Nummer für die "Beenden"-Option auf "6" an.
3. **Testen (im Terminal):**
    - Führe das Skript aus: `python crm.py`
    - Füge einen Kunden hinzu, lösche ihn dann und überprüfe mit "Kunden anzeigen", ob er weg ist.
    - Versuche, einen nicht existierenden Kunden zu löschen, um die Fehlermeldung zu sehen.
4. **Änderungen zum Staging hinzufügen:**
    
    ```
    git add crm.py
    
    ```
    
5. **Commit erstellen:**
    
    ```
    git commit -m "FEAT: Funktion zum Löschen von Kunden implementiert"
    
    ```
    
6. **Branch pushen:**
    
    ```
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
    
    ```
    git checkout -b feature/speichern-laden
    
    ```
    
2. **Code implementieren (`crm.py`):**
    - Öffne die Datei `crm.py` in VS Code.
    - **Importiere das `json`Modul:** Füge `import json` ganz am Anfang der Datei hinzu.
    - **Definiere den Dateinamen als Konstante:** Füge eine Konstante `DATEINAME = "kunden.json"` unter der `kunden`Dictionary-Definition hinzu.
    - **Füge die Funktion `katalog_speichern()` hinzu:** Definiere eine neue Funktion namens `katalog_speichern()` nach der `kunde_loeschen()` Funktion.
        - Innerhalb dieser Funktion:
            - Verwende einen `try-except`Block, um potenzielle `IOError` beim Speichern abzufangen.
            - Öffne die Datei mit dem Namen `DATEINAME` im Schreibmodus (`'w'`) mit UTF-8-Kodierung. Verwende die `with open(...) as f:`Syntax.
            - Speichere das globale `kunden`Dictionary als JSON in der Datei. Nutze `json.dump(kunden, f, indent=4, ensure_ascii=False)` für eine lesbare Formatierung und korrekte Behandlung von Sonderzeichen.
            - Gib eine Erfolgs- oder Fehlermeldung aus.
    - **Füge die Funktion `katalog_laden()` hinzu:** Definiere eine neue Funktion namens `katalog_laden()` nach der `katalog_speichern()` Funktion.
        - Innerhalb dieser Funktion:
            - Deklariere `global kunden` am Anfang der Funktion, um die globale Variable `kunden` innerhalb der Funktion ändern zu können.
            - Verwende einen `try-except`Block, um `FileNotFoundError` (wenn die Datei noch nicht existiert), `json.JSONDecodeError` (wenn die Datei kein gültiges JSON enthält) und allgemeine `Exception`s abzufangen.
            - Versuche, die Datei `DATEINAME` im Lesemodus (`'r'`) mit UTF-8-Kodierung zu öffnen.
            - Lade die JSON-Daten in das `kunden`Dictionary. Nutze `kunden.update(json.load(f))`.
            - Gib entsprechende Erfolgs- oder Fehlermeldungen aus.
            - Im Falle eines Fehlers (Datei nicht gefunden, ungültiges JSON, etc.) setze `kunden` auf ein leeres Dictionary (`kunden.clear()`), um sicherzustellen, dass das Programm mit einem sauberen Zustand startet.
    - **Aktualisiere die `main()` Funktion:**
        - Rufe `katalog_laden()` ganz am Anfang der `main()` Funktion auf, bevor die `while True`Schleife beginnt, um die Daten beim Programmstart zu laden.
        - Rufe `katalog_speichern()` auf, bevor das Programm beendet wird (innerhalb des `elif wahl == '6':` Blocks, direkt vor dem `break`Statement), um die Änderungen zu speichern.
3. **Testen (im Terminal):**
    - Führe das Skript aus. Füge einige Kunden hinzu. Beende das Programm (Option 6).
    - Starte das Programm erneut. Sind die Kunden noch da? (Sie sollten aus `kunden.json` geladen werden).
    - Öffne die Datei `kunden.json` in VS Code, um den gespeicherten JSON-Inhalt zu sehen.
    - Lösche die `kunden.json`Datei manuell im Explorer und starte das Programm. Es sollte mit einem leeren Katalog starten und die Meldung "Keine vorhandene Katalogdatei gefunden." anzeigen.
4. **Änderungen zum Staging hinzufügen:**
    
    ```
    git add crm.py
    git add kunden.json # Füge auch die neue JSON-Datei hinzu, wenn sie erstellt wurde
    
    ```
    
5. **Commit erstellen:**
    
    ```
    git commit -m "FEAT: Katalog speichern und laden mit JSON implementiert"
    
    ```
    
6. **Branch pushen:**
    
    ```
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
    
    ```
    git checkout -b chore/eingabe-validierung
    
    ```
    
2. **Code implementieren (`crm.py`):**
    - Öffne die Datei `crm.py` in VS Code.
    - **Importiere das `re`Modul:** Füge `import re` ganz am Anfang der Datei hinzu (unter `import json`), falls du reguläre Ausdrücke für die E-Mail-Validierung verwenden möchtest.
    - **Passe `kunde_hinzufuegen()` an:**
        - Ändere die Eingabeaufforderung für die E-Mail: Implementiere eine `while True`Schleife, die den Benutzer nach der E-Mail fragt. Überprüfe innerhalb der Schleife, ob die eingegebene E-Mail ein gültiges Format hat (z.B. mit `re.match(r"[^@]+@[^@]+\.[^@]+", email)` oder einer einfacheren Prüfung auf `@` und `.`). Wenn das Format ungültig ist, gib eine Fehlermeldung aus und fahre mit der Schleife fort. Wenn gültig, beende die Schleife mit `break`.
        - Ändere die Eingabeaufforderung für die Telefonnummer: Implementiere eine ähnliche `while True`Schleife. Frage nach der Telefonnummer. Überprüfe, ob die Eingabe nur Ziffern enthält (z.B. mit `telefon.isdigit()` oder `telefon.replace('+', '').isdigit()` wenn ein führendes `+` erlaubt ist). Wenn ungültig, gib eine Fehlermeldung aus und frage erneut. Wenn gültig, beende die Schleife.
    - **Passe `kunde_aktualisieren()` an:**
        - Wende die gleichen Validierungslogiken für die neue E-Mail und Telefonnummer an, wie du sie in `kunde_hinzufuegen()` implementiert hast. Achte darauf, dass die Validierung nur dann erfolgt, wenn der Benutzer tatsächlich eine neue E-Mail oder Telefonnummer eingibt (d.h., die Eingabe nicht leer lässt). Wenn die Eingabe leer ist, soll keine Validierung stattfinden und der Wert unverändert bleiben.
3. **Testen (im Terminal):**
    - Führe das Skript aus: `python crm.py`
    - Versuche, einen Kunden hinzuzufügen. Gib ungültige E-Mail-Formate (z.B. "test", "test@") und Telefonnummern (z.B. "abc", "123a") ein. Beobachte die Fehlermeldungen und die Aufforderung zur erneuten Eingabe.
    - Teste auch die Aktualisierungsfunktion mit ungültigen Eingaben.
4. **Änderungen zum Staging hinzufügen:**
    
    ```
    git add crm.py
    
    ```
    
5. **Commit erstellen:**
    
    ```
    git commit -m "CHORE: Eingabevalidierung für E-Mail und Telefonnummer implementiert"
    
    ```
    
6. **Branch pushen:**
    
    ```
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
    
    ```
    git checkout -b chore/code-dokumentation
    
    ```
    
2. **Code implementieren (`crm.py`):**
    - Öffne die Datei `crm.py` in VS Code.
    - **Modul-Docstring:** Füge ganz am Anfang der Datei (direkt unter den `import`Anweisungen) einen Modul-Docstring hinzu. Dieser sollte den allgemeinen Zweck des `crm.py`Skripts beschreiben (z.B. "Ein einfaches Python-Programm zur Verwaltung eines Kundenmanagement-Systems (CRM). Es ermöglicht das Hinzufügen, Anzeigen, Suchen, Aktualisieren und Löschen von Kunden sowie das Speichern und Laden der Kundendaten in/aus einer JSON-Datei.").
    - **Funktions-Docstrings:** Gehe jede Funktion in deiner `crm.py`Datei durch (`kunden_anzeigen`, `kunde_hinzufuegen`, `kunde_suchen`, `kunde_aktualisieren`, `kunde_loeschen`, `katalog_speichern`, `katalog_laden`, `zeige_menue`, `main`).
        - Füge für jede Funktion einen Docstring hinzu. Platziere den Docstring direkt unter der `def`Zeile der Funktion (drei doppelte Anführungszeichen `"""`).
        - Beschreibe im Docstring prägnant, was die Funktion tut.
        - Wenn die Funktion Parameter hat, liste diese auf und beschreibe ihre Bedeutung.
        - Wenn die Funktion einen Wert zurückgibt, beschreibe, was zurückgegeben wird.
    - **Inline-Kommentare:** Gehe den gesamten Code durch und füge kurze, erklärende Inline-Kommentare (`#`) an Stellen hinzu, an denen die Logik komplexer ist oder nicht sofort ersichtlich. Dies kann Schleifen, bedingte Anweisungen, Dictionary-Manipulationen oder Fehlerbehandlungsblöcke umfassen. Ziel ist es, die Lesbarkeit und das Verständnis des Codes zu verbessern.
3. **Testen (im Terminal):**
    - Führe das Skript aus: `python crm.py`
    - Überprüfe, ob das Programm weiterhin korrekt funktioniert.
    - Die Hauptaufgabe des Tests ist hier die Überprüfung der **Lesbarkeit** des Codes. Lies den Code durch und versuche, die Logik nur anhand der Kommentare und Docstrings zu verstehen.
4. **Änderungen zum Staging hinzufügen:**
    
    ```
    git add crm.py
    
    ```
    
5. **Commit erstellen:**
    
    ```
    git commit -m "CHORE: Code mit Docstrings und Kommentaren dokumentiert"
    
    ```
    
6. **Branch pushen:**
    
    ```
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