
# Displaying Child List Elements

__Category: React__

For performance reasons, it is important to include a unique key when rendering a list of child elements in React. Keys act as an identifier and provide React with a way to determine which items have been added, removed, or changed.

If you omit the key you will see the following error in the JavaScript console:

```console
Warning: Each child in a list should have a unique "key" prop.
```

When rendering a collection, include a `key` with a value derived from the array index for each item as follows:

```javascript
const StoreInventory:React.FC = () => {
  const products = ['Appliances', 'Books', 'Computers', 'Cosmetics', 'Shoes', 'Sporting Goods', 'Stationary'];

  return (
    <>
      {
        products.map((product, index) => 
          <Product key={index}>{product}</Product>
        )
      }
    </>
  )
}
```
