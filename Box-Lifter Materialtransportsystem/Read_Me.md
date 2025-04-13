Box-Lifter Materialtransportsystem
Projektbeschreibung / Idee
Dieses Projekt simuliert ein materialtransportierendes System („Box-Lifter“) in Siemens TIA Portal mit einer S7‑1200 SPS. Die Anlage transportiert automatisch Boxen auf einem Förderband (Förderer 1) und übergibt sie mittels eines Schiebers auf einen zweiten Förderer (Förderer 2). Ziel der Steuerung ist es, den Materialfluss mit Hilfe von Sensoren und Aktoren zu automatisieren und einen kontinuierlichen Zyklus zu ermöglichen. Das Projekt dient als Lernbeispiel für die SPS-Programmierung eines sequentiellen Ablaufs mit Zeitverzögerungen und Ereignissteuerung.
Ablaufbeschreibung
Der Ablauf der Steuerung lässt sich wie folgt zusammenfassen:
Start: Wenn der Starttaster betätigt wird, läuft die Förderkette an und befördert eine Box auf Förderer 1.
Box erkannt: Sobald eine Box den Sensor am Förderer 1 passiert, wird die Förderkette gestoppt.
Verzögerung im Ladebereich: Nachdem die Box im Ladebereich zum Stillstand gekommen ist, wartet die Steuerung 1 Sekunde.
Weitertransport: Die Förderkette startet danach erneut und bewegt die Box weiter in Richtung Entladeposition.
Entladeposition erreicht: Wenn die Box den Entladesensor am Ende von Förderer 1 erreicht, stoppt die Förderkette erneut.
Box ausschieben: Nach einer Wartezeit von 2 Sekunden wird der Schieber aktiviert. Der Schieber fährt aus und schiebt die Box seitlich auf Förderer 2 hinüber.
Schieber zurück: Sobald der Schieber vollständig zurückgefahren ist, erkennt ein Reed-Schalter die Grundstellung des Schiebers.
Zyklusfortsetzung: 1 Sekunde nachdem der Reed-Schalter ausgelöst hat, startet die Förderkette erneut, und der nächste Zyklus beginnt (sofern weitere Boxen vorhanden sind).
Stopp: Der Zyklus wiederholt sich kontinuierlich, bis der Stopptaster betätigt wird. Beim Drücken des Stopptasters hält die Anlage an und die Förderkette stoppt dauerhaft.
Verwendete Variablen
Symbolname (DE)	Adresse	Typ	Beschreibung
Starttaster	E0.0	BOOL	Starttaste (Ein-Taster) – startet den Anlagenzyklus
Stopptaster	E0.1	BOOL	Stopptaste (Aus-Taster) – hält den Anlagenzyklus an
Sensor Förderer 1	E0.2	BOOL	Sensor am Förderer 1 – erkennt eine ankommende Box
Entladesensor	E0.3	BOOL	Sensor an der Entladeposition (Ende Förderer 1) – erkennt eine Box
Reed-Schalter Schieber	E0.4	BOOL	Reed-Kontaktschalter – erkennt den Schieber in Grundstellung
Motor Förderkette	A0.0	BOOL	Antrieb der Förderkette (Förderer 1 Ein/Aus)
Schieber (Auswerfer)	A0.1	BOOL	Antrieb des Schiebers – stößt die Box auf Förderer 2 aus
Betriebsbit	M0.0	BOOL	Merker für Automatikbetrieb – wird durch Start gesetzt und durch Stop zurückgesetzt
Status
Das Projekt ist erfolgreich implementiert und wurde im Home Lab getestet. Die Steuerung läuft wie erwartet in der Simulation (PLCSIM) sowie auf einer realen S7‑1200 CPU. Der aktuelle Status des Projekts ist funktionsfähig.
