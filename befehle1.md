# Übungsaufgaben 

> **So funktioniert’s:** Lies zuerst nur die Schritt‑Beschreibung. Klappe dann **Tipps anzeigen** (nur Befehle) auf, wenn du Hilfe benötigst. Die vollständigen Lösungen findest du im Abschnitt **„Lösungen“** am Ende des Dokuments.

---

### Aufgabe 1 – Mini‑Projektordner erstellen und prüfen

1. Lege ein neues Verzeichnis namens **projekt** an.
2. Wechsle in dieses Verzeichnis.
3. Erstelle eine leere Datei **readme.txt**.
4. Schreibe den Text *Hallo Shell* in die Datei.
5. Gib den Inhalt der Datei im Terminal aus.

<details><summary>Tipps anzeigen</summary>

```bash
mkdir
cd
touch
echo
cat
```

</details>

---

### Aufgabe 2 – Datei sichern

1. Lege einen Ordner **\~/backup** an.
2. Kopiere die Datei **datei.txt** in diesen Ordner.
3. Liste den Inhalt des Ordners auf, um die Sicherung zu prüfen.

<details><summary>Tipps anzeigen</summary>

```bash
mkdir
cp
ls
```

</details>

---

### Aufgabe 3 – Datei archivieren und Verzeichnis anzeigen

1. Lege einen Unterordner **old** im aktuellen Verzeichnis an.
2. Verschiebe die Datei **data.txt** in diesen Ordner.
3. Benenne die Datei so um, dass das aktuelle Datum angehängt wird (z. B. `data_$(date +%F).txt`).
4. Zeige den Pfad des aktuellen Arbeitsverzeichnisses an.

<details><summary>Tipps anzeigen</summary>

```bash
mkdir
mv
date
pwd
```

</details>

---

### Aufgabe 4 – Verlauf sichern und untersuchen

1. Exportiere deinen Shell‑Verlauf in die Datei **hist.txt** (`history > hist.txt`).
2. Prüfe den Dateityp von **hist.txt**.
3. Öffne die Datei seitenweise, um den Verlauf zu durchstöbern (Navigation in *less*: *Leertaste* vorwärts, *b* rückwärts, *q* beenden).

<details><summary>Tipps anzeigen</summary>

```bash
history
file
less
```

</details>

---

### Aufgabe 5 – Komfort‑Listing per Alias

1. Definiere einen Alias **LL**, der eine lange Listenansicht aller Dateien zeigt.
2. Lass dir anzeigen, wie der Alias definiert ist.
3. Nutze den Alias, um den Inhalt des aktuellen Verzeichnisses aufzulisten.

<details><summary>Tipps anzeigen</summary>

```bash
alias
```

</details>

---

## Kurzübungen

### Kurzübung 1 – Home & Übersicht

1. Wechsle in dein Home‑Verzeichnis.
2. Liste **alle** Dateien und Ordner (auch versteckte) detailliert auf.

<details><summary>Tipps anzeigen</summary>

```bash
cd
ls -la
```

</details>

---

### Kurzübung 2 – Backup Schnellkopie

1. Lege im aktuellen Verzeichnis einen Ordner **backup** an.
2. Kopiere die Datei **notes.txt** und benenne sie dabei zu **notes\_backup.txt** um.
3. Prüfe durch Auflisten des Ordners, ob die Kopie da ist.

<details><summary>Tipps anzeigen</summary>

```bash
mkdir
cp
ls
```

</details>

---

### Kurzübung 3 – Falscher Dateiname korrigieren

1. Im aktuellen Ordner liegt eine Datei **reprot.txt** (Tippfehler).
2. Benenne die Datei korrekt in **report.txt** um.
3. Zeige den Ordnerinhalt, um den neuen Namen zu prüfen.

<details><summary>Tipps anzeigen</summary>

```bash
mv
ls
```

</details>

---

### Kurzübung 4 – Leeres Verzeichnis anlegen und entfernen (Fehler‑Challenge)

1. Erstelle im aktuellen Pfad ein leeres Verzeichnis **tmp\_empty**.
2. Entferne dieses Verzeichnis wieder.
3. Liste danach den Ordnerinhalt, um zu prüfen, dass es wirklich weg ist.

<details><summary>Tipps anzeigen</summary>

```bash
mkdir
rm -r
ls
```

> **Hinweis:** `mkdir` legt Ordner an, `rm -r` entfernt sie rekursiv. Für leere Ordner ginge auch `rmdir`.

</details>

---

### Kurzübung 5 – Verzeichnisstruktur Check

1. Gib das aktuelle Arbeitsverzeichnis aus.
2. Wechsle eine Ebene nach oben.
3. Liste den Inhalt des neuen Pfades detailliert auf.

<details><summary>Tipps anzeigen</summary>

```bash
pwd
cd ..
ls -l
```

</details>

---

## Lösungen

### Aufgabe 1 – Mini‑Projektordner

<details><summary>Lösung anzeigen</summary>

```bash
mkdir projekt
cd projekt
touch readme.txt
echo "Hallo Shell" > readme.txt
cat readme.txt
```

</details>

### Aufgabe 2 – Datei sichern

<details><summary>Lösung anzeigen</summary>

```bash
mkdir ~/backup
cp datei.txt ~/backup/
ls -l ~/backup
```

</details>

### Aufgabe 3 – Datei archivieren und Verzeichnis anzeigen

<details><summary>Lösung anzeigen</summary>

```bash
mkdir old
mv data.txt old/
mv old/data.txt old/data_$(date +%F).txt
pwd
```

</details>

### Aufgabe 4 – Verlauf sichern und untersuchen

<details><summary>Lösung anzeigen</summary>

```bash
history > hist.txt
file hist.txt
less hist.txt
```

</details>

### Aufgabe 5 – Komfort‑Listing per Alias

<details><summary>Lösung anzeigen</summary>

```bash
alias LL='ls -la'
alias LL
LL
```

</details>

### Kurzübung 1 – Home & Übersicht

<details><summary>Lösung anzeigen</summary>

```bash
cd ~
ls -la
```

</details>

### Kurzübung 2 – Backup Schnellkopie

<details><summary>Lösung anzeigen</summary>

```bash
mkdir backup
cp notes.txt backup/notes_backup.txt
ls -l backup
```

</details>

### Kurzübung 3 – Falscher Dateiname korrigieren

<details><summary>Lösung anzeigen</summary>

```bash
mv reprot.txt report.txt
ls -l
```

</details>

### Kurzübung 4 – Leeres Verzeichnis anlegen und entfernen

<details><summary>Lösung anzeigen</summary>

```bash
mkdir tmp_empty
rm -r tmp_empty
ls -l
```

</details>

### Kurzübung 5 – Verzeichnisstruktur Check

<details><summary>Lösung anzeigen</summary>

```bash
pwd
cd ..
ls -l
```

</details>
