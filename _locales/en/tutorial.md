# _locales/en/tutorial
# My Tutorial
## Step 1

### Climapse - Climate 🌍🌡️ changing over Time  ⏳️

In the following tutorial you learn
1. reading the temperature.
2. send the temperature to the pc and work with it

## Step 2

In the beginning we show a heart symbol ``||basic.showIcon||``. So we know the micro:bit is running.

```blocks
basic.showIcon(IconNames.Heart)
```

## Step 3

First we want to show as the temperature value from the built in sensor. 
The code ``||basic.showString||`` should show the ``||input.temperature||`` 

```blocks
basic.forever(function () {
    basic.showString("" + (input.temperature()))
})
```

## Step 4

In the following step we want to send the data to the connected PC with 
 ``||serial.writeValue||``.
For the text we choos *T in °C* and as value we use ``||input.temperature||``.

```blocks
basic.forever(function () {
    basic.showString("" + (input.temperature()))
    serial.writeValue("T", input.temperature())
})
```

## Step 5

There must be a little pause between reading further values, so we add 
``||basic.pa#||`` with a 1sec, just 1000 milii seconds.

```blocks
basic.forever(function () {
    basic.showString("" + (input.temperature()))
    serial.writeValue("T", input.temperature())
    basic.pause(1000)
})
```

## Step 6

Download the code to your micro:bit and control after that the *console* to watch the values.


 <!-- for PXT/microbit -->
<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
