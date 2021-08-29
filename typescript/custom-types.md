# Custom Types

__Category: TypeScript__

TypeScript custom types are created using the `type` keyword followed by the name and then an assignment to a {} block with the type properties. 

### Example custom type

Properties can be specified as primitives or custom types. 

Optional properties are specified using the `?` modifier. You can omit any of the properties when creating a value with that type.

```javascript
type Vehicle = {
  manufacturer: string;
  model: string;
  isPerformanceVehicle: boolean;
  weight: number;
  power: number;
  torque: number;
  topSpeed?: number;
  features: string[];
};
```

Using the above example, create an instance of the type as follows:

```javascript
const sportsCar: Vehicle = {
  manufacturer: 'BMW',
  model: 'M4 Competition',
  isPerformanceVehicle: true,
  weight: 1725,
  power: 375,
  torque: 650,
  features: ['Engine Auto Stop-Start Feature', 'Regenerative Alternator', 'Black Grille', 'LED Brakelights']
};
```

### Using comments for code completion hints

Adding comments to a type using TSDoc format will display hints when using code completion. For example:

```javascript
type Product = {
  /**
   * Company that created the product.
   */ 
  manufacturer: string;
  /**
   * Cost of the product in the base currency.
   */
  price: number;
};
```
