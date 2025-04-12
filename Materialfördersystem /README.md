# ⚙️ Materialfördersystem – Automatisierungsprojekt

## Projektbeschreibung

Dieses Projekt beschreibt ein Materialfördersystem, das dazu dient, Materialien wie Körner, Pulver oder Granulat von Bodenniveau auf eine bestimmte Höhe zu transportieren. Der Fördermechanismus basiert auf einer Kette, die durch einen Elektromotor angetrieben wird, und einem Schwingförderer zur kontinuierlichen Beschickung eines Behälters.

---

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

| Symbolischer Name      | Beschreibung                     | Typ     |
|------------------------|----------------------------------|---------|
| `start_PB`             | Start-Taster                     | Bool    |
| `motor_kette`          | Motor für Förderkette            | Bool    |
| `schwingfoerderer`     | Vibrationsförderer               | Bool    |
| `level_sensor`         | Füllstandssensor                 | Bool    |
| `timer_start_foerderer`| Timer für Fördererstart          | TON     |
| `timer_stop_kette`     | Timer für Ketten-Stoppverzögerung| TON     |

---

## Screenshots

| Startsequenz            | Stoppsequenz            |
|-------------------------|-------------------------|
| ![start](BILDER/startsequenz.png) | ![stopp](BILDER/stoppsequenz.png) |

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
> Bei Fragen oder Feedback: [Dein Name oder LinkedIn Profil]


