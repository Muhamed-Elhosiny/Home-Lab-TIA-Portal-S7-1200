# Projektname: Automatische Boxensortierung mit Förderbändern (S7-1200)

## Projektidee:

Dieses Projekt simuliert eine automatische Sortieranlage für Boxen, wie in Abbildung 1 dargestellt. Sie besteht aus einem Hauptförderband, von dem die Boxen geladen werden, sowie zwei Entladeförderbändern, die die Boxen in unterschiedliche Richtungen transportieren.

![image](https://github.com/user-attachments/assets/981d0ec8-bfe6-4342-b456-afd01d2bcc38)

Es sind vier Reflexsensoren mit Reflektoren installiert, wie in der Abbildung gezeigt.

- Wenn ein Reflexsensor eine Box auf dem Hauptförderband erkennt, startet das Hauptförderband nach einer Verzögerung von 1 Sekunde.
- Sobald die Box Sensor 2 erreicht, stoppt das Hauptförderband.
- Das Transferförderband transportiert zuerst **5 Boxen zu Förderband 1**, danach die restlichen Boxen zu **Förderband 2**.
- Der Zähler wird zurückgesetzt, sobald der **Stopp-Taster** gedrückt wird.

## Verwendete Komponenten:

- S7-1200 SPS
- 4 Reflexsensoren
- Hauptförderband
- Transferförderband
- Förderband 1
- Förderband 2
- Zähler (Counter)
- Steuerpult mit Start-/Stopp-Taster und Reset-Funktion

## Funktionsübersicht:

1. **Sensorerkennung**: Erkennt die ankommende Box am Hauptförderband.
2. **Verzögerter Start**: Start des Hauptförderbands nach 1 Sekunde.
3. **Stopp an Sensor 2**: Hält das Hauptband, wenn eine Box Sensor 2 erreicht.
4. **Boxenverteilung**: 
   - 5 Boxen werden zu Förderband 1 sortiert.
   - Weitere Boxen zu Förderband 2.
5. **Zähler-Reset**: Manuell über Stopp-Taster.

## SPS-Tags (PLC Tags)

Hier sind alle verwendeten Ein- und Ausgänge, Speicher und Timer mit ihren Adressen und Bedeutungen dokumentiert.

![image](https://github.com/user-attachments/assets/cb0391c7-4ebb-4534-a691-0782c8535250)


---

## TIA-Programm (LAD / Steuerungslogik)

Dieses Abschnitt enthält Screenshots des Programms, das in TIA Portal erstellt wurde.

 ![image](https://github.com/user-attachments/assets/aa50e3a0-448d-4184-878e-d75747992717)



## Hinweis:
Dieses Projekt befindet sich aktuell in der Entwicklung und wird schrittweise getestet und dokumentiert.



