# Get Width Or Height Of Window

__Category: React__

You can dynamically obtain the width or height of the document window using React Hooks. In this example, window resize events will trigger a call to obtain, then store the new window width and height in the application state.

Store the width and height with `useState` as follows:

```javascript
const [screenSize, getDimension] = useState({
  width: window.innerWidth,
  height: window.innerHeight
});

const setDimension = () => {
  getDimension({
    width: window.innerWidth,
    height: window.innerHeight
  })
}
```

Add a listener to handle window resize events with `useEffect` as follows:

```javascript
useEffect(() => {
  window.addEventListener('resize', setDimension);
  return(() => {
      window.removeEventListener('resize', setDimension);
  })
}, [screenSize])
```

Get the screen width and height:

```javascript
console.log(`Screen width is ${screenSize.width} and screen height ${screenSize.height}`);
```
