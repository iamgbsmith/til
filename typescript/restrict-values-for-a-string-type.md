# Restrict Values For A String Type

__Category: TypeScript__

You can restrict the values used for a string type by creating a custom type alias.

For example, assume you want to restrict specific string literals for an order status, define the type as follows:

```javascript
type OrderStatus = 'entered' | 'shipped' | 'cancelled' | 'refunded';
```

Create a instance using the appropriate string literal:

```javascript
const orderStatus: OrderStatus = 'entered';
```

Using any other value will result in a compiler error.
