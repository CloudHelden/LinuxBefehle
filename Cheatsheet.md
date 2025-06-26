# Grundlegende Shell‑Befehle

| Nr. | Befehl    | Kurzbeschreibung                                             | Beispiel                      |        |
| --- | --------- | ------------------------------------------------------------ | ----------------------------- | ------ |
| 2   | `pwd`     | Gibt das aktuelle Arbeitsverzeichnis aus.                    | `pwd`                         |        |
| 3   | `cd`      | Wechselt in ein anderes Verzeichnis.                         | `cd /tmp`                     |        |
| 4   | `ls`      | Listet Inhalte eines Verzeichnisses.                         | `ls -l`                       |        |
| 5   | `touch`   | Erstellt eine leere Datei oder aktualisiert den Zeitstempel. | `touch beispiel.txt`          |        |
| 6   | `file`    | Zeigt den Dateityp einer Datei an.                           | `file beispiel.txt`           |        |
| 7   | `cat`     | Gibt den Inhalt von Dateien aus.                             | `cat beispiel.txt`            |        |
| 8   | `less`    | Blättert komfortabel durch längere Dateien.                  | `less /var/log/syslog`        |        |
| 9   | `history` | Listet zuletzt eingegebene Befehle auf.                      | \`history                     | tail\` |
| 10  | `cp`      | Kopiert Dateien oder Ordner.                                 | `cp quelle.txt ziel.txt`      |        |
| 11  | `mv`      | Verschiebt oder benennt Dateien/Ordner.                      | `mv altname.txt neuename.txt` |        |
| 12  | `mkdir`   | Erstellt ein neues Verzeichnis.                              | `mkdir neuer_ordner`          |        |
| 13  | `rm`      | Entfernt Dateien oder Verzeichnisse.                         | `rm beispiel.txt`             |        |
| 14  | `find`    | Durchsucht Verzeichnisse rekursiv.                           | `find . -name "*.txt"`        |        |
| 15  | `help`    | Zeigt Hilfe für Shell‑Builtins.                              | `help cd`                     |        |
| 16  | `man`     | Öffnet die Handbuchseite eines Befehls.                      | `man ls`                      |        |
| 17  | `whatis`  | Gibt eine Kurzbeschreibung eines Befehls.                    | `whatis grep`                 |        |
| 18  | `alias`   | Erstellt oder listet Aliase.                                 | `alias ll='ls -l'`            |        |
| 19  | `exit`    | Beendet die aktuelle Shell‑Sitzung.                          | `exit`                        |        |

---

### Gruppenübung – Befehlskette

1. **Vorbereitung:** Alle Teilnehmenden starten jeweils eine neue Ubuntu‑EC2‑Instanz (z. B. über die AWS‑Konsole).
2. **Spielablauf:** Reihum bestimmt eine Person die Aktion, die nächste nennt den passenden Shell‑Befehl.

   * Beispiel: *Person 1*: „Erstelle einen Ordner“ → *Person 2*: `mkdir test`.
   * Anschließend führen **alle** den genannten Befehl gleichzeitig aus und beobachten die Ausgabe.
   * Danach übernimmt *Person 2* das Ansagen der nächsten Aktion; *Person 3* liefert den Befehl usw.
3. **Ziel:** Gemeinsam eine fortlaufende Befehls­kette entwickeln, Verständnis vertiefen und auftretende Fehler direkt diskutieren.

---