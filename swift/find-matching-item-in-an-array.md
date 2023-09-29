# Find Matching Item In An Array

__Category: Swift__

You can find a matching item in a Swift array containing a custom class type using the `first(where:)` method.

Given the following `Employee` class:

```swift
class Employee {
    let id: String
    let name: String,
    let email: String

    init(id: String, name: String, email: String) {
        self.id = id
        self.name = name
        self.email = email
    }
}
```

And array of employees:

```swift
let employees = [
    Employee(id: "b2ebf8bd-9124-4144-98f5-d1bbd8e9c258", name: "Steve Page", email: "steve.page@microspan.com"),
    Employee(id: "58ecde56-672d-4812-8935-acaae501bee1", name: "Sharon Herbert", email: "sharon.herbert@microspan.com"),
    Employee(id: "eb2a097e-59c3-4458-ac91-1af076c7a4d4", name: "Bob Jackson", email: "bob.jackson@microspan.com")
]
```

Find the first matching item in the array as follows:

```swift
let employeeId = "eb2a097e-59c3-4458-ac91-1af076c7a4d4"

if let employee = employees.first(where: { $0.id == employeeId }) {
    print("Found employee \(employee.id): \(employee.name)")
} else {
    print("Unable to find employee")
}
```
