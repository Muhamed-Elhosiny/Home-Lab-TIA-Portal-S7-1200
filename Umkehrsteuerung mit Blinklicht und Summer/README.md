# Projekt: Automatisierung einer Umkehrsteuerung mit Blinklicht und Summer

In diesem Projekt wird ein Motor mithilfe einer Umkehrsteuerung automatisch gesteuert.  
Bei Tastendruck in eine Richtung startet der Motor manuell. Sobald ein Motor läuft,  
aktiviert sich ein automatischer Blinkmechanismus mit zwei Lampen, die sich im Sekundentakt abwechseln,  
sowie ein Summer, der nur für eine Sekunde ertönt.   
Die gesamte Steuerung läuft solange, bis der Motor gestoppt wird.

---

## Ein-/Ausgangstabelle

| Nr. | Typ     | Adresse | Bezeichnung | Verwendung              |
|-----|---------|---------|-------------|--------------------------|
| 1   | Eingang | I0.1    | Start       | Start Rechtslauf         |
| 2   | Eingang | I0.2    | Stop        | Stop Rechtslauf          |
| 3   | Eingang | I0.3    | Start       | Start Linkslauf          |
| 4   | Eingang | I0.4    | Stop        | Stop Linkslauf           |
| 5   | Ausgang | Q0.1    | Motor-R     | Motor Rechtslauf         |
| 6   | Ausgang | Q0.2    | Motor-L     | Motor Linkslauf          |
| 7   | Ausgang | Q0.7    | Horn        | Summer (akustisches Signal) |
| 8   | Ausgang | Q1.0    | Lamp1       | Blinklicht 1             |
| 9   | Ausgang | Q1.1    | Lamp2       | Blinklicht 2             |

---
# Screenashots

![image](https://github.com/user-attachments/assets/c3d8a140-da28-4dea-8abc-8c056e07da94)
![image](https://github.com/user-attachments/assets/c507c934-ae09-45b9-b8ac-8766df51d45e)
![image](https://github.com/user-attachments/assets/2cda9092-00ef-4c53-a1a6-ca7b9a9ab653)
![image](https://github.com/user-attachments/assets/13a03d7c-c998-4405-b33e-06a44423cb6a)
![image](https://github.com/user-attachments/assets/c3201206-a9c8-456f-82be-26867746a921)
![image](https://github.com/user-attachments/assets/26ac892a-9a52-4f87-b41b-e5fb1d7ad401)
![image](https://github.com/user-attachments/assets/99a68735-9d11-406e-8c33-7e353c1723ca)

![image](https://github.com/user-attachments/assets/2ec0839b-dbef-407f-ba52-c7395a763233)



## Hinweise

- Die Steuerung verwendet **Set/Reset-Bausteine** sowie das Zeitglied **TONR**,  
  da beide Bausteine ihren Zustand auch bei Stromausfall behalten.
- Nach Wiedereinschalten setzt die Steuerung automatisch dort fort, wo sie aufgehört hat.
- Das Blinklicht schaltet automatisch zwischen zwei Lampen im Sekundentakt.
- Der Summer (`Horn`) gibt bei Start ein kurzes akustisches Signal (1 Sekunde) ab.

---

**Getestet im Home Lab mit Siemens S7-1200 (1214C AC/DC/Rly) und TIA Portal.**

Projekt unter aktiver Entwicklung – Feedback und Anregungen willkommen!

