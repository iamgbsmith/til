# Get Random Value From An Array

__Category: JavaScript__

Assuming an array of values:

```javascript
const manufacturers = [
  'Aston Martin', 
  'Audi', 
  'BMW', 
  'Jaguar', 
  'McLaren', 
  'Mercedes-Benz', 
  'Porsche', 
  'Renault', 
  'Volkswagen'
];
```

You can obtain a random value from the array as follows:

```javascript
const randomItem = manufacturers[Math.floor(Math.random() * manufacturers.length)];
```
