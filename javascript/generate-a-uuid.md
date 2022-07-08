# Generate A UUID

__Category: JavaScript__

You can generate a Version 4 UUID using the following code:

```javascript
const uuidv4 = () => {
  return ([1e7]+-1e3+-4e3+-8e3+-1e11).replace(/[018]/g, c =>
    // eslint-disable-next-line prettier/prettier
    (c ^ crypto.getRandomValues(new Uint8Array(1))[0] & 15 >> c / 4).toString(16)
  );
};
```

Generate a UUID:

```javascript
let randomUUID = uuidv4();
console.log(`UUID is ${randomUUID}`);
```

Output:

```shell
UUID is 166cf86c-de31-4eaf-89c3-1c87c3fd754d
```
