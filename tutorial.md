# My Tutorial
### @activities true

## Activity 1
### Step 1

### Climapse - Climate 🌍🌡️ changing over Time  ⏳️

Im folgenden Tutorial lernst Du
1. Die Temperatur auszulesen
2. Die Temperatur am PC auszugeben und zu bearbeiten

### Step 2

Zum Start lassen wir einfach Herzsymbol ``||basic.showIcon||`` einblenden, damit wir wissen,
ob der Microbit läuft. 

```blocks
basic.showIcon(IconNames.Heart)
```

### Step 3

Nun wollen wir als erstes die Temperatur anzeigen lassen. 
Dazu laden wir ``||basic.showString||`` den internen Sensorwert ``||input.temperature||`` 

```blocks
basic.forever(function () {
    basic.showString("" + (input.temperature()))
})
```

### Step 4

Im nächsten Schritt wollen wir die Temperatur an den PC übertragen 
mit ``||serial.writeValue||``.
Als Wertepaar wählen wir als Text *T in °C* und ``||input.temperatur||``.

```blocks
basic.forever(function () {
    basic.showString("" + (input.temperature()))
    serial.writeValue("T", input.temperature())
})
```

### Step 5

Für bessere Werte ist es angebracht eine kurze Pause #
zwischen dem Auslesen hinzuzufügen mit ``||basic.pause||`` von 1 Sekunde, also 1000 Millisekunden.

```blocks
basic.forever(function () {
    basic.showString("" + (input.temperature()))
    serial.writeValue("T", input.temperature())
    basic.pause(1000)
})
```

## Activity 2

* for PXT/microbit
<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
