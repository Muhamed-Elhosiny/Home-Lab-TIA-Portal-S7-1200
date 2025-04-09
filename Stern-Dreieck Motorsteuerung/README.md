# Stern-Dreieck-Schaltung – SPS-Projekt (TIA Portal)

## Projektbeschreibung

Dieses Projekt zeigt die klassische Stern-Dreieck-Ansteuerung zur Reduzierung des Anlaufstroms bei Drehstrommotoren. Die Logik wird über eine Siemens S7-1200 SPS realisiert und im TIA Portal programmiert. Der Übergang von Stern zu Dreieck erfolgt automatisch nach einer Zeitverzögerung.

---

## Ein-/Ausgangsbelegung

| Nr. | Typ            | Adresse | Symbol | Beschreibung        |
|-----|----------------|---------|--------|----------------------|
| 1   | Eingang (n.o.) | I0.1    | Start  | Starttaste           |
| 2   | Eingang (n.c.) | I0.0    | Stop   | Not-Aus / Stopptaste |
| 3   | Ausgang        | Q0.0    | Main   | Hauptschütz          |
| 4   | Ausgang        | Q0.1    | Star   | Sternschütz          |
| 5   | Ausgang        | Q0.2    | Delta  | Dreieckschütz        |

---

## Ablaufsteuerung (Logik)

1. **Start** aktiviert den Hauptschütz und den Sternschütz.
2. Nach einer voreingestellten Zeit (z. B. 5 Sekunden) wird der Sternschütz ausgeschaltet.
3. Anschließend wird mit einer kleinen Verzögerung der Dreieckschütz aktiviert.
4. **Stop** oder ein Fehler schaltet alle Ausgänge ab.

---

## Voraussetzungen

- Siemens S7-1200 SPS (getestet mit 1214C AC/DC/Rly)
- TIA Portal (ab V15 empfohlen)
- Grundkenntnisse in der SPS-Programmierung (LAD oder FBD)

---

## Screenshots

![image](https://github.com/user-attachments/assets/9c691777-1eb0-45db-8c7c-e545c10982b6)

![image](https://github.com/user-attachments/assets/3457e707-9857-4687-a2ef-d35078d23adb)

![image](https://github.com/user-attachments/assets/2253fea1-597a-4e44-8aaa-618c3c569d8b)

![image](https://github.com/user-attachments/assets/3eb17729-9b27-4e41-b2f6-a50aa9a88d1a)



 


