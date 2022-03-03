# Handle Key Press Events

__Category: JavaScript__

Key press events on a physical keyboard such as keydown, keypress, and keyup generate a code. 

To handle these events, add a key listener to the window:

```javascript
window.addEventListener('keydown', onKeyDown);
```

Use the following to print out the key code when a keydown event is generated:

```javascript
const onKeyDown = (event: any) => {
  console.log(`Event code ${event.code}`);
}
```

For example: 

* The L key will generate a key code of `KeyL`
* The 2 key will generate a key code of `Number2`
* The left Shift key will generate a key code of `ShiftLeft`

The ASCII value for the key event can be shown using `event.keyCode` which returns an integer. For example, the letter `a` returns a value of 65.
