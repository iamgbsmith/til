# Get Unique Values From A JSON Array

__Category: JavaScript__

Assuming a JSON array:

```json
const vehicles = [
  {
      "manufacturer": "BMW",
      "car": "M4 CSL"
  },
  {
      "manufacturer": "BMW",
      "car": "X3 M Competition"
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
      "car": "718 Cayman GT4 RS"
  },
  {
      "manufacturer": "Porsche",
      "car": "Taycan Turbo S"
  },
  {
      "manufacturer": "Volkswagen",
      "car": "Golf GTI Clubsport"
  },
  {
      "manufacturer": "Volkswagen",
      "car": "Golf R"
  }
];
```

To obtain a unique collection of `manufacturer` values, use the following:

```javascript
const manufacturers = vehicles.map((value) => value.manufacturer).filter((value, index, _arr) => _arr.indexOf(value) == index);
console.log(manufacturers);
```
