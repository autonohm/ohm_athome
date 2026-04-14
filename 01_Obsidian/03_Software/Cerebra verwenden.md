---
tags:
  - Motoren
Autor: "[[Jonathan Grunewald]]"
---
﻿# Anleitung Cerebra
## Vorbereitung
- prüfen, ob Raspberry Pi läuft und Netzteil für Motoren angeschlossen ist
- Prüfen, ob grüne LED am Relais leuchtet, sonst Relais schließen
- Relais schließen:
  - Auf dem RPi Programmierung -> BrickViewer offnen
  - "Connect" klicken
  - Reiter Reklais öffnen
  - "Switch on" klicken
  - Prüfen, ob Relais geschlossen ist (grüne LED)
- Browser auf RPI öffnen und "localhost" aufrufen
  - Unter Joint Control -> Hardware ID prüfen, ob Bricklets mit /dev/ttyMotorX (X = laufende Nummer) bezeichnet ist
  - Wenn nein: Neustart
  - Motor kann unter Reiter Joint Control ausgewählt und mit Schieberegler angesteuert werden
- **Achtung: Motoren nur vorsichtig bewegen da keine Maximalbewegungen definiert sind. Beschädigungen am Pib durch zu weite Gelenkbewegung möglich**
- **Bei "Festklemmen" eines Motors droht dessen Überhitzung: Sofort Stromversorgung trennen!**

## Motorrichtung invertieren:
Bewegen sich die Finger in die andere Richtung als erwartet kann die Richtung invertiert werden:
* Cerebra: Joint Control -> Zahnradsymbol des Motors klicken
* “Extended Values” Klicken
* Checkbox “Invert Motor” aktivieren bzw. deaktivieren

## Pose  definieren und ansteuern
- Motoren einzeln unter Reiter Joint Control in Cerebra ansteuern um Pose einzustellen
- Pose Speichern: Reiter Pose -> Pose speichern. Name eingeben und bestätigen
- Pose ansteuern: Reiter Pose -> Grüner Pfeil bei Zielpose betätigen

## Kamera ansteuern
* Reiter Camera; selbsterklärend

## Voice Assistant
* Z.Zt. Nicht funbktionstauglich -> Token von Insento anfordern

## Program
* Grafische Programmieroberfläche mit Blöcken unter Reiter Program
* Noch keine wesentlichen Erfahrungen gesammelt; Nutzen zweifelhaft

## Troubleshoot
- Wenn Motoren nicht reagieren: Systemneustart (teilweise auch mehrfach inkl. vollständige Trennung der Stromversorgung) notwendig. Ansonsten siehe Vorbereitung
- Wenn einzelner Motor nicht reagiert: Versuchen über Debug-Tool anzusteuern (siehe Motor kalibrieren). Wenn möglich: Verkabelung prüfen. Wenn nicht: Motor tauschen.