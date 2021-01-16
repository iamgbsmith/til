# Create A Callback Function

__Category: Swift__

Callback functions (also known as completion handlers) in Swift can be achieved using a closure. This example assumes you have two classes and need to call a method in one class from the other class, also passing an argument.

### Main class

This class contains the function you will call from the other class.

```swift
let outdoorSensor = TemperatureSensor()
var outdoorTemperature: Int = 0

func someMethod() {
    
    outdoorSensor.initialize(callback: { (temperature : Int) -> Void in
        self.outdoorTemperature = temperature
        if (self.outdoorTemperature > 0) {
            print("Temperature outside is greater than zero.")
        } else {
            print("Temperature outside is less than zero. It's cold!")
        }
    })
}
```

### Invoking class

This code is in a different class and will invoke the callback function.

```swift
// TemperatureSensor.swift
var temperatureCallback: ((Int) -> ())?

func initialize(temperatureCallback: @escaping(Int) -> Void) {
    self.temperatureCallback = temperatureCallback
}

// When a temperature update is received, invoke the callback with the new temperature reading
func temperatureUpdateReceived(_ temperature: Int) {
    self.temperatureCallback!(temperature)
}
```