# Wind Turbine Tutorial

```package
fwd-edu-breakout=github:climate-action-kits/pxt-fwd-edu/fwd-breakout
=github:climate-action-kits/pxt-fwd-edu
=github:climate-action-kits/pxt-fwd-edu

```
## Step 1 @showdialog
Plug your USB cable into the micro:bit. 
Insert the micro:bit into the Climate Action Board.
![breakout board with microbit](https://raw.githubusercontent.com/mbakhtar/wind-turbine-lesson-tutorial/master/breakout-resized.png)

## Step 2 @showdialog
Click on the button to the right of the download and follow the steps to pair our micro:bit.
![pairing gif](https://raw.githubusercontent.com/mbakhtar/iste-wind-energy-v1/master/pair%20microbit-280x203.gif)

## Step 3
Click on the ``||fwdSensors:Sensors||`` drawer and find the 
``||fwdSensors:on dial1 turned delta||`` block. Duplicate it.
```blocks
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.dialDirection.cw, function (delta) {
    })
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.dialDirection.cw, function (delta) {
    })
```
## Step 4
Change the direction arrow of the second block. 
Hit download to activate your ``||fwdSensors:Dial||`` and a 
``||fwdSensors:Touch||`` button.
![dial direction](https://raw.githubusercontent.com/mbakhtar/wind-turbine-lesson-tutorial/master/dial%20direction%20change.gif)
```blocks
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.dialDirection.cw, function (delta) {
    })
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.dialDirection.ccw, function (delta) {
    })
```
## Step 5
Click the ``||fwdSensors:Sensors||`` drawer and add a 
``||fwdSensors:on touch down||`` block to the coding screen. 
```blocks
fwdSensors.touch.fwdOnTouch(jacdac.ButtonEvent.Down, function () {
    })
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.dialDirection.cw, function (delta) {
    })
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.dialDirection.ccw, function (delta) {
})
```
## Step 6
To control the speed of the ``||Wind Turbine||``, use 
``||fwdSensors:Dial||`` from the ``||fwdSensors:Sensors||`` drawer. 
Nest ``||fwdMotors:set servo1 to 0%||`` under the 
``||fwdSensors:on dial1 turned delta||`` block.
```blocks
fwdSensors.touch.fwdOnTouch(jacdac.ButtonEvent.Down, function () {
    })
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.dialDirection.cw, function (delta) {
    fwdMotors.servo1.fwdSetSpeed(0)
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.dialDirection.ccw, function (delta) {
})
```

## Step 7
Duplicate ``||fwdMotors:set servo1 to 0%||`` and place it under the other
``||fwdSensors:on dial1 turned delta||`` block and the
``||fwdSensors: on touch down||``block.
```blocks
fwdSensors.touch.fwdOnTouch(jacdac.ButtonEvent.Down, function () {
    fwdMotors.servo1.fwdSetSpeed(0)
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.dialDirection.cw, function (delta) {
    fwdMotors.servo1.fwdSetSpeed(0)
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.dialDirection.ccw, function (delta) {
    fwdMotors.servo1.fwdSetSpeed(0)
})
```
## Step 8
Set the speed of the ``||Wind Turbine||`` according to the rotation of the 
``||fwdSensors:Dial||``. Click on ``||fwdSensors:Sensors||``.
Drag the ``||fwdSensors:dial1 absolute position block||``.
It should match/overlay/overlap the 0% of the ``||fwdMotors:set servo1 0%||``
block.
```blocks
fwdSensors.touch.fwdOnTouch(jacdac.ButtonEvent.Down, function () {
    fwdMotors.servo1.fwdSetSpeed(0)
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.dialDirection.cw, function (delta) {
    fwdMotors.servo1.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.dialDirection.ccw, function (delta) {
    fwdMotors.servo1.fwdSetSpeed(0)
})
```
## Step 9
Do the same for the other ``||fwdSensors:on dial1 turned delta||``
and ``||fwdMotors:set servo1 0%||``.
```blocks
fwdSensors.touch.fwdOnTouch(jacdac.ButtonEvent.Down, function () {
    fwdMotors.servo1.fwdSetSpeed(0)
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.dialDirection.cw, function (delta) {
    fwdMotors.servo1.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.dialDirection.ccw, function (delta) {
    fwdMotors.servo1.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
```
## Step 10
The ``||fwdMotors:set servo1 0%||`` under the ``||fwdSensors:on touch down||``
block stays the same. Check your code by downloading it and turning the 
``||fwdSensors:Dial||`` clockwise.
```blocks
fwdSensors.touch.fwdOnTouch(jacdac.ButtonEvent.Down, function () {
    fwdMotors.servo1.fwdSetSpeed(0)
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.dialDirection.cw, function (delta) {
    fwdMotors.servo1.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
fwdSensors.dial1.fwdOnDialTurned(fwdSensors.dialDirection.ccw, function (delta) {
    fwdMotors.servo1.fwdSetSpeed(fwdSensors.dial1.fwdPosition())
})
```
## Step 11
Congratulations on completing your project! 
Go back to the lesson for more activities and extensions.

```package
fwd-edu-breakout=github:climate-action-kits/pxt-fwd-edu/fwd-breakout
=github:climate-action-kits/pxt-fwd-edu
=github:climate-action-kits/pxt-fwd-edu
```
