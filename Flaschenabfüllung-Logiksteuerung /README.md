# Füllstandssteuerung mit Ventil- und Linienkontrolle

Dieses Projekt simuliert eine industrielle Füllstandsregelung mit zwei Einlaufleitungen und einem Ventil zum Füllen eines Behälters. Der Ablauf wird mit Sensoren überwacht, um sicherzustellen, dass der Behälter nicht überläuft oder leerläuft.

## Ziel
Demonstration einer praxisnahen Automatisierungslösung für die Steuerung eines Füllsystems mit mehreren Sensoren und Ausgängen.

---
## Funktionsweise

Beim Drücken der **Starttaste I0.1** wird die **erste Produktionslinie Q0.1** und die **zweite Q0.2** aktiviert – beide bewegen sich in dieselbe Richtung.

Die erste Linie ist für Flaschen mit unterschiedlicher Größe zuständig. Die Unterscheidung erfolgt über die Sensoren:

- **I0.2** für kleine Flaschen  
- **I0.3** für große Flaschen  

Sobald eine große Flasche den **Sensor I0.4** erreicht, wird die erste Linie gestoppt.

Wenn sich die Flasche in der richtigen Füllposition befindet, öffnet sich das **Ventil Q0.3** automatisch für eine voreingestellte Zeit. Danach:

- Das Ventil schließt sich wieder
- Die erste Linie startet erneut
- Der nächste Zyklus beginnt

Die Füllzeit wird abhängig von der Flaschengröße über den Speicherwert **VW0** gesteuert – dieser wird durch die Sensoren bestimmt.

Die **zweite Produktionslinie Q0.2** bleibt aktiv, bis der **Stopptaster I0.0** gedrückt wird.  
Diese Linie dient der Steuerung, damit keine neue Flasche einläuft, bevor die erste vollständig befüllt ist.


## 🔌 Eingänge und Ausgänge

| Nr. | Typ     | Adresse | Beschreibung          |
|-----|----------|---------|------------------------|
| 1   | Eingang  | I0.0    | Stop                  |
| 2   | Eingang  | I0.1    | Start                 |
| 3   | Eingang  | I0.2    | Sensor High (max)     |
| 4   | Eingang  | I0.3    | Sensor Low (min)      |
| 5   | Eingang  | I0.4    | Sensor Position       |
| 6   | Ausgang  | Q0.1    | Linie 1               |
| 7   | Ausgang  | Q0.2    | Linie 2               |
| 8   | Ausgang  | Q0.3    | Ventil                |

![image](https://github.com/user-attachments/assets/343a491a-397d-408c-9928-b529b48d2d31)

---

## 🔄 Funktionsbeschreibung

1. **Startsequenz**: Durch das Drücken der Starttaste (I0.1) wird das System aktiviert. Sensoren prüfen den Füllstand, und die Linien Q0.1/Q0.2 starten automatisch je nach Pegelstand.
2. **Sensorüberwachung**: Wenn der Sensor I0.2 (High) aktiv ist, wird das Ventil Q0.3 geschlossen.
3. **Niedrigstand**: Bei niedrigem Wasserstand (I0.3) wird das Ventil Q0.3 geöffnet, um das Becken zu füllen.
4. **Sicherheitsabschaltung**: Die Stopptaste (I0.0) oder Sensorfehler stoppt das gesamte System.
5. **Zusätzliche Logik**: Die Linie Q0.1 startet über I0.1, Q0.2 über I0.4.

---
![image](https://github.com/user-attachments/assets/80a048d0-cee6-4440-b2ed-9e47bf0fd489)


## 🖥️ Programmlogik (TIA Portal)

> Das Projekt wurde im **TIA Portal** mit einem Siemens S7-1200 (1214C AC/DC/Rly) in **LAD (KOP)** programmiert.
 **Verwendete Bausteine**:
- Positive Flanke (`P`)
- TON / TONR-Timer
- SR-Set/Reset
- MOVE & Vergleichsoperatoren

---

## 🧩 Visualisierung

> Beispielhafte Darstellung des Behältersystems:

📷 `screenshots/01_system_structure.png`

📷 `screenshots/02_ladder_logic.png`

---

## 🔧 Hinweis

Einige Teile des Projekts befinden sich **noch in aktiver Entwicklung und Optimierung**. Die Funktionalität wird schrittweise getestet und erweitert.

---

## 👨‍💻 Autor

Muhamed Elhosiny  
Automatisierung & SPS-Entwicklung  
[GitHub-Profil ansehen](https://github.com/Muhamed-Elhosiny)


