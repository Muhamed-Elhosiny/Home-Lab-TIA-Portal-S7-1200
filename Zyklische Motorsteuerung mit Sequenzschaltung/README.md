# Projektname: Zyklische Motorsteuerung mit Sequenzschaltung

## Projektbeschreibung:

Dieses Projekt simuliert die sequentielle Steuerung von vier Motoren (dargestellt durch Pilotlampen). Die Steuerung erfolgt über einen Start-Taster. Die Motoren starten nacheinander (Motor1 → Motor2 → Motor3 → Motor4), wobei jeder Motor für 5 Sekunden läuft. Nach Abschluss der Sequenz beginnt der Zyklus von vorne. Der Stopp-Taster unterbricht den Zyklus jederzeit.

## Komponenten:

- 🟢 Start-Taster (`%I0.0`)
- 🔴 Stopp-Taster (`%I0.1`)
- 🟡 Motor1 (Pilotlampe) → `%Q0.0`
- 🟡 Motor2 (Pilotlampe) → `%Q0.1`
- 🟡 Motor3 (Pilotlampe) → `%Q0.2`
- 🟡 Motor4 (Pilotlampe) → `%Q0.3`
- ⏲️ Timer für jede Motorlaufzeit: 5 Sekunden (z. B. `T1`, `T2`, `T3`, `T4`)

---

## SPS-Tags (PLC Tags):

| Symbolname       | Adresse | Typ   | Beschreibung                         |
|------------------|---------|-------|--------------------------------------|
| Start_Taster     | %I0.0   | Input | Startet den Zyklus                   |
| Stop_Taster      | %I0.1   | Input | Stoppt den Zyklus                    |
| Motor1           | %Q0.0   | Output| Lampe für Motor1                     |
| Motor2           | %Q0.1   | Output| Lampe für Motor2                     |
| Motor3           | %Q0.2   | Output| Lampe für Motor3                     |
| Motor4           | %Q0.3   | Output| Lampe für Motor4                     |
| Timer_M1         | T1      | Timer | 5 Sek. Laufzeit Motor1               |
| Timer_M2         | T2      | Timer | 5 Sek. Laufzeit Motor2               |
| Timer_M3         | T3      | Timer | 5 Sek. Laufzeit Motor3               |
| Timer_M4         | T4      | Timer | 5 Sek. Laufzeit Motor4               |

---

## Steuerlogik (Ablaufbeschreibung):

1. Nach Druck auf den **Start-Taster** beginnt Motor1 zu laufen.
2. Nach **5 Sekunden** (Timer T1) stoppt Motor1, Motor2 startet.
3. Nach weiteren **5 Sekunden** (Timer T2) stoppt Motor2, Motor3 startet.
4. Nach weiteren **5 Sekunden** (Timer T3) stoppt Motor3, Motor4 startet.
5. Nach weiteren **5 Sekunden** (Timer T4) stoppt Motor4, der Zyklus beginnt erneut bei Motor1.
6. Wenn der **Stop-Taster** gedrückt wird, stoppt der gesamte Ablauf.

---

## Screenshots / Programm (TIA LAD):

*(Hier kannst du Screenshots deiner Netzwerke einfügen, z. B. Network 1 – Startbedingung, Network 2 – Motor1 aktiv, usw.)*

---

## Hinweise:

- Kann auch mit **SR-Flipflops** oder **Zähler** aufgebaut werden.
- Wenn du Factory IO oder eine echte SPS verwendest, kannst du die Lampen als Motoren visualisieren.

---

If you’d like, I can also help generate the **TIA ladder logic** or **export a PLC tag table `.xlsx`** for this project. Want that?
