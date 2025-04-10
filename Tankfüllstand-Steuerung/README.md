
# Tankfüllstand-Steuerung (Tank Level Control)

## Beschreibung

Dieses Projekt simuliert eine Steuerung für den Füllstand eines Tanks mit drei Pumpen. Die Steuerung erfolgt anhand von drei verschiedenen Füllstandssensoren und einem Not-Aus-Taster.

## Funktionsweise

- **Pumpe 1** (Q0.1) wird aktiviert, wenn der Füllstand unter I1.2 (Operation Level) fällt.
- **Pumpe 2** (Q0.2) wird aktiviert, wenn der Füllstand unter I1.3 (Low Level) fällt.
- Beide Pumpen bleiben aktiv, bis der Füllstand I1.1 (High Level) erreicht ist.
- **Pumpe 3** (Q0.3) dient als Notpumpe. Sie wird nur aktiviert, wenn der Füllstand unter I1.3 fällt und innerhalb einer halben Minute nicht ansteigt.

## Komponentenübersicht

![image](https://github.com/user-attachments/assets/ca2eab95-98af-433f-b46b-2c2bbedd47c1)

## Programm Mit Beschreibung

![image](https://github.com/user-attachments/assets/2c34c22e-a11a-448a-9814-68e78238a277)



 

