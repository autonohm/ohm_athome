---
tags:
  - Motoren
Autor: "[[Jonathan Grunewald]]"
---
# Motoren Kalibrieren
﻿
## Vorbereitung
- Raspberry Pi starten
- Servo Adapter über Netzteil mit Strom versorgen, über USB mit Pie verbinden
  - Wichtig: Nur eine Daisy Chain am Bricklet und nur ein Bricklet mit Pi verbinden
  - Nicht mehrere Motoren mit gleicher ID in eine Daisy Chain verbinden (im Zweifel nur einen Motor wählen)
- Konsole: Debug-Programm über Konsolenbefehl: FT_SCServo_Debug_Qt starten (wenn nicht Verfügbar: Installation über https://github.com/Kotakku/FT_SCServo_Debug_Qt )
- Im Debug Tool:
  - COM-Port des Bricklets asuswählen und "Open", danach "Search" klicken
  - Motor in Liste links auswählen

## ID zuweisen
- Im Debug Tool:
  - Unter Reiter Programming -> Adress 5: ID auswählen
  - neue ID eingeben und bestätigen

## Kleine Motoren Kalibrieren
- Im Debug Tool:
  - Bei Servo Control -> Write auswählen
  - Wert bei Goal auslesen
  - Reiter Programming -> Adress 31: Position Offset Value auswählen
  - Neuer Offset = alter Offset + (Goal - 2047)
  - Neuen Offset speichern
  - Im Reiter Debug -> Servo Control -> Goal: Wert 2047 eingeben und "Set" klicken

## Große Motoren kalibrieren
- Betreffenes Gelenk demontieren sodass Motor sich frei bewegen lässt
- Im Debug Tool:
  - Im Reiter Debug -> Servo Control -> Goal: Wert 2047 eingeben und "Set" klicken
- Gelenk in gewünschter Kalibrierungsposition wieder zusammen setzen