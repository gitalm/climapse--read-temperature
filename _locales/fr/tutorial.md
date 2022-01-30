# _locales/fr/tutorial
# My Tutorial
## Step 1

### Climapse - Climate 🌍🌡️ changing over Time  ⏳️

Dans ce tutoriel, tu vas apprendre à
1. lire la température
2. afficher et travailler avec la température sur ordinateur

## Step 2

Pour commencer, nous affichons le symbole du cœur ``||basic.montrer l'icône||`` pour vérifier que le microbit fonctionne. 

```blocks
basic.showIcon(IconNames.Heart)
```

## Step 3

Nous voulons d'abord afficher la température. 
Alors nous utilisons ``||basic.zeige Text||`` den internen Sensorwert ``||input.Temperatur||`` 

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


* for PXT/microbit
<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
