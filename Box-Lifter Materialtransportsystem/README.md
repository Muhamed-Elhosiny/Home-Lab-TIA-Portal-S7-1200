# Projektname: Box-Lifter Materialtransportsystem

## Projektbeschreibung / Idee

Dieses Projekt simuliert ein materialtransportierendes System („Box-Lifter“) in **Siemens TIA Portal** mit einer **S7‑1200 SPS**.  
Die Anlage transportiert automatisch Boxen auf einem Förderband (Förderer 1) und übergibt sie mittels eines Schiebers auf einen zweiten Förderer (Förderer 2).  

Ziel der Steuerung ist es, den Materialfluss mit Hilfe von Sensoren und Aktoren zu automatisieren und einen kontinuierlichen Zyklus zu ermöglichen.  
Das Projekt dient als Lernbeispiel für die **SPS-Programmierung eines sequentiellen Ablaufs** mit **Zeitverzögerungen** und **Ereignissteuerung**.

---

## Ablaufbeschreibung

1. **Start**  
   Wenn der Starttaster betätigt wird, läuft die Förderkette an und befördert eine Box auf Förderer 1.

2. **Box erkannt**  
   Sobald eine Box den Sensor am Förderer 1 passiert, wird die Förderkette gestoppt.

3. **Verzögerung im Ladebereich**  
   Nachdem die Box im Ladebereich zum Stillstand gekommen ist, wartet die Steuerung 1 Sekunde.

4. **Weitertransport**  
   Die Förderkette startet danach erneut und bewegt die Box weiter in Richtung Entladeposition.

5. **Entladeposition erreicht**  
   Wenn die Box den Entladesensor am Ende von Förderer 1 erreicht, stoppt die Förderkette erneut.

6. **Box ausschieben**  
   Nach einer Wartezeit von 2 Sekunden wird der Schieber aktiviert.  
   Der Schieber fährt aus und schiebt die Box seitlich auf Förderer 2 hinüber.

7. **Schieber zurück**  
   Sobald der Schieber vollständig zurückgefahren ist, erkennt ein Reed-Schalter die Grundstellung des Schiebers.

8. **Zyklusfortsetzung**  
   1 Sekunde nachdem der Reed-Schalter ausgelöst hat, startet die Förderkette erneut,  
   und der nächste Zyklus beginnt (sofern weitere Boxen vorhanden sind).

9. **Stopp**  
   Der Zyklus wiederholt sich kontinuierlich, bis der Stopptaster betätigt wird.  
   Beim Drücken des Stopptasters hält die Anlage an und die Förderkette stoppt dauerhaft.

---

## Verwendete Variablen

| Symbolname (DE)             | Adresse | Typ   | Beschreibung                                                      |
|----------------------------|---------|-------|-------------------------------------------------------------------|
| Starttaster                | E0.0    | BOOL  | Starttaste (Ein-Taster) – startet den Anlagenzyklus              |
| Stopptaster                | E0.1    | BOOL  | Stopptaste (Aus-Taster) – hält den Anlagenzyklus an              |
| Sensor Förderer 1          | E0.2    | BOOL  | Sensor am Förderer 1 – erkennt eine ankommende Box               |
| Entladesensor              | E0.3    | BOOL  | Sensor an der Entladeposition (Ende Förderer 1) – erkennt eine Box |
| Reed-Schalter Schieber     | E0.4    | BOOL  | Reed-Kontaktschalter – erkennt den Schieber in Grundstellung     |
| Motor Förderkette          | A0.0    | BOOL  | Antrieb der Förderkette (Förderer 1 Ein/Aus)                      |
| Schieber (Auswerfer)       | A0.1    | BOOL  | Antrieb des Schiebers – stößt die Box auf Förderer 2 aus         |
| Betriebsbit                | M0.0    | BOOL  | Merker für Automatikbetrieb – wird durch Start gesetzt und durch Stop zurückgesetzt |

---

## Status

✅ Das Projekt ist erfolgreich implementiert und wurde im Home Lab getestet.  
Die Steuerung läuft wie erwartet in der **Simulation (PLCSIM)** sowie auf einer **realen S7‑1200 CPU**.  
Der aktuelle Status des Projekts ist **funktionsfähig**.


---
# Projektname: Box-Lifter Materialtransportsystem

## Projektidee

Dieses Projekt simuliert ein automatisiertes Materialfördersystem mit einem **Box-Lifter** mithilfe von **Siemens TIA Portal** und einer **S7-1200 SPS**. Ziel ist die Realisierung eines kontinuierlichen Materialflusses mit Hilfe von Sensorik und Aktorik zur praxisnahen Anwendung sequentieller Steuerungen mit Zeitverzögerungen.

---

## Funktionsbeschreibung

1. **Start**: Nach dem Drücken des Starttasters (`%I0.0`) läuft der Motor der Förderkette (`%Q0.0`) an.
2. **Box erkannt**: Der Sensor an Förderer 1 (`%I0.2`) erkennt die Box → Förderer stoppt.
3. **1s Verzögerung**: Zeitverzögerung nach Stopp (TON-Timer `T1`).
4. **Weitertransport**: Förderer wird erneut gestartet.
5. **Entladeposition**: Entladesensor (`%I0.3`) erkennt die Box → Förderer stoppt.
6. **Schieber aktiv**: Nach 2s Verzögerung wird der Schieber (`%Q0.1`) ausgelöst.
7. **Schieber zurück**: Reed-Schalter (`%I0.4`) erkennt die Grundstellung.
8. **1s Wartezeit**, dann startet der Zyklus erneut.
9. **Stop**: Über den Stopptaster (`%I0.1`) wird der gesamte Zyklus gestoppt.

---

## SPS Variablentabelle (TIA Portal kompatibel)

| Symbolname (DE)            | Adresse  | Typ     | Beschreibung |
|----------------------------|----------|----------|--------------|
| `Start_Taster`             | `%I0.0`  | Input   | Startet den Prozess |
| `Stopp_Taster`             | `%I0.1`  | Input   | Hält den Prozess an |
| `Sensor_Förderer1`         | `%I0.2`  | Input   | Box am Förderer 1 erkannt |
| `Sensor_Entladeposition`   | `%I0.3`  | Input   | Box am Ende Förderer 1 |
| `Reed_Schieber`            | `%I0.4`  | Input   | Schieber in Grundstellung |
| `Motor_Förderkette`        | `%Q0.0`  | Output  | Förderbandmotor Ein/Aus |
| `Schieber_Auswerfer`       | `%Q0.1`  | Output  | Schieber betätigen |
| `Betriebsmodus`            | `%M0.0`  | Merker  | Aktiver Zyklusstatus |
| `Timer_Startverzögerung`   | `T1`     | Timer   | 1s Verzögerung nach Box |
| `Timer_Schieber`           | `T2`     | Timer   | 2s Verzögerung für Schieber |
| `Timer_NächsterZyklus`     | `T3`     | Timer   | 1s Wartezeit vor Restart |

---

## Projektstatus

- ✅ Vollständig getestet im **Home Lab** mit einer realen **S7‑1200 CPU**
- ✅ Lauffähig in **TIA Portal V17+**
- ✅ Funktioniert mit **PLCSIM** oder realem Aufbau
- 📁 Alle Projektdateien im Repository enthalten

