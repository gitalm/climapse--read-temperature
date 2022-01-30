# _locales/de/tutorial
# My Tutorial
## Step 1

### Climapse - Climate 🌍🌡️ changing over Time  ⏳️

Im folgenden Tutorial lernst Du
1. Die Temperatur auszulesen
2. Die Temperatur am PC auszugeben und zu bearbeiten

## Step 2

Zum Start lassen wir einfach Herzsymbol ``||basic.zeige Symbol||`` einblenden, damit wir wissen,
ob der Microbit läuft. 

```blocks
basic.showIcon(IconNames.Heart)
```

## Step 3

Nun wollen wir als erstes die Temperatur anzeigen lassen. 
Dazu laden wir ``||basic.zeige Text||`` den internen Sensorwert ``||input.Temperatur||`` 

```blocks
basic.forever(function () {
    basic.showString("" + (input.temperature()))
})
```

## Step 4

Im nächsten Schritt wollen wir die Temperatur an den PC übertragen 
mit ``||serial.schreibe Wertepaar||``.
Als Wertepaar wählen wir als Text *T in °C* und ``||input.Temperatur||``.

```blocks
basic.forever(function () {
    basic.showString("" + (input.temperature()))
    serial.writeValue("T", input.temperature())
})
```

## Step 5

Für bessere Werte ist es angebracht eine kurze Pause #
zwischen dem Auslesen hinzuzufügen mit ``||basic.Pause||`` von 1 Sekunde, also 1000 Millisekunden.

```blocks
basic.forever(function () {
    basic.showString("" + (input.temperature()))
    serial.writeValue("T", input.temperature())
    basic.pause(1000)
})
```

## Step 6

Lade nun den Code auf deinen micro:bit und öffne anschließend die *Konsole* um die Werte zu sehen.


 <!-- for PXT/microbit -->
<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
