# Civilwarnings
Implementation of Civil Warnings from German BKK to DAPNET

# Ideen für Algorithmus und Behandlung

## Gefahrendurchsagen
Quelle: https://warnung.bund.de/bbk.mowas/gefahrendurchsagen.json
* Gefahrendurchsagen sind selten, aber mit hoher Wichtigkeit
* Aussendung an ``allskypercall`` an einen Sender, der im Gültigkeitsbereich ist. Bis es die Möglichkeit gibt, einen Sender direkt anzusprechen wird man mit den Transmitter-Gruppen auf Bundesland-Ebene leben müssen.
* Bestimmung, welches Bundesland das Richtige ist:
** Nehme Bundeslandgrenzen von https://github.com/DecentralizedAmateurPagingNetwork/Core/issues/116 http://wiki.openstreetmap.org/wiki/WikiProject_Germany/Grenzen
** Überprüfe, ob Gefahrendurchsage-Polygon in einem Bundesland-Polygon ist
** Wenn ja, sende Ruf an ``allskypercall`` mit dieser TX-Gruppe aus.

## Unwetter
Quelle: https://warnung.bund.de/bbk.dwd/unwetter.json
* Nicht ganz so wichtig, daher als Rubrik pro Bundesland
* Bestimmung, welches Bundesland das Richtige ist:
** Nehme Bundeslandgrenzen von https://github.com/DecentralizedAmateurPagingNetwork/Core/issues/116 http://wiki.openstreetmap.org/wiki/WikiProject_Germany/Grenzen
** Überprüfe, ob Unwetter-Polygon in einem Bundesland-Polygon ist
** Wenn ja, füge Nachricht in Rubrik ein
