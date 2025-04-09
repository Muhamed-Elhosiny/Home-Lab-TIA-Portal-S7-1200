# Projekt: Stern/Delta Steuerung mit zwei Geschwindigkeiten

Dieses Projekt zeigt eine einfache **SPS-Steuerung** für einen Motor mit zwei Betriebsarten: **niedrige Geschwindigkeit (Low Speed)** und **hohe Geschwindigkeit (High Speed)**. Der Wechsel erfolgt automatisch über eine Stern/Delta-Schaltung mit Zeitverzögerung. Die Steuerung wurde in meinem **Home Lab mit einem Siemens S7-1200 (1214C AC/DC/Rly)** entwickelt und getestet.

---

## Belegungstabelle (Inputs & Outputs)

| Nr. | Typ     | Adresse | Name        | Beschreibung          |
|-----|---------|---------|-------------|------------------------|
| 1   | Eingang | I0.1    | Start       | Starttaster (n.o.)     |
| 2   | Eingang | I0.0    | Stop        | Stopptaster (n.c.)     |
| 3   | Ausgang | Q0.1    | Low_Speed   | Motor - niedrige Drehzahl |
| 4   | Ausgang | Q0.2    | High_Speed  | Motor - hohe Drehzahl  |
| 5   | Ausgang | Q0.3    | Stern       | Stern-Kontaktor        |

---

## Screenshots Mit Funktionsbeschreibung
 
![image](https://github.com/user-attachments/assets/12b1d75d-fc2f-4170-81a7-4b9f49ec64d5)





 
---

##  Testumgebung

Dieses Projekt wurde erfolgreich auf meinem **Siemens S7-1200 (1214C AC/DC/Rly)** im Home Lab getestet. Alle Netzwerke sind kommentiert und strukturiert dokumentiert.

---

**Status:** In Betrieb  
**Dateien:** `.zap`, Screenshots und Schaltpläne im Projektordner  
**Werkzeuge:** TIA Portal, S7-1200, WinCC Basic
  
