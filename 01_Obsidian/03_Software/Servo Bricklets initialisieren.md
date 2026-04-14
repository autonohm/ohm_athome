---
tags:
  - Motoren
Autor: "[[Jonathan Grunewald]]"
---
# Servo Control Bricklets tauschen

Bei Austausch eines Servo Control Bricklets auf der Innenseite der oberen Klappe des pib nach folgendem Workflow initialisieren:
- Alle Verbindungen zwischen **allen** Servo Bricklets und Raspberry Pi trennen
- Pi starten
- Im Pi:
  - Konsole: sudo dmsg -w
- Neue Bricklet über USB mit Pi verbinden
- Im Pi:
  - Konsole: Neuer Eintrag mit Bezeichnung ttyACMX (X = laufende Nummer) erscheint zusammen mit Seriennummer des Bricklets. Diese notieren.
  - Konsole: Laufendes Skript mit Strg + C beenden
  - Konsole: sudo nano /etc/udev/rules.d/99-pib-motors.rules
  - Konsole: Seriennummer des ausgetauschten Bricklets mit neuer ersetzen
  - Konsole: Skript mit Strg + X beenden
  - Konsole: sudo udevadm --reload-rules
  - Konsole: sudo udevadm trigger
  - Reboot, mit Cerebra testen