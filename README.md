# LoxoneP1meter
Beschrijving van de set-up van een koppeling tussen P1 meter en Loxone

## Hardware

Ik heb de eerste kabel (P1 Converter Kabel, p1 naar USB) op deze webshop gekocht (http://www.smartmeterdashboard.nl/webshop) (Eur 19,95).
Deze P1 Convertercable is volledig 'plug&play', dus inclusief gemonteerde RJ11 connector, geconfigureerd voor de P1 poort van uw slimme meter
en getest op correcte werking. Alle  Nederlandse, Luxemburgse en Belgische (alleen Fluvius en Sibelga) slimme meters met een P1/H1 poort 
dsmr 2/3/4 en (e)smr 5) kunnen worden uitgelezen met deze P1 Converter Cable.

Ik heb een Domoticz installatie op de Raspberry Pi, met de smart meter kabel in de USB socket, en met een MQTT gateway… Setup Domoticz to
support MQTT (see  https://www.domoticz.com/wiki/MQTT). Voor het uitlezen van de slimme meter, lees: https://wiki.pieper.eu/slimme-meter-uitlezen-1
Het grote topic: http://www.domoticz.com/forum/viewtopic.php?f=14&t=4970

Domoticz is misschien overkill, maar ik gebruik het ook om mijn weerstation waardes te bewaren en te koppelen aan Loxone (werkt heel goed).
De waardes van de P1 sensor worden via Domoticz gepublished op een URL. Die url is: 
http://ipadresvanRPi:8080/json.htm?type=devices&rid=1 (voor electra)
of rid=2 voor gas maar die rid hangt af van welke devices je nog meer aan Domoticz hebt gekoppeld.


