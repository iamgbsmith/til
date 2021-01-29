# Format A Date String

__Category: Swift__

Dates in Swift can be formatted using a custom format to show either the date, time, or both.

```swift
// Date formatter with custom format
let dateFormatter = DateFormatter()
dateFormatter.dateFormat = "dd-MM-yyyy"

// Create a date and print out with applicable format
let now = Date()
let someDateString = dateFormatter.string(from: now)
print("Date is " + someDateString)
```

Output:

```shell
Date is 22-12-2020
```

If you are printing out the time, it will be displayed in local time if the timezone has not been set.
