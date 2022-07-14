# Get Width Or Height Of Device Window

__Category: React Native__

You can obtain the width or height of a device window with the `useWindowDimensions()` hook.

```javascript
const window = useWindowDimensions();
const {width, height} = window;
console.log(`Width is ${width} and height is ${height}`);
```

The values for width and height automatically update the when screen size changes.

Some operating systems allow users to scale their font sizes larger or smaller for reading comfort. Font scale can also be obtained using:

```javascript
useWindowDimensions().fontScale;
```

Pixel ratio can be obtained using:

```javascript
useWindowDimensions().scale;
```

A value of 1 indicates PPI/DPI of 96 (76 on some platforms). A value of 2 indicates a Retina or high DPI display.
