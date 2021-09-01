# Composing Types

__Category: TypeScript__

Types can be composed together using the union operator or the intersection operator.

### Union operator

Unions are created using the | (pipe) operator. This means a value can have any valid TypeScript type in the union.

```javascript
type AccountCode = number | string
```

Using the above, the following assignments are valid:

```javascript
const firstAccountCode: AccountCode = 'abcaed34112';
const secondAccountCode: AccountCode = 4332914124;
```

### Intersection operator

Intersections create a completely new type that has all the properties of the types being intersected together.

Assume the following types:

```javascript
type Product = {
  code: string;
  manufacturer: string;
  description: string;
  features?: string[];
};

type Supplier = {
  name: string;
}

type StockDetails = {  
  code: string;
  inventoryLevel: number;
  supplier: Supplier;
}
```

A new type using the above types can be created with an intersection as follows:

```javascript
type InventoryItem = Product & StockDetails;

let firstInventoryItem: InventoryItem = {
    code: 200,
    manufacturer: true,
    description: 'Hula Hoop',
    inventoryLevel: 37,
    supplier: {
        name: 'Plastics R Us'
    }
}
```
