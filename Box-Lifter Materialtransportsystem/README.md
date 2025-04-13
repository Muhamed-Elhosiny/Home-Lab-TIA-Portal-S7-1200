# Projektname: Box-Lifter Materialtransportsystem

 ![image](https://github.com/user-attachments/assets/00ff6373-0401-4c8e-92f3-6a2d212011a1)


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

