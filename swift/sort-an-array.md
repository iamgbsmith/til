# Sort An Array

__Category: Swift__

Given a struct in Swift:

```swift
struct Manufacturer {
    var name: String
    var website: String
}
```

Assuming you have created the following array:

```swift
var manufacturers = [
    Manufacturer(name: "BMW", website: "https://www.bmw.com"),
    Manufacturer(name: "Toyota", website: "https://www.toyota.com"),
    Manufacturer(name: "Honda", website: "https://www.honda.com.au"),
    Manufacturer(name: "Audi", website: "https://www.audi.de"),
    Manufacturer(name: "Porsche", website: "https://www.porsche.com"),
    Manufacturer(name: "Nissan", website: "https://www.nissan.co.jp")
]
```

Sort the array in place as follows:

```swift
manufacturers.sort {
    $0.name < $1.name
}
```

Or create a sorted array from an existing array:

```swift
let sortedManufacturers = manufacturers.sorted {
    $0.name < $1.name
}
```