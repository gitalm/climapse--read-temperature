# 📡 Remote Sensing - Receiving

## Step 1

### Climapse - Climate 🌍🌡️ changing over Time  ⏳️ 

In the following tutorial you learn
1. send sensor values to a micro:bit
2. read and draw the sensor values

## Radio group receiver

Use a second micro:bit and set the ``||radio:setGroup||`` to the identical number, eg *42*.
To distinguish the sender and receiver, we indicate this device by a snake 🐍 ``||basic:showIcon||`` during start process.

```blocks
radio.setGroup(42)
basic.showIcon(IconNames.Snake)
```

## Create a variable

To store the received values we have to create a variable ``||variable:variable||``. **Create a variable** in the menuand name this eg ``||variable:Temp||``.


## Receive values

Receive the values by ``||radio:onReceivedValue||`` and store the value in **Temp** by ``||variable:setVariable||``
with the received value ``||radio:value||``.

```blocks
radio.onReceivedValue(function (name, value) {
    Temp = value
})
```

## Send data to PC

After wireless receiving the value you can write the stored value ``||variable:Temp||`` by ``||serial:writeValue||`` to the PC.

```blocks
basic.forever(function () {
    serial.writeValue("T", Temp)
})
```

## Show acitivity

A blinking diamond 💎 can sho the status from the microbit while your PC is graphing the values in the  *console*. The data can be also downloaded for further analysis with some spreadsheet applications.

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
