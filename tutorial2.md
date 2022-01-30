# Remote Sensing
## Step 1

### Climapse - Climate 🌍🌡️ changing over Time  ⏳️

Im folgenden Tutorial lernst Du
1. Sensorwerte an einen miccro:bit zu senden
2. Die Sensorwerte zu empfangen und aufbereiten

## Step 2

Zum Start lassen wir einfach Entensymbol ``||basic.showIcon||`` 
einblenden, damit wir wissen,
ob der Microbit läuft. 
Zusätzlich müssen wir 
eine ``||radio:Setze Funkgruppe||``, beispielsweise *42* auswählen. 
In dieser muss dann auch der empfangende micro:bit sein.

```blocks
radio.setGroup(42)
basic.showIcon(IconNames.Duck)
```

## Step 3

Der Wert des internen Tempertursensors ``||input:Temperatur||`` wird nun dauerhaft 
als Wertepaar gesendet, mit dem Befehl ``||radio:sende Wertepaar||``. Das Wertepaar soll auswählen
der Abkürzung *T* für Temperatur bestehen und dem Wert der ``||input:Temperatur||``.

```blocks
basic.forever(function () {
    radio.sendValue("T", input.temperature())
})
```

## Step 4

Mit einem blinkenden Diamanten ``||basic:zeige Symbol||`` kann man die Aktivität 
des Sender überwachen. Zwischen einer Sendepause ``||basic:Pause||`` von 1 Sekunde wird 
der kleine und große Diamant abwechselnd dargestellt.

```blocks
basic.forever(function () {
    radio.sendValue("T", input.temperature())
    basic.showIcon(IconNames.Diamond)
    basic.pause(1000)
    basic.showIcon(IconNames.SmallDiamond)
})
```
