# Home-Lab-TIA-Portal-S7-1200

# Ampelprojekt mit S7-1200

# 🚦 Ampelsteuerung – Siemens TIA Portal | S7-1200 (1214C AC/DC/Rly)

Dieses Projekt simuliert eine vollständige Ampelsteuerung mithilfe einer Siemens S7-1200 SPS im TIA Portal.  
Die Steuerung ist modular aufgebaut und wurde auf echter Hardware (CPU 1214C AC/DC/Rly) in meinem Home Lab programmiert und getestet.  
Das Projekt zeigt den Einsatz von TON- und TP-Timern zur Steuerung der Lichtphasen sowie des gelben Blinksignals ohne Verwendung von `SM0.5`.

---

## 💡 Hauptfunktionen

- Steuerung von Rot-, Gelb- und Grünlicht mit festen Zeitintervallen
- Gelbes Blinklicht über TP-Timer (kein SM0.5 benötigt)
- Getestet auf echter Hardware (S7-1200 CPU 1214C AC/DC/Rly)
- Strukturierter Aufbau in mehreren Netzwerken (LAD/KOP)
- Ideal für Schulungs- und Präsentationszwecke

---

## ⚙️ Projektübersicht

| Komponente              | Beschreibung                         |
|-------------------------|--------------------------------------|
| SPS                     | Siemens S7-1200, CPU 1214C AC/DC/Rly |
| Programmiersoftware     | TIA Portal V16 oder höher            |
| Sprache                 | KOP (LAD – Ladder Diagram)           |
| Blinklogik              | TP-Timer (Impulsgenerator)           |
| Simulation              | PLCSIM möglich, getestet mit echter Hardware |

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

1. **Rotphase** (z. B. 5 Sekunden)
2. **Gelb blinkend** (TP-Timer, 0.5s Takt)
3. **Grünphase** (z. B. 5 Sekunden)
4. Wiederholung

---

## 🧠 Aufbau des Programms

- **Netzwerk 1** – Initialisierung / Reset aller Ausgänge
- **Netzwerk 2** – Rotphase über TON-Timer
- **Netzwerk 3** – Gelbes Blinklicht über TP-Timer
- **Netzwerk 4** – Grünphase über TON-Timer
- **Netzwerk 5** – Ablaufsteuerung / Schrittlogik

---

## 📸 Screenshots (optional einfügen)

Lege die Screenshots im Ordner `Screenshots/` ab und füge sie so ein:

```markdown
![Rotphase](./Screenshots/Netzwerk2_Rot.png)  
![Gelbphase](./Screenshots/Netzwerk3_Gelb.png)  
![Grünphase](./Screenshots/Netzwerk4_Gruen.png)
📁 Projektstruktur
swift
Copy
Edit
📁 Traffic_Light_Controller_S7-1200
├── README.md
├── /Screenshots/          ← Bilder der Netzwerke
│   ├── Netzwerk2_Rot.png
│   ├── Netzwerk3_Gelb.png
│   └── Netzwerk4_Gruen.png
├── /TIA_Project/          ← TIA-Projektdatei
│   └── TrafficLight.zap16
🛠️ Verwendete Technologien
Siemens TIA Portal v16+

Siemens S7-1200 (1214C AC/DC/Rly)

KOP (LAD)

TON- & TP-Timer

Digitale Ausgänge Q0.0 – Q0.2

▶️ Projekt ausführen
.zap16-Datei im TIA Portal öffnen

SPS verbinden (oder PLCSIM verwenden)

Projekt aufspielen und beobachten:

Q0.0 → Rotlicht

Q0.1 → Gelblicht (Blinken)

Q0.2 → Grünlicht

👤 Autor
Muhamed Elhosiny
Automatisierungsingenieur mit Fokus auf SPS, SCADA und Steuerungstechnik

📧 muhamad.elhosiny@gmail.com
🔗 LinkedIn-Profil
🔗 GitHub-Profil

📜 Lizenz
Dieses Projekt ist für Lern- und Demonstrationszwecke frei verfügbar.
Gerne mit Verweis auf den Autor bei Wiederverwendung 🙌

 
 





