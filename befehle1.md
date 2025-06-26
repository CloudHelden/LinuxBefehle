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

## Übungsaufgaben (Kombinationen aus 3–4 Befehlen)

> **So funktioniert’s:** Lies zuerst nur die Schritt‑Beschreibung. Klappe dann **Tipps anzeigen** (nur Befehle) oder **Lösung anzeigen** (kompletter Code) auf, wenn du Hilfe benötigst.

---

### Aufgabe 1 – Mini‑Projektordner erstellen und prüfen

1. Lege ein neues Verzeichnis namens **projekt** an.
2. Wechsle in dieses Verzeichnis.
3. Erstelle eine leere Datei **readme.txt**.
4. Schreibe den Text *Hallo Shell* in die Datei.
5. Gib den Inhalt der Datei im Terminal aus.

<details><summary>Tipps anzeigen</summary>

```
mkdir
cd
touch
echo
cat
```

</details>

<details><summary>Lösung anzeigen</summary>

```bash
mkdir projekt
cd projekt
touch readme.txt
echo "Hallo Shell" > readme.txt
cat readme.txt
```

</details>

---

### Aufgabe 2 – Datei sichern

1. Lege einen Ordner **\~/backup** an.
2. Kopiere die Datei **datei.txt** in diesen Ordner.
3. Liste den Inhalt des Ordners auf, um die Sicherung zu prüfen.

<details><summary>Tipps anzeigen</summary>

```
mkdir
cp
ls
```

</details>

<details><summary>Lösung anzeigen</summary>

```bash
mkdir ~/backup
cp datei.txt ~/backup/
ls -l ~/backup
```

</details>

---

### Aufgabe 3 – Datei archivieren und Verzeichnis anzeigen

1. Lege einen Unterordner **old** im aktuellen Verzeichnis an.
2. Verschiebe die Datei **data.txt** in diesen Ordner.
3. Benenne die Datei so um, dass das aktuelle Datum angehängt wird (z. B. `data_$(date +%F).txt`).
4. Zeige den Pfad des aktuellen Arbeitsverzeichnisses an.

<details><summary>Tipps anzeigen</summary>

```
mkdir
mv
date
pwd
```

</details>

<details><summary>Lösung anzeigen</summary>

```bash
mkdir old
mv data.txt old/
mv old/data.txt old/data_$(date +%F).txt
pwd
```

</details>

---

### Aufgabe 4 – Verlauf sichern und untersuchen

1. Exportiere deinen Shell‑Verlauf in die Datei **hist.txt** (`history > hist.txt`).
2. Prüfe den Dateityp von **hist.txt**.
3. Öffne die Datei seitenweise, um den Verlauf zu durchstöbern (Navigation in *less*: *Leertaste* vorwärts, *b* rückwärts, *q* beenden).

<details><summary>Tipps anzeigen</summary>

```
history
file
less
```

</details>

<details><summary>Lösung anzeigen</summary>

```bash
history > hist.txt
file hist.txt
less hist.txt
```

</details>

---

### Aufgabe 5 – Komfort‑Listing per Alias

1. Definiere einen Alias **LL**, der eine lange Listenansicht aller Dateien zeigt.
2. Lass dir anzeigen, wie der Alias definiert ist.
3. Nutze den Alias, um den Inhalt des aktuellen Verzeichnisses aufzulisten.

<details><summary>Tipps anzeigen</summary>

```
alias
```

</details>

<details><summary>Lösung anzeigen</summary>

```bash
alias LL='ls -la'
alias LL
LL
```

</details>

---

## Kurzübungen 

---

### Kurzübung 1 – Home & Übersicht

1. Wechsle in dein Home‑Verzeichnis.
2. Liste **alle** Dateien und Ordner (auch versteckte) detailliert auf.

<details><summary>Tipps anzeigen</summary>

```
cd
ls -la
```

</details>

<details><summary>Lösung anzeigen</summary>

```bash
cd ~
ls -la
```

</details>

---

### Kurzübung 2 – Backup Schnellkopie

1. Lege im aktuellen Verzeichnis einen Ordner **backup** an.
2. Kopiere die Datei **notes.txt**  und benenne sie dabei zu **notes\_backup.txt** um.
3. Prüfe durch Auflisten des Ordners, ob die Kopie da ist.

<details><summary>Tipps anzeigen</summary>

```
mkdir
cp
ls
```

</details>

<details><summary>Lösung anzeigen</summary>

```bash
mkdir backup
cp notes.txt backup/notes_backup.txt
ls -l backup
```

</details>

---

### Kurzübung 3 – Falscher Dateiname korrigieren

1. Im aktuellen Ordner liegt eine Datei **reprot.txt** (Tippfehler).
2. Benenne die Datei korrekt in **report.txt** um.
3. Zeige den Ordnerinhalt, um den neuen Namen zu prüfen.

<details><summary>Tipps anzeigen</summary>

```
mv
ls
```

</details>

<details><summary>Lösung anzeigen</summary>

```bash
mv reprot.txt report.txt
ls -l
```

</details>

---

### Kurzübung 4 – Leeres Verzeichnis anlegen und entfernen (Fehler‑Challenge)

1. Erstelle im aktuellen Pfad ein leeres Verzeichnis **tmp\_empty**.
2. Entferne dieses Verzeichnis wieder.
3. Liste danach den Ordnerinhalt, um zu prüfen, dass es wirklich weg ist.

<details><summary>Tipps anzeigen</summary>

```
mkdir
rm -r
ls
```

> **Erklärung:** `mkdir` legt Ordner an, `rm -r` entfernt sie rekursiv. Für leere Ordner ginge auch `rmdir` (nicht in Grundliste).

</details>

<details><summary>Lösung anzeigen</summary>

```bash
mkdir tmp_empty
rm -r tmp_empty
ls -l
```

</details>

---

### Kurzübung 5 – Verzeichnisstruktur Check

1. Gib das aktuelle Arbeitsverzeichnis aus.
2. Wechsle eine Ebene nach oben.
3. Liste den Inhalt des neuen Pfades detailliert auf.

<details><summary>Tipps anzeigen</summary>

```
pwd
cd ..
ls -l
```

</details>

<details><summary>Lösung anzeigen</summary>

```bash
pwd
cd ..
ls -l
```

</details>
