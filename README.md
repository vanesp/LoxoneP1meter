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

## Domoticz Set-up of P1 Device

![P1 Device](https://github.com/vanesp/LoxoneP1meter/blob/master/img/domoticz_p1.png)

## Domoticz Devices

![Devices](https://github.com/vanesp/LoxoneP1meter/blob/master/img/domoticz_devices.png)

# Loxone Config

## Blocks configuration

![Blocks](https://github.com/vanesp/LoxoneP1meter/blob/master/img/loxone_config.png)

## Virtual Device Eectricity

![Virtual Input](https://github.com/vanesp/LoxoneP1meter/blob/master/img/virtual_inputs.png)

## Electricity split into counter and usage

![Counter](https://github.com/vanesp/LoxoneP1meter/blob/master/img/electricity.png)

![Usage](https://github.com/vanesp/LoxoneP1meter/blob/master/img/usage.png)

## Parameters of Electricity block

![Loxone Block Electricity](https://github.com/vanesp/LoxoneP1meter/blob/master/img/block_electricity.png)

## Virtual Device Gas

![Virtual Input](https://github.com/vanesp/LoxoneP1meter/blob/master/img/virtual_input_gas.png)

## Gas counter only

In mijn installatie geeft de P1 meter slechts één keer per uur een update.

![Counter](https://github.com/vanesp/LoxoneP1meter/blob/master/img/gas.png)

## Parameters of Gas block

![Loxone Block Gas](https://github.com/vanesp/LoxoneP1meter/blob/master/img/block_gas.png)
