Git & Python Lernprojekt: Dein Kundenmanagement-System (CRM) - Vollständige erste Version
Dies ist die vollständige Implementierung des Kundenmanagement-Systems (CRM) in Python, wie sie vor der Einführung der Code-Lücken und TODO-Aufgaben aussah. Du kannst diese Version verwenden, um die Lösungen für die TODO-Aufgaben in der anderen Version zu überprüfen oder um den Schülern den vollständigen Code zu zeigen, nachdem sie ihre eigenen Implementierungen versucht haben.

Projektübersicht: Das Kundenmanagement-System
Dieses Python-Programm ermöglicht das Hinzufügen, Anzeigen, Suchen, Aktualisieren und Löschen von Kunden. Die Kundendaten werden lokal in einer JSON-Datei gespeichert und geladen.

Vorbereitung: Projekt initialisieren (Einmalig)
Die Schritte zur Initialisierung des Projekts bleiben gleich, da sie die grundlegende Git-Struktur und GitHub-Verbindung herstellen.

Öffne VS Code.

Öffne das Terminal: Terminal > New Terminal.

Navigiere zum gewünschten Speicherort:

cd ~ # Oder ein anderer Projektordner

Erstelle einen neuen Projektordner:

mkdir CRMProjekt
cd CRMProjekt

Initialisiere ein Git-Repository:

git init

Erstelle die Hauptdatei für dein Programm:

Klicke im VS Code Explorer auf "New File" und nenne die Datei crm.py.

Füge einen Kommentar hinzu: # Dein Kundenmanagement-System

Speichere die Datei.

Füge die Datei zum Staging hinzu und mache den ersten Commit:

git add crm.py
git commit -m "Initialer Commit: Leere crm.py erstellt"

Erstelle ein neues Repository auf GitHub:

Gehe zu github.com und melde dich an.

Klicke auf "+" > "New repository".

Nenne es CRMProjekt.

Wähle "Public" oder "Private".

WICHTIG: Wähle NICHT die Optionen zum Initialisieren des Repositories mit einer README, .gitignore oder Lizenz.

Klicke auf "Create repository".

Verbinde dein lokales Repo mit GitHub und pushe:

Kopiere die URL von GitHub (z.B. https://github.com/DeinBenutzername/CRMProjekt.git).

Im VS Code Terminal:

git remote add origin https://github.com/DeinBenutzername/CRMProjekt.git
git branch -M main
git push -u origin main

Überprüfe auf GitHub, ob deine crm.py-Datei hochgeladen wurde.

Die Tickets: Schritt für Schritt zum CRM (Vollständiger Code)
Hier ist der vollständige Code für jedes Ticket.

TICKET-001: Grundgerüst und Kundenliste anzeigen
Beschreibung:
Implementiere ein leeres Python-Dictionary, das als Speicher für deine Kunden dient. Füge eine Funktion hinzu, die alle aktuell im CRM vorhandenen Kunden anzeigt.

Vollständiger Code (crm.py):

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

TICKET-002: Kunden hinzufügen
Beschreibung:
Implementiere eine Funktion, die es dem Benutzer erlaubt, einen neuen Kunden mit Namen, E-Mail und Telefonnummer zum Katalog hinzuzufügen.

Vollständiger Code (crm.py):

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

TICKET-003: Interaktives Menü
Beschreibung:
Erstelle ein einfaches Textmenü, das dem Benutzer erlaubt, zwischen den Funktionen "Kunden hinzufügen" und "Kunden anzeigen" zu wählen. Das Menü soll in einer Schleife laufen, bis der Benutzer das Programm beendet.

Vollständiger Code (crm.py):

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

# Startet das Hauptprogramm, wenn die Datei direkt ausgeführt wird
if __name__ == "__main__":
    main()

TICKET-004: Kunden suchen
Beschreibung:
Füge eine Funktion hinzu, die es dem Benutzer erlaubt, Kunden nach einem Teil des Namens oder der E-Mail-Adresse zu suchen. Die Suche soll alle passenden Kunden anzeigen.

Vollständiger Code (crm.py):

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

TICKET-005: Kunden aktualisieren
Beschreibung:
Füge eine Funktion hinzu, die es dem Benutzer erlaubt, die E-Mail-Adresse und/oder die Telefonnummer eines bestehenden Kunden anhand seines Namens zu aktualisieren.

Vollständiger Code (crm.py):

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

TICKET-006: Kunden löschen
Beschreibung:
Implementiere eine Funktion, die es dem Benutzer erlaubt, einen Kunden anhand seines Namens aus dem CRM zu entfernen.

Vollständiger Code (crm.py):

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

TICKET-007: Daten speichern und laden (JSON)
Beschreibung:
Implementiere Funktionen, um die Kundendatenbank in einer JSON-Datei zu speichern und beim Start des Programms zu laden.

Vollständiger Code (crm.py):

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

def katalog_speichern(): # NEU
    try:
        with open(DATEINAME, 'w', encoding='utf-8') as f:
            json.dump(kunden, f, indent=4, ensure_ascii=False)
        print(f"Katalog erfolgreich in '{DATEINAME}' gespeichert.")
    except IOError as e:
        print(f"Fehler beim Speichern des Katalogs: {e}")

def katalog_laden(): # NEU
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
    print("6. Beenden") # GEÄNDERT
    print("----------------")

def main():
    katalog_laden() # GEÄNDERT: Laden beim Start
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
        elif wahl == '6': # GEÄNDERT
            katalog_speichern() # GEÄNDERT: Speichern vor dem Beenden
            print("Programm wird beendet. Auf Wiedersehen!")
            break
        else:
            print("Ungültige Eingabe. Bitte versuchen Sie es erneut.")

if __name__ == "__main__":
    main()

TICKET-008: Eingabevalidierung
Beschreibung:
Verbessere die Robustheit deines Programms, indem du Benutzereingaben validierst (z.B. E-Mail-Format, Telefonnummer nur Ziffern) und geeignete Fehlermeldungen ausgibst.

Vollständiger Code (crm.py):

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

def kunde_hinzufuegen(): # GEÄNDERT: Mit Validierung
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
    for name, details in gefundene_kunden.items():
        print(f"Name: {name}")
        print(f"  E-Mail: {details.get('email', 'N/A')}")
        print(f"  Telefon: {details.get('telefon', 'N/A')}")
        print("-------------------------")

def kunde_aktualisieren(): # GEÄNDERT: Mit Validierung
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

TICKET-009: Code-Dokumentation (Docstrings & Kommentare)
Beschreibung:
Füge Docstrings zu allen Funktionen und Modulen hinzu, die deren Zweck, Parameter und Rückgabewerte beschreiben. Ergänze außerdem sinnvolle Inline-Kommentare, um komplexe Logik zu erklären und die Lesbarkeit des Codes zu verbessern.

Vollständiger Code (crm.py):

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
