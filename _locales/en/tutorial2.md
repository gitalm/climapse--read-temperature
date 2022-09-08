# _locales/en/tutorial2

# 📡 Remote Sensing - Sending

## Step 1

### Climapse - Climate 🌍🌡️ changing over Time  ⏳️ 

In the following tutorial you learn
1. send values from the internal sensors of the micro:bit
2. receive the values and let your PC draw a diagram 📈

## Radio group for the transmitter

In the beginning we use ``||basic.showIcon||`` 
to indicate that the micro:bit is running. 
Additionally we use ``||radio:setGroup||`` eg. *42*. 
The receiver must use the same group.

```blocks
radio.setGroup(42)
basic.showIcon(IconNames.Duck)
```

## Send sensor value

The value from the internal sensor ``||input:temperature||`` will be now continously send by ``||radio:sendValue||``. We name it *T* for temperature and use the value ``||input:temperature||``.

```blocks
basic.forever(function () {
    radio.sendValue("T", input.temperature())
})
```

## Show activity

A blinking diamond ``||basic:showIcon||`` is indicating the active microcontroller. The sensor need a time out ``||basic:pause||`` of roughly a second and the diamond is indicating the active status from the sender.

```blocks
basic.forever(function () {
    radio.sendValue("T", input.temperature())
    basic.showIcon(IconNames.Diamond)
    basic.pause(1000)
    basic.showIcon(IconNames.SmallDiamond)
})
```