# Projektname: Box-Lifter Materialtransportsystem

 ![image](https://github.com/user-attachments/assets/00ff6373-0401-4c8e-92f3-6a2d212011a1)


## Projektidee

Dieses Projekt simuliert ein automatisiertes Materialfördersystem mit einem **Box-Lifter** mithilfe von **Siemens TIA Portal** und einer **S7-1200 SPS**. Ziel ist die Realisierung eines kontinuierlichen Materialflusses mit Hilfe von Sensorik und Aktorik zur praxisnahen Anwendung sequentieller Steuerungen mit Zeitverzögerungen.

---

## Funktionsbeschreibung

1. **Start**: Nach dem Drücken des Starttasters (`%I0.1`) läuft der Motor der Förderkette (`%Q0.1`) an.
2. **Box erkannt**: Der Sensor an Förderer 1 (`%I0.2`) erkennt die Box → Förderer stoppt.
3. **1s Verzögerung**: Zeitverzögerung nach Stopp (TON-Timer `T1`).
4. **Weitertransport**: Förderer wird erneut gestartet.
5. **Entladeposition**: Entladesensor (`%I0.4`) erkennt die Box → Förderer stoppt.
6. **Schieber aktiv**: Nach 2s Verzögerung wird der Schieber (`%Q0.3`) ausgelöst.
7. **Schieber zurück**: Reed-Schalter (`%I0.4`) erkennt die Grundstellung.
8. **1s Wartezeit**, dann startet der Zyklus erneut.
9. **Stop**: Über den Stopptaster (`%I0.0`) wird der gesamte Zyklus gestoppt.

![image](https://github.com/user-attachments/assets/4b86cbe9-6990-4acc-a959-4c0633a6cb78)

---

## SPS Variablentabelle (TIA Portal kompatibel)

 ![image](https://github.com/user-attachments/assets/95b24294-d503-4a8e-aa01-7ce6d7e5504f)

  
| `Timer_Startverzögerung`   | `T1`     | Timer   | 1s Verzögerung nach Box |
| `Timer_Schieber`           | `T2`     | Timer   | 2s Verzögerung für Schieber |
| `Timer_NächsterZyklus`     | `T3`     | Timer   | 1s Wartezeit vor Restart |

---
# Programm

![image](https://github.com/user-attachments/assets/ad19df91-2aa4-4223-913e-cdcd82b9d6f4)

## Projektstatus

- ✅ Vollständig getestet im **Home Lab** mit einer realen **S7‑1200 CPU**
- ✅ Lauffähig in **TIA Portal V17+**
- ✅ Funktioniert mit **PLCSIM** oder realem Aufbau
- 📁 Alle Projektdateien im Repository enthalten

