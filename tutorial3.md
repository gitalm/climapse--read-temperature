# 📡 Remote Sensing - Receiving

** Climapse - Climate 🌍🌡️ changing over Time  ⏳️ **

Im folgenden Tutorial lernst Du
1. Sensorwerte an einen micro:bit zu senden
2. Die Sensorwerte zu empfangen und aufbereiten

## Funkgruppe Empfänger

Verwende nun den zweiten micro:bit und setze bei diesem ebenso die ``||radio:Funkgruppe||`` auf diesselbe Zahl, also *42*.
Um Sender und Empfänger zu unterscheiden, kann man eine Schlange 🐍 ``||basic:zeige Symbol||`` anzeigen zum Start.

```blocks
radio.setGroup(42)
basic.showIcon(IconNames.Snake)
```

## Variable erstellen

Um die Werte zum Empfangen benötigt man eine Variable ``||variable:Variable||``. **Erstelle eine Variable** diese
im Menü und nenne diese beispielsweise ``||variable:Temp||``.


## Wertepaar empfangen

Empfange nun das Wertepaar ``||radio:wenn Wertepaar empfangen||`` und ordne den Wert der Variablen **Temp** über ``||variable:setze Temp||``
auf den empfangenen Wert ``||radio:value||``.

```blocks
radio.onReceivedValue(function (name, value) {
    Temp = value
})
```

## Daten an PC senden

Nach dem Empfangen der Daten können diese nun an den PC geschrieben werden über ``||serial:schreibe Wert||`` 
mit der Bezeichnung *T in °C* und dem Wert der Variablen ``||variable:Temp||``.

```blocks
basic.forever(function () {
    serial.writeValue("T", Temp)
})
```

## Aktivität anzeigen

Mit einem blinkden Diamanten 💎 kann man die Aktivität anzeigen lassen und auf dem Rechner über die *Konsole* die 
Werte des sendenden micro:bit verfolgen.
Diese können auch heruntergeladen werden. 

```blocks
radio.onReceivedValue(function (name, value) {
    Temp = value
})
let Temp = 0
radio.setGroup(42)
basic.showIcon(IconNames.Snake)
basic.forever(function () {
    serial.writeValue("T", Temp)
    basic.showIcon(IconNames.Diamond)
    basic.pause(1000)
    basic.showIcon(IconNames.SmallDiamond)
})

```

