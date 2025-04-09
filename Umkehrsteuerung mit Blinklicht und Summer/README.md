# Projekt: Automatisierung einer Umkehrsteuerung mit Blinklicht und Summer

In diesem Projekt wird ein Motor mithilfe einer Umkehrsteuerung automatisch gesteuert.  
Bei Tastendruck in eine Richtung startet der Motor manuell. Sobald ein Motor läuft,  
aktiviert sich ein automatischer Blinkmechanismus mit zwei Lampen, die sich im Sekundentakt abwechseln,  
sowie ein Summer, der nur für eine Sekunde ertönt.  
Die gesamte Steuerung läuft solange, bis der Motor gestoppt wird.

---

## 📊 Ein-/Ausgangstabelle

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

## Hinweise

- Die Steuerung verwendet **Set/Reset-Bausteine** sowie das Zeitglied **TONR**,  
  da beide Bausteine ihren Zustand auch bei Stromausfall behalten.
- Nach Wiedereinschalten setzt die Steuerung automatisch dort fort, wo sie aufgehört hat.
- Das Blinklicht schaltet automatisch zwischen zwei Lampen im Sekundentakt.
- Der Summer (`Horn`) gibt bei Start ein kurzes akustisches Signal (1 Sekunde) ab.

---

**Getestet im Home Lab mit Siemens S7-1200 (1214C AC/DC/Rly) und TIA Portal.**

Projekt unter aktiver Entwicklung – Feedback und Anregungen willkommen!

