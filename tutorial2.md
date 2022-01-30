### @activities 1

## Introduction

### Introduction step

# Remote Sensing

** Climapse - Climate 🌍🌡️ changing over Time  ⏳️ **

Im folgenden Tutorial lernst Du
1. Sensorwerte an einen micro:bit zu senden
2. Die Sensorwerte zu empfangen und aufbereiten



## Activity 1

### Funkgruppe für Sender

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

### Sensorwert senden

Der Wert des internen Tempertursensors ``||input:Temperatur||`` wird nun dauerhaft 
als Wertepaar gesendet, mit dem Befehl ``||radio:sende Wertepaar||``. Das Wertepaar soll auswählen
der Abkürzung *T* für Temperatur bestehen und dem Wert der ``||input:Temperatur||``.

```blocks
basic.forever(function () {
    radio.sendValue("T", input.temperature())
})
```

### Aktivität anzeigen Sender

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

## Activity 2

### Funkgruppe Empfänger

Verwende nun den zweiten micro:bit und setze bei diesem ebenso die ``||radio:Funkgruppe||`` auf diesselbe Zahl, also *42*.
Um Sender und Empfänger zu unterscheiden, kann man eine Schlange 🐍 ``||basic:zeige Symbol||`` anzeigen zum Start.

```blocks
radio.setGroup(42)
basic.showIcon(IconNames.Snake)
```

### Variable erstellen

Um die Werte zum Empfangen benötigt man eine Variable ``||variable:Variable||``. **Erstelle eine Variable** diese
im Menü und nenne diese beispielsweise ``||variable:Temp||``.


### Wertepaar empfangen

Empfange nun das Wertepaar ``||radio:wenn Wertepaar empfangen||`` und ordne den Wert der Variablen **Temp** über ``||variable:setze Temp||``
auf den empfangenen Wert ``||radio:value||``.

```blocks
radio.onReceivedValue(function (name, value) {
    Temp = value
})
```
