# Projektname: Verkettete Motorsteuerung mit Zeitverzögerung

## Projektidee

Dieses Projekt demonstriert die sequentielle Steuerung von drei Motoren, die nacheinander mit festgelegter Zeitverzögerung aktiviert werden. Die Steuerung erfolgt über eine Start-/Stop-Logik in Kombination mit Timern (TON).

Ziel des Projekts ist es, das Konzept der Ablaufsteuerung mit Hilfe von SPS-Programmierung zu verdeutlichen.

---

## 🔁 Funktionsweise

1. Beim Drücken der Starttaste (`I0.1`) wird der erste Motor (`Q0.1`) aktiviert.
2. Nach einer kurzen Verzögerung wird der zweite Motor (`Q0.2`) eingeschaltet.
3. Anschließend wird nach weiterer Verzögerung der dritte Motor (`Q0.3`) aktiviert.
4. Über den Stopptaster (`I0.0`) kann der Prozess jederzeit abgebrochen werden.

---

## Variablentabelle

![Variablentabelle](https://github.com/user-attachments/assets/7d084790-48a0-4e9d-b0d6-9467879d6f61)

---

## 🛠️ SPS-Programm (TIA Portal – LAD)

![LAD-Programm](https://github.com/user-attachments/assets/8d0a4556-fa7b-4e4f-8581-059db1341213)

---

## Status

Vollständig getestet in einem Home Lab mit Siemens S7-1200  
TIA Portal Projektdateien im Repository enthalten  
Projekt ist Teil einer Serie von praktischen SPS-Beispielen


#Projektname: Verkettete Motorsteuerung mit Zeitverzögerung

## Projektidee:

Dieses Projekt zeigt die Steuerung von drei Motoren, die nacheinander mit Zeitverzögerung aktiviert werden. Die Steuerung erfolgt über eine Start-/Stop-Logik und Timer.

Variablen:

![image](https://github.com/user-attachments/assets/7d084790-48a0-4e9d-b0d6-9467879d6f61)

Programm
![image](https://github.com/user-attachments/assets/8d0a4556-fa7b-4e4f-8581-059db1341213)
