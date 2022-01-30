# Remote Sensing

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
