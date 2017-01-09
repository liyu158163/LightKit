# LightKit
[![License](http://img.shields.io/badge/license-BSD-blue.svg?style=flat-square)](https://github.com/maxmouchet/LightKit/blob/master/LICENSE)
[![CocoaPods compatible](https://img.shields.io/cocoapods/v/LightKit.svg?style=flat-square)](#)
[![Carthage compatible](https://img.shields.io/badge/Carthage-compatible-4BC51D.svg?style=flat-square)](#)

Access the ambient light sensors, and control MacBook's display & keyboard brightness in Swift.

![LightKit](http://cdn.makeagif.com/media/5-05-2015/muJWM6.gif)

**Warning:** While it should be safe to play with the backlight, I am not responsible for any damages made to a computer using this code.

## Installation

```bash
# Podfile
pod "LightKit"

# Cartfile
github "maxmouchet/LightKit"
```

## Usage
```swift
import LightKit
let lk = LightKit()! // May be nil if it failed to open I/Os.
```

**Note :** Most methods and properties are returning optional as I/Os requests may fail if sensors and controllers could not be found.

#### Ambient light sensors
```swift
let lightSensorsReadings = lk.lightSensors
print("Left sensor: \(lightSensorsReadings?.left).")
print("Right sensor: \(lightSensorsReadings?.right).")
```

#### Display
```swift
print("Display brightness is \(lk.displayBrightness)")
lk.setDisplayBrightness(0.8) // A value between 0 and 1.
```

```swift
lk.setDisplayPower(false) // Put display to sleep
lk.setDisplayPower(true) // Wake up display
```

#### Keyboard
```swift
print("Keyboard brightness is \(lk.keyboardBrightness)")
lk.setKeyboardBrightness(0.8) // A value between 0 and 1.
```
