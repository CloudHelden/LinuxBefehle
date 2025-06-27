# Linux‑I/O‑Streams



## Umleitung und Pipes

* **Ausgabe in eine Datei schreiben (überschreiben)**

  ```bash
  echo "Zeile A" > datei.txt
  ```
* **An Datei anhängen**

  ```bash
  echo "Zeile B" >> datei.txt
  ```

---

## 1 · Standardausgabe (stdout)

Die **Standardausgabe** ist der Datenstrom, über den Programme ihr Ergebnis ausgeben; standardmäßig landet sie im Terminalfenster.

| Befehl                                  | Wirkung                                                                        |
| --------------------------------------- | ------------------------------------------------------------------------------ |
| `echo "Hallo Welt"`                     | Gibt *Hallo Welt* im Terminal aus.                                             |
| `echo "Hallo Welt" > peanuts.txt`       | Leitet stdout in die Datei `peanuts.txt` um (neu angelegt oder überschrieben). |
| `echo "Noch eine Zeile" >> peanuts.txt` | Hängt den Text ans Ende der Datei an.                                          |

### Kurzübungen

1. **Willkommen‑Datei:** Erstelle mit einem einzigen Befehl eine Datei `welcome.txt`, die die Zeile *Willkommen bei Linux I/O!* enthält.
2. **Zählen:** Lass dir die Zeilenanzahl von `peanuts.txt` mit `wc -l` anzeigen, ohne den Inhalt auf dem Bildschirm zu sehen.
3. **Überschreiben vs. Anhängen:** Schreibe *Neu* in `status.txt`, hänge anschließend *Fertig* an dieselbe Datei an und zeige den Inhalt an.

---

## 2 · Standardeingabe (stdin)

Die **Standardeingabe** ist der Datenstrom, aus dem Programme lesen. Üblicherweise ist das die Tastatur, doch er lässt sich umleiten.

| Befehl                           | Wirkung                                                                                |
| -------------------------------- | -------------------------------------------------------------------------------------- |
| `cat < peanuts.txt`              | Liest den Inhalt von `peanuts.txt` als stdin und zeigt ihn auf stdout (Bildschirm) an. |
| `cat < peanuts.txt > banana.txt` | Liest aus `peanuts.txt` (stdin) und schreibt das Ergebnis in `banana.txt` (stdout).    |

### Kurzübungen

1. **Worte zählen:** Leite `peanuts.txt` via `<` in `wc -w`, um die Wortanzahl zu bestimmen.
2. **Sortieren:** Erstelle `numbers.txt` mit den Zeilen 3, 1, 2. Sortiere die Datei per `sort` und `<` in `sorted.txt`.
3. Was ist der unterschied wenn ich echo oder printf verwende für Aufgabe 2?
4. **Vergleichen:** Nutze `diff` mit `<` für zwei Dateien (`peanuts.txt` und `banana.txt`) und leite das Ergebnis auf den Bildschirm.

---

## 3 · Standardfehler (stderr)

Über **stderr** geben Programme Fehlermeldungen aus. stdout und stderr sind voneinander getrennt und lassen sich separat umleiten.

> **Hinweis:** Wir nutzen den nicht vorhandenen Pfad `nothere`, um Fehlermeldungen zu erzeugen.

| Befehl                            | Wirkung                                                                                                                                          |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| `ls nothere 2> peanuts.txt`       | Schreibt nur Fehlermeldungen (stderr) in `peanuts.txt`.                                                                                          |
| `ls . nothere > peanuts.txt 2>&1` | Listet erst den aktuellen Ordner (`.`) auf **(stdout)** und schreibt anschließend die Fehlermeldung zu `nothere` **(stderr)** in dieselbe Datei. |
| `ls . nothere &> peanuts.txt`     | Kurzschreibweise: stdout **und** stderr landen gemeinsam in der Datei.                                                                           |
| `ls nothere 2> /dev/null`         | Verwirft alle Fehlermeldungen (stderr), indem sie in das schwarze Loch `/dev/null` umgeleitet werden.                                            |

### Kurzübungen

1. **Nur Fehler sichern:** Leite die Fehlermeldung von `cat missing.txt` in `error.log`, ohne stdout (falls vorhanden) zu speichern.
2. **Fehler unterdrücken:** Führe `grep "foo" missing.txt` aus und verwerfe dabei komplett das stderr.
3. **Gemeinsame Logdatei:** Kombiniere stdout und stderr von `find / -name "passwd"` in `find.log`, um alle Ausgaben an einem Ort zu sammeln.

---

## 4 · Pipe (|) und `tee`

Die **Pipe** (`|`) leitet die Standardausgabe eines Befehls als Standardeingabe an den nächsten Befehl weiter – wie ein Schlauch zwischen zwei Prozessen.

| Befehl        | Erklärung  |                                                                                                        |             |
| ------------- | ---------- | ------------------------------------------------------------------------------------------------------ | ----------- |
| \`ls -la /etc | less\`     | Übergibt die Dateiliste von `/etc` an `less`, damit du bequem darin blättern kannst.                   |             |
| \`sudo dmesg  | grep usb\` | Zeigt Kernel‑Meldungen an und filtert nach „usb“. Falls `dmesg` gesperrt ist, verwende \`journalctl -k | grep usb\`. |

### Ausgabe gleichzeitig speichern

Mit **`tee`** lässt sich stdout *sowohl* auf dem Bildschirm als auch in eine Datei schreiben.

| Befehl | Wirkung           |                                                                             |
| ------ | ----------------- | --------------------------------------------------------------------------- |
| \`ls   | tee peanuts.txt\` | Zeigt das Ergebnis von `ls` und schreibt es parallel in `peanuts.txt`.      |
| \`ls   | tee -a log.txt\`  | Dasselbe, aber mit `-a` (*append*) wird an eine vorhandene Datei angehängt. |

### Kurzübungen

1. **Durchzählen:** Erzeuge mit `seq 1 100 | tee zahlen.txt | less` eine Liste von 1 bis 100, blättere darin und speichere sie gleichzeitig.
2. **Mehrere Filter:** Verkette `cat /etc/passwd | cut -d":" -f1 | sort | tee userlist.txt | head -n 5`, um die ersten fünf Usernamen alphabetisch zu sehen und in `userlist.txt` abzulegen.
3. **Wortfrequenz:** `cat peanuts.txt | tr -cs 'A-Za-z' '\n' | tr 'A-Z' 'a-z' | sort | uniq -c | tee freq.txt | sort -nr | head`, um Häufigkeiten der Wörter zu ermitteln und im Terminal plus Datei anzuzeigen.

---
