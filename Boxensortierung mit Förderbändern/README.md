# Projektname: Automatische Boxensortierung mit Förderbändern (S7-1200)

## Projektidee:

Dieses Projekt simuliert eine automatische Sortieranlage für Boxen, wie in Abbildung 1 dargestellt. Sie besteht aus einem Hauptförderband, von dem die Boxen geladen werden, sowie zwei Entladeförderbändern, die die Boxen in unterschiedliche Richtungen transportieren.

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

## Screenshots:



## Hinweis:
Dieses Projekt befindet sich aktuell in der Entwicklung und wird schrittweise getestet und dokumentiert.



