# Iterate An Array

__Category: JavaScript__

For loops can be used to iterate an array, however a more powerful approach is to use `.map()` which accepts a callback function.

Givan a JSON array:

```json
const vehicles = [
  {
    "id": "26832b81-f3af-427a-ae3a-604f27ba9f4e", "make": "Audi", "model": "RS6"
  },
  {
    "id": "f2edf84c-23a8-4f7e-8707-69e87a88dd28", "make": "BMW", "model": "M5 CS"
  },
  {
    "id": "d2dafa90-e0d7-42d0-ae46-25d618ddee1a", "make": "Ferrari", "model": "SF90 Stradale"
  },
  {
    "id": "003ef959-f119-42ac-9625-99e3fa25f844", "make": "Ford", "model": "GT"
  },
  {
    "id": "ea93f456-1b15-4520-bae5-5cb35cf139d1", "make": "Porsche", "model": "911 GT2 RS"
  },
];
```

Iterate through the contents as follows:

```javascript
vehicles.map(item => {
  console.log('Make: ' + item.make + ', model: ' + item.model);
})
```

It is also possible to call a function on each item in an array.

For example, given an an array of integers you can double each value and assign to a new array:

```javascript
const bagSizes = [3, 6, 12, 14, 17, 22, 25, 30];
```

Double the value of each item as follows:

```javascript
const increaseSize = bagItem => bagItem * 2;
const bigBagSizes = bagSizes.map(increaseSize);
console.log(bigBagSizes);
```
