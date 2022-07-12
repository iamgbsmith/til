# Programatically Transfer Focus

__Category: React__

Focus can be transferred programmatically between React components by calling `focus()` on a `ref`.

This TIL assumes the use of TypeScript.

Assume you have a text input field. Create a ref to it and a method to transfer focus:

```javascript
const searchInputRef = useRef<HTMLInputElement>(null);

const transferFocus = () => {
  if (searchInputRef.current !== null) {
    searchInputRef.current.focus();
  }
  console.log('Transferring focus to search input');
}
```

Assign the ref to the text input field:

```javascript
<input ref={searchInputRef}>
  // etc
</input>
```

Transfer focus using the following:

```javascript
transferFocus();
```

__Note:__ You must specify the type for the ref (for example `HTMLInputElement`), otherwise the TypeScript compiler will complain about a potential null reference showing an error message of `Object is possibly null`.
