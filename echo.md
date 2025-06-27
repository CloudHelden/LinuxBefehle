# Linux‑I/O‑Streams

Bevor wir uns `echo` ansehen, solltest du wissen, was die Shell ist:

* **Shell**: Ein Programm, das Befehle entgegennimmt und ausführt. Unter Ubuntu ist die standardmäßige Shell die **Bash**.
* Du interagierst mit der Shell über ein **Terminal** (z. B. GNOME Terminal).
* Befehle in der Shell bestehen aus einem **Kommando** und optionalen **Optionen** und **Argumenten**.

---

## Was ist `echo`?

* `echo` ist ein einfaches Kommando, das Text auf dem Bildschirm ausgibt.
* Es hilft dir, Nachrichten anzuzeigen, Inhalte von Variablen oder Ergebnissen von Berechnungen zu sehen.
* Syntax:

  ```bash
  echo [OPTIONEN] TEXT
  ```

---

## Aufbau eines Terminals

Ein Terminal zeigt dir typischerweise eine Eingabeaufforderung (`prompt`):

```
benutzername@rechnername:~$
ubuntu@ip-10-0-6-137:~$
```

---

## Grundlegende Verwendung von `echo`

1. **Einfachen Text ausgeben**

   ```bash
   echo "Hallo Welt"
   # Ausgabe: Hallo Welt
   ```
2. **Leere Zeile**

   ```bash
   echo
   # Ausgabe: (eine leere Zeile)
   ```

---

### Beispiele mit Optionen

```bash
# Ohne Zeilenumbruch
echo -n "Bitte eingeben: "

# Neue Zeile per Escape
⌥ Option + ⇧ Shift + 7

echo -e "Zeile1\nZeile2"
# Ausgabe:
# Zeile1
# Zeile2
```

---

## Variablen und Substitution

1. **Variable setzen**

   ```bash
   name="Max"
   ```
2. **Variable ausgeben**

   ```bash
   echo "Hallo, $name!"
   # Ausgabe: Hallo, Max!
   ```
3. **Kommando‑Substitution**

   ```bash
   echo "Heutiges Datum: $(date +%Y-%m-%d)"
   ```
4. **Rechenoperationen**

   ```bash
   echo "5 + 7 = $((5 + 7))"
   # Ausgabe: 5 + 7 = 12
   ```

---

## Einsteigeraufgaben

Bearbeite die folgenden Mini‑Aufgaben direkt in deinem Terminal. Jede Aufgabe lässt sich mit **einem einzigen Shell‑Befehl** lösen.

| Nr. | Aufgabe                                                                                    |
| --- | ------------------------------------------------------------------------------------------ |
| 1   | **Hallo Welt** – Gib genau den Text `Hallo Welt` aus.                                      |
| 2   | **Leerzeile** – Erzeuge eine leere Zeile.                                                  |
| 3   | **Variable verwenden** – a) Setze `name` auf deinen Vornamen. b) Gib `Hallo, <Name>!` aus. |
| 4   | **Datum anzeigen** – Zeige das heutige Datum im Format `JJJJ-MM-TT` an.                    |
| 5   | **Rechnen** – Berechne `5 + 7` und gib `5 + 7 = 12` aus.                                   |

---
