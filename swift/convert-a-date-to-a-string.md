# Convert A Date To A String

__Category: Swift__

You can convert a date to a localised string in Swift with the following code:

```swift
print(Date().description(with: .current))
```

Output:

```swift
Tuesday, 17 October 2023 at 10:02:28 PM New Zealand Daylight Time
```

To convert to ISO8601 format showing UTC, use the following code:

```swift
let formatter = ISO8601DateFormatter()
formatter.formatOptions = [.withInternetDateTime,
                            .withDashSeparatorInDate,
                            .withFullDate,
                            .withFractionalSeconds,
                            .withColonSeparatorInTimeZone]

// ...     
print(formatter.string(from: Date()))
```

Output:

```
2023-10-17T09:15:38.115Z
```
