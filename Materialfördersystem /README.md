# Materialfördersystem – Automatisierungsprojekt

## Projektbeschreibung

Dieses Projekt beschreibt ein Materialfördersystem, das dazu dient, Materialien wie Körner, Pulver oder Granulat von Bodenniveau auf eine bestimmte Höhe zu transportieren. Der Fördermechanismus basiert auf einer Kette, die durch einen Elektromotor angetrieben wird, und einem Schwingförderer zur kontinuierlichen Beschickung eines Behälters.

![image](https://github.com/user-attachments/assets/330e1534-4edd-42ab-aa9a-7c0ad0503699)

## Funktionsbeschreibung

### 1. Startsequenz:
- Bei Betätigung des **Start-Tasters** (`start_PB`):
  - Der **Elektromotor** startet sofort → die **Förderkette** beginnt sich zu bewegen.
  - Nach einer **Verzögerung von 2 Sekunden** startet der **Schwingförderer**.

### 2. Förderprozess:
- Der **Schwingförderer** beschickt kontinuierlich einen Behälter mit Material.
- Der Behälter entlädt das Material in einen **Lagertank**.

### 3. Stoppsequenz:
- Wenn der **Füllstandssensor** (`level_sensor`) ein „Voll“-Signal erkennt:
  - Der **Schwingförderer** wird **sofort** gestoppt.
  - Der **Elektromotor (Förderkette)** wird **nach 2 Sekunden Verzögerung** abgeschaltet.

---

## Verwendete SPS-Komponenten

- **Siemens S7-1200 CPU**
- Programmiersprache: **LAD (Kontaktplan)** oder **FUP (Funktionsplan)**
- Bausteine: `OB1`, `FB1_Materialfoerderung`, `DB1_Timerdaten`
- Verwendete Timer: **TON (Ein-Verzögerung)**

---

## Symbolische Variablenbezeichnung

![image](https://github.com/user-attachments/assets/8f977d51-aa25-420b-adbc-859ad6a3cd30)

---

## Screenshots

![image](https://github.com/user-attachments/assets/1c856986-0707-4f01-adf3-8b9501414b5b)


---

## Projektdateien

- Die Projektdatei `materialfoerderung.ap17` ist mit **TIA Portal V17** erstellt.
- Alle Screenshots, Tag-Tabellen und Abläufe sind im Ordner **DOKUMENTATION/** verfügbar.

---

## Ziel

Demonstration eines einfachen aber praxisnahen Automatisierungsablaufs mit Fokus auf **zeitverzögerten Steuerungen**, Sensorik und **symmetrischer Abschaltlogik**.

---

## Kontakt

> Erstellt im Rahmen meines Home-Lab-Projekts.  
> Bei Fragen oder Feedback: www.linkedin.com/in/elhosiny


