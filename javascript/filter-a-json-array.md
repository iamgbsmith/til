# Filter A JSON Array

__Category: JavaScript__

You can filter a JSON array by matching on elements.

Given the following JSON array called `cars`:

```json
[
    {
        "manufacturer": "BMW",
        "car": "M3 Competition"
    },
    {
        "manufacturer": "BMW",
        "car": "X5 M Competition"
    },
    {
        "manufacturer": "Honda",
        "car": "Civic Type R"
    },
    {
        "manufacturer": "Ford",
        "car": "Mustang GT"
    },
    {
        "manufacturer": "Porsche",
        "car": "911 GT3"
    },
    {
        "manufacturer": "Volkswagen",
        "car": "Golf GTI Clubsport"
    },
    {
        "manufacturer": "Volkswagen",
        "car": "T-ROC R"
    }
]
```

To return items where the element matches a specific value:

```javascript
var filteredItems = cars.filter((car) => car.manufacturer === "BMW");
```
