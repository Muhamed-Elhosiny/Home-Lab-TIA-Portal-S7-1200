
# Ampelprojekt mit S7-1200

# 🚦 Ampelsteuerung – Siemens TIA Portal | S7-1200 (1214C AC/DC/Rly)

Dieses Projekt simuliert eine vollständige Ampelsteuerung mithilfe einer Siemens S7-1200 SPS im TIA Portal.  
Die Steuerung ist modular aufgebaut und wurde auf echter Hardware (CPU 1214C AC/DC/Rly) in meinem Home Lab programmiert und getestet.  
Das Projekt zeigt den Einsatz von TON- und TP-Timern zur Steuerung der Lichtphasen.

---

## 💡 Hauptfunktionen

- Steuerung von Rot-, Gelb- und Grünlicht mit festen Zeitintervallen
- Gelbes Blinklicht über TP-Timer 
- Getestet auf echter Hardware (S7-1200 CPU 1214C AC/DC/Rly)
- Strukturierter Aufbau in mehreren Netzwerken (LAD/KOP)

## ⚙️ Projektübersicht

| Komponente              | Beschreibung                         |
|-------------------------|--------------------------------------|
| SPS                     | Siemens S7-1200, CPU 1214C AC/DC/Rly |
| Programmiersoftware     | TIA Portal V16 oder höher            |
| Sprache                 | KOP (LAD – Ladder Diagram)           |
| Blinklogik              | TP-Timer (Impulsgenerator)           |
| Simulation              | getestet mit echter Hardware 

---

## 🧪 Realitätsnahe Umsetzung

Das Projekt wurde in meinem **Home Lab mit realer SPS** umgesetzt:

- **Hardware:** Siemens S7-1200 CPU 1214C AC/DC/Rly
- **Logik:** Phasensteuerung über TON-Timer, Blinklicht über TP-Timer
- **Ausgänge:**  
  - Q0.0 → Rot  
  - Q0.1 → Gelb  
  - Q0.2 → Grün

---

## 🔄 Ablauf der Lichtphasen

1. **Rotphase** (5 Sekunden)
2. **Gelbphase** (3 Sekunden)
3. **Grünphase** (5 Sekunden)
4. **Wiederholung**

---

## Aufbau des Programms

![image](https://github.com/user-attachments/assets/3460542e-b9ba-4b37-a014-20192eff769b)

![image](https://github.com/user-attachments/assets/ebf7a12c-9b9e-4022-bac1-f47cc788c3f7)

![image](https://github.com/user-attachments/assets/65a223d5-5719-4c87-b92e-29f150f4724a)

![image](https://github.com/user-attachments/assets/c5354169-1936-4b36-b3c7-f67f853dfa13)






 
 





